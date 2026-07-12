# Resume Recommendation Pipeline

## 1. Load the Sentence Transformer Model

```python
model = SentenceTransformer("sentence-transformers/all-MiniLM-L6-v2")
```

* Loads the pre-trained **all-MiniLM-L6-v2** model.
* Converts resume text into **384-dimensional embeddings**.
* These embeddings capture the semantic meaning of the resume instead of just matching keywords.

---

## 2. Generate Resume Embeddings

```python
resume_embeddings = model.encode(
    df["resume_text"].tolist(),
    batch_size=32,
    show_progress_bar=True,
    convert_to_numpy=True
)
```

### Parameters

* **df["resume_text"].tolist()**

  * Converts the `resume_text` column into a Python list.

* **batch_size=32**

  * Processes 32 resumes at a time for faster embedding generation.

* **show_progress_bar=True**

  * Displays the encoding progress.

* **convert_to_numpy=True**

  * Returns embeddings as NumPy arrays.

### Output

```python
resume_embeddings.shape
```

```
(7006, 384)
```

* **7006** → Number of resumes
* **384** → Embedding dimension

---

## 3. Create the FAISS Index

```python
dimension = resume_embeddings.shape[1]

index = faiss.IndexFlatL2(dimension)
```

### Explanation

* `shape[1]` returns the embedding dimension (**384**).
* `IndexFlatL2` creates a FAISS index using **Euclidean (L2) distance**.
* Initially, the index is empty.

---

## 4. Add Embeddings to the Index

```python
index.add(
    np.array(resume_embeddings).astype("float32")
)
```

### Explanation

* Converts embeddings to `float32`, which FAISS requires.
* Stores every resume embedding inside the index.
* The index is now ready for similarity search.

---

## 5. Encode the Query Resume

```python
query = model.encode(
    [df.iloc[0]["resume_text"]],
    convert_to_numpy=True
).astype("float32")
```

### Explanation

* Selects one resume from the dataset (used here as a sample query).
* Converts it into a **384-dimensional embedding**.
* Converts the embedding to `float32`.

### Output

```python
query.shape
```

```
(1, 384)
```

---

## 6. Search Similar Resumes

```python
distance, indices = index.search(
    query,
    k=10
)
```

### Parameters

* **query**

  * Query resume embedding.

* **k=10**

  * Returns the 10 nearest resumes.

### Returned Values

```python
distance
```

Example:

```
[[0.00, 0.18, 0.35, 0.62, 0.81, ...]]
```

* Contains the L2 distance between the query and each retrieved resume.
* Smaller distance means higher similarity.

```python
indices
```

Example:

```
[[45, 18, 201, 8, 300, ...]]
```

* Contains the DataFrame row indices of the retrieved resumes.

---

## Understanding `indices[0]`

Suppose:

```python
indices =
[
    [45, 18, 201, 8, 300]
]
```

Since only **one query** is searched:

```python
indices[0]
```

returns:

```
[45, 18, 201, 8, 300]
```

These are the row numbers of the most similar resumes.

---

## Understanding `distance[0][0]`

Suppose:

```python
distance =
[
    [0.00, 0.18, 0.35, 0.62, 0.81]
]
```

Then:

* `distance[0]` → All distances for the first query.
* `distance[0][0]` → Distance to the closest resume.
* `distance[0][1]` → Distance to the second closest resume.
* `distance[0][2]` → Distance to the third closest resume.

The positions in `distance` correspond directly to the positions in `indices`.

---

## 7. Collect Job Roles

```python
recommendations = []

for idx in indices[0]:

    recommendations.extend([
        df.iloc[idx]["job_role_1"],
        df.iloc[idx]["job_role_2"],
        df.iloc[idx]["job_role_3"],
        df.iloc[idx]["job_role_4"],
        df.iloc[idx]["job_role_5"]
    ])
```

### Explanation

Each similar resume contains up to five possible job roles.

Instead of considering only one job role, the system collects all five from every similar resume.

For 10 similar resumes:

```
10 resumes × 5 job roles = 50 job-role candidates
```

These candidates are later used to generate recommendations.

---

## 8. Create Weighted Job Scores

```python
job_scores = defaultdict(float)
```

Creates a dictionary where every job starts with a score of `0.0`.

Example:

```python
{
    "Python Developer": 0.0,
    "Data Scientist": 0.0
}
```

---

## 9. Score Similar Resumes

```python
for rank, idx in enumerate(indices[0]):
```

Example:

```
indices[0]

[45, 18, 201]
```

`enumerate()` returns both the position (`rank`) and the resume index (`idx`).

| Rank | Resume Index |
| ---- | ------------ |
| 0    | 45           |
| 1    | 18           |
| 2    | 201          |

---

## 10. Convert Distance to Similarity

```python
similarity = 1 / (1 + distance[0][rank])
```

FAISS returns distances.

These are converted into similarity scores.

| Distance | Similarity |
| -------: | ---------: |
|     0.00 |       1.00 |
|     0.20 |       0.83 |
|     0.50 |       0.67 |
|     1.00 |       0.50 |

A smaller distance produces a larger similarity score.

---

## 11. Update Job Scores

```python
for col in job_columns:

    job = df.iloc[idx][col]

    if pd.notna(job):
        job_scores[job] += similarity
```

### Process

1. Read every job role from the retrieved resume.
2. Skip missing (`NaN`) values.
3. Add the resume's similarity score to that job role.

Example:

```
Python Developer += 0.92
ML Engineer += 0.92
Data Scientist += 0.92
```

More similar resumes contribute more to the final recommendation.

---

## 12. Sort Jobs by Score

```python
top_jobs = sorted(
    job_scores.items(),
    key=lambda x: x[1],
    reverse=True
)
```

Sorts all job roles by their accumulated similarity scores in descending order.

Example:

```
[
 ('Python Developer', 4.12),
 ('ML Engineer', 3.76),
 ('Data Scientist', 3.11),
 ('AI Engineer', 2.54),
 ('Backend Developer', 1.97)
]
```

---

## 13. Display the Top Recommendations

```python
print(top_jobs[:5])
```

Outputs the five highest-ranked job roles.

Example:

```
[
 ('Python Developer', 4.12),
 ('ML Engineer', 3.76),
 ('Data Scientist', 3.11),
 ('AI Engineer', 2.54),
 ('Backend Developer', 1.97)
]
```

These are the final recommended job roles for the uploaded resume.

---

# Overall Workflow

```
Resume Text
      │
      ▼
Sentence Transformer
      │
      ▼
384-Dimensional Embedding
      │
      ▼
FAISS Similarity Search
      │
      ▼
Top-k Similar Resumes
      │
      ▼
Extract Job Roles
      │
      ▼
Convert Distance → Similarity
      │
      ▼
Weighted Job Scoring
      │
      ▼
Sort by Score
      │
      ▼
Top 5 Recommended Job Roles
```

