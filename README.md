# 🚀 AI Resume Analyzer & Real-Time Job Recommendation System

An AI-powered web application that analyzes resumes using **Natural Language Processing (NLP)** and instantly recommends the most suitable job roles based on resume content. After predicting the best career matches, the application automatically fetches **real-time live job opportunities**, allowing users to explore and apply for relevant positions directly.

Unlike traditional resume analyzers that only provide role predictions, this project combines **AI-based resume analysis** with **live job recommendations**, making it a practical tool for job seekers.

---

# 📌 Project Overview

The goal of this project is to simplify the job search process by combining Artificial Intelligence with real-time job searching.

The application accepts resumes in **PDF** and **DOCX** formats, extracts the resume text, generates semantic embeddings using **Sentence Transformers (MiniLM)**, and compares them against a prepared resume dataset using **FAISS similarity search**. Based on the similarity scores, it recommends the most suitable job roles.

Once the recommendations are generated, the system automatically searches the internet for **real-time job openings** related to those roles using the **JSearch API**, providing users with both AI-powered career guidance and current job opportunities in one place.

---

# 🎯 Problem Statement

Many job seekers struggle to determine which job roles best match their skills and experience. Existing resume analyzers typically stop after suggesting job titles, requiring users to manually search multiple job portals to find relevant opportunities.

This project solves that problem by integrating:

- AI-powered resume analysis
- Intelligent job role recommendation
- Real-time live job recommendations

into a single application.

---

# 💡 Solution

The application follows a simple and intelligent workflow:

1. Upload Resume (PDF/DOCX)
2. Extract Resume Text
3. Generate Semantic Embeddings using MiniLM
4. Compare Resume using FAISS Similarity Search
5. Recommend Top Matching Job Roles
6. Fetch Real-Time Live Jobs
7. Display AI Recommendations and Live Job Opportunities

---

# 🎯 Objectives

- Build an AI-powered resume analysis system.
- Recommend suitable job roles using semantic similarity.
- Display real-time live job opportunities.
- Provide a modern and responsive user interface.
- Reduce manual effort involved in job searching.
- Demonstrate the integration of Machine Learning with Full-Stack Web Development.

---

# ⭐ Key Features

- 📄 PDF & DOCX Resume Upload
- 🤖 AI-Powered Resume Analysis
- 🧠 MiniLM Sentence Transformer Embeddings
- ⚡ FAISS Semantic Similarity Search
- 💼 Real-Time Live Job Recommendations
- 🌐 FastAPI REST API
- ⚛️ React + Vite Frontend
- 📱 Fully Responsive Design
- ☁️ Railway Backend Deployment
- 🚀 Vercel Frontend Deployment

---

# 🌟 Unique Selling Proposition (USP)

The biggest strength of this project is its ability to combine **AI Resume Analysis** with **Real-Time Live Job Recommendations**.

Most resume analyzers stop after recommending job roles.

This application goes one step further by automatically searching and displaying **live job opportunities** related to the predicted roles, allowing users to immediately explore and apply for relevant positions without visiting multiple job portals.

This transforms the application from a simple resume analyzer into a practical AI-powered career assistance platform.



# 🏗️ Chapter 2 – System Design & Architecture

This project follows a modern **Full-Stack AI Architecture** where the frontend, backend, machine learning model, and external APIs work together to provide intelligent resume analysis and real-time job recommendations.

---

# 🏛️ System Architecture

> *(Insert your architecture diagram here.)*

```md
![System Architecture](docs/system_architecture.png)
```

---

# 🔄 Application Workflow

The complete workflow of the application is illustrated below.

```text
User
 │
 ▼
Upload Resume (PDF / DOCX)
 │
 ▼
Frontend (React + Vite)
 │
 ▼
FastAPI Backend
 │
 ▼
Resume Text Extraction
 │
 ▼
Sentence Transformer (MiniLM)
 │
 ▼
Generate Resume Embeddings
 │
 ▼
FAISS Similarity Search
 │
 ▼
Top AI Job Role Recommendations
 │
 ▼
RapidAPI (JSearch API)
 │
 ▼
Real-Time Live Job Recommendations
 │
 ▼
Display Results to User
```

---

# 🧩 System Components

The application is divided into four major modules.

## 1️⃣ Frontend

The frontend provides a responsive and user-friendly interface where users can upload resumes, view AI-generated job recommendations, and explore real-time job opportunities.

### Responsibilities

- Resume Upload
- File Validation
- API Communication
- Recommendation Display
- Live Job Display
- Loading Animations
- Mobile Responsive UI

**Technology Used**

- React
- Vite
- Axios
- CSS

---

## 2️⃣ Backend

The backend acts as the central controller of the application.

It receives uploaded resumes, extracts text, communicates with the AI recommendation engine, searches live jobs, and returns results to the frontend.

### Responsibilities

- File Upload Handling
- Resume Processing
- AI Prediction
- Live Job Search
- REST API
- Error Handling

**Technology Used**

- FastAPI
- Uvicorn
- Pydantic

---

## 3️⃣ AI Recommendation Engine

The recommendation engine analyzes resume content using semantic similarity instead of simple keyword matching.

The uploaded resume is converted into embeddings using MiniLM and compared with thousands of resumes stored in the FAISS vector database.

### Responsibilities

- Resume Embedding
- Semantic Similarity Search
- Job Role Prediction

**Technology Used**

- Sentence Transformers (MiniLM)
- FAISS
- NumPy

---

## 4️⃣ Live Job Recommendation Module

After predicting the most suitable job roles, the system automatically searches current job openings using the JSearch API.

Users receive AI recommendations along with live job opportunities.

### Responsibilities

- Search Current Jobs
- Format Job Results
- Return Job Information

**Technology Used**

- RapidAPI
- JSearch API
- Requests Library

---

# ⚙️ Technology Stack

| Category | Technology |
|-----------|------------|
| Frontend | React + Vite |
| Backend | FastAPI |
| Programming Language | Python |
| Machine Learning | Sentence Transformers |
| Embedding Model | MiniLM |
| Similarity Search | FAISS |
| Live Jobs API | RapidAPI (JSearch) |
| HTTP Client | Axios |
| Deployment (Frontend) | Vercel |
| Deployment (Backend) | Railway |
| Version Control | Git + GitHub |

---

# 📂 Project Structure

```text
Resume_Job_Recommendation_Application
│
├── backend
│   ├── app
│   │   ├── main.py
│   │   ├── predictor.py
│   │   ├── recommendation.py
│   │   ├── ocr.py
│   │   ├── job_api.py
│   │   ├── job_formatter.py
│   │   └── uploads/
│   │
│   ├── models/
│   ├── requirements.txt
│   └── Procfile
│
├── frontend
│   ├── src
│   │   ├── components
│   │   ├── services
│   │   ├── assets
│   │   └── App.jsx
│   │
│   ├── public
│   ├── package.json
│   └── vite.config.js
│
├── docs
│   ├── system_architecture.png
│   ├── workflow.png
│   └── screenshots
│
└── README.md
```

---

# 🌐 API Endpoints

| Method | Endpoint | Description |
|----------|----------------|--------------------------------|
| GET | `/` | Health Check API |
| POST | `/predict` | Analyze Resume & Recommend Job Roles |
| POST | `/live-jobs` | Fetch Real-Time Job Recommendations |

---

# 🔒 File Validation

The application currently supports:

- ✅ PDF (.pdf)
- ✅ DOCX (.docx)

Maximum Upload Size:

```text
10 MB
```

---

# 📱 Responsive Design

The application is fully responsive and optimized for multiple devices.

Supported Platforms:

- Desktop
- Laptop
- Tablet
- Mobile Devices

Additional Mobile Features:

- Smooth Auto Scroll
- AI Loading Animation
- Responsive Recommendation Panel
- Responsive Live Job Cards

---

# 🚀 Deployment Architecture

```text
React Frontend
      │
      ▼
Vercel
      │
 HTTPS API
      │
      ▼
FastAPI Backend
      │
      ▼
Railway
      │
      ├──────────────► MiniLM Model
      │
      ├──────────────► FAISS Index
      │
      └──────────────► RapidAPI (JSearch)
```



# 📊 Chapter 3 – Dataset & Data Preparation

The performance of any AI system depends heavily on the quality of its dataset. Instead of using a preprocessed text dataset, this project builds a custom resume dataset by extracting text from resume images, cleaning the extracted data, and preparing it for semantic similarity search.

---

# 📂 Dataset Source

The original dataset consists of thousands of resume images collected from Kaggle.

Each resume was stored as an image rather than plain text, requiring an OCR pipeline to convert the images into machine-readable text.

---

# 🔄 Dataset Preparation Pipeline

The dataset preparation process follows the workflow below.

```text
Resume Images
        │
        ▼
OCR Text Extraction
        │
        ▼
Extract Resume Text
        │
        ▼
Create CSV Dataset
        │
        ▼
Data Cleaning
        │
        ▼
Duplicate Removal
        │
        ▼
Remove Invalid Resumes
        │
        ▼
Final Clean Dataset
        │
        ▼
Semantic Embedding Generation
        │
        ▼
FAISS Index Creation
```

---

# 📝 OCR Text Extraction

Since the original dataset contained resume images, Optical Character Recognition (OCR) was used to extract text.

Each image was processed individually, and the extracted text was stored in a structured CSV file.

The extracted dataset contains:

- Resume Text
- Resume Image Name
- Job Role Label

---

# 🧹 Data Cleaning

After OCR extraction, several preprocessing steps were performed to improve dataset quality.

Cleaning operations included:

- Removing duplicate resumes
- Removing empty resumes
- Removing resumes with very little text
- Removing corrupted OCR outputs
- Standardizing text formatting
- Resetting dataset indexing

These steps significantly improved the quality of semantic embeddings generated later.

---

# 🚫 Duplicate Removal

Many resumes in the original dataset were duplicated.

Duplicate entries were removed using the extracted resume text, ensuring that identical resumes appeared only once.

This reduced unnecessary bias during similarity search.

---

# 📏 Resume Length Filtering

Very small resumes usually contain insufficient information for semantic comparison.

To improve recommendation quality, resumes containing fewer than **30 words** were removed from the dataset.

This ensured that only meaningful resumes were included during embedding generation.

---

# 📈 Final Dataset

After preprocessing, the final dataset contains:

| Property | Value |
|-----------|-------|
| Dataset Type | Resume Text Dataset |
| Original Format | Resume Images |
| OCR Engine | EasyOCR |
| Final Dataset Format | CSV |
| Final Records | ~7000+ Resumes |
| Supported Language | English |

---

# 🧠 Why Build a Custom Dataset?

Most publicly available resume datasets already contain clean text.

However, real-world resumes are usually uploaded as:

- PDF Files
- DOCX Files
- Images

Building a custom OCR pipeline makes the application more practical and closer to real-world deployment.

---

# 🔍 Dataset Features

Each processed resume contains rich textual information such as:

- Technical Skills
- Programming Languages
- Education
- Certifications
- Work Experience
- Projects
- Tools & Technologies
- Soft Skills

These features are later converted into semantic embeddings for similarity search.

---

# ⚙️ Data Preprocessing Steps

Before generating embeddings, every resume goes through the following preprocessing pipeline:

```text
Resume Text
      │
      ▼
Lowercase Conversion
      │
      ▼
Whitespace Cleaning
      │
      ▼
Remove Invalid Characters
      │
      ▼
Word Count Validation
      │
      ▼
Final Resume Text
```

---

# 📌 Why Dataset Quality Matters

Semantic similarity models such as MiniLM rely on high-quality textual data.

Poor-quality resumes can lead to:

- Incorrect embeddings
- Poor similarity matching
- Incorrect job recommendations

Therefore, dataset cleaning plays a critical role in improving recommendation accuracy and overall application performance.

---

# ✅ Outcome

The final cleaned dataset provides a strong foundation for semantic similarity search using MiniLM and FAISS.

This dataset enables the system to recommend job roles based on the meaning and context of resume content rather than relying on simple keyword matching.



# 🧠 Chapter 4 – LLM-Based Resume Annotation & Structured Dataset Generation

One of the biggest challenges in building an intelligent resume recommendation system is the lack of structured resume datasets. Most publicly available resume datasets either contain only raw resume text or predefined labels, making them unsuitable for semantic recommendation systems.

To overcome this limitation, a custom **Large Language Model (LLM) annotation pipeline** was developed to automatically convert raw resume text into structured information.

Instead of manually labeling thousands of resumes, the system uses an LLM to extract important information such as technical skills, education, work experience, certifications, projects, and predicted job roles.

This structured dataset later becomes the foundation of the recommendation engine.

---

# 🎯 Why Use an LLM?

Raw resume text contains unstructured information.

Example:

```text
John Doe
Bachelor of Technology
Python
Machine Learning
FastAPI
SQL
TensorFlow
```

Although humans can easily understand this information, machine learning models require structured data.

The LLM automatically transforms raw resume text into a structured JSON format that can be processed efficiently.

---

# 🔄 Annotation Pipeline

```text
Resume Images
        │
        ▼
EasyOCR
        │
        ▼
Raw Resume Text
        │
        ▼
LLM Annotation
        │
        ▼
Structured JSON
        │
        ▼
CSV Dataset
        │
        ▼
Recommendation Engine
```

---

# 🤖 LLM Models Used

During development, two different Large Language Models were used.

## 1️⃣ Google Gemini API

Initially, Google's Gemini API was selected because of its strong reasoning capabilities and high-quality structured output.

Advantages:

- High-quality extraction
- Excellent JSON generation
- Accurate understanding of resume content

However, while processing thousands of resumes, the project encountered API rate limits, making it unsuitable for large-scale dataset annotation.

---

## 2️⃣ Qwen/Qwen3-4B-2507

To overcome the limitations of Gemini, the annotation pipeline was migrated to the **Qwen/Qwen3-4B-2507** model.

Reasons for switching:

- Better scalability
- Suitable for batch processing
- Consistent structured output
- Reduced dependency on strict API rate limits
- Efficient processing of large resume datasets

The migration allowed the project to continue generating structured resume data efficiently.

---

# 📄 Resume Parsing Process

Each resume is processed individually.

Workflow:

```text
Resume Text
        │
        ▼
Prompt Template
        │
        ▼
Qwen LLM
        │
        ▼
Structured JSON
```

The model reads the entire resume and identifies meaningful information instead of relying on keyword matching.

---

# 📌 Information Extracted

The LLM extracts multiple attributes from every resume.

These include:

- Job Role
- Technical Skills
- Programming Languages
- Education
- Certifications
- Work Experience
- Projects
- Soft Skills
- Tools & Technologies
- Experience Level

This structured information significantly improves the quality of semantic recommendations.

---

# 🧾 JSON Output Structure

Each processed resume is converted into a structured JSON format.

Example:

```json
{
  "job_role": "Backend Developer",
  "skills": [
    "Python",
    "FastAPI",
    "SQL",
    "Docker"
  ],
  "education": "Bachelor of Technology",
  "experience_level": "Fresher",
  "certifications": [
    "AWS Cloud Practitioner"
  ],
  "projects": [
    "Resume Recommendation System"
  ]
}
```

This structured output is later stored inside the processed dataset.

---

# ⚙️ Local Annotation Environment

The annotation pipeline was executed locally to process thousands of resumes efficiently.

## Development Environment

- Python
- VS Code
- Virtual Environment (venv)
- Pandas
- Requests
- tqdm
- dotenv

The project used environment variables to securely manage API credentials during development.

---

# 📁 Dataset Generation Workflow

```text
Raw Resume CSV
        │
        ▼
Read Resume
        │
        ▼
Send Prompt to LLM
        │
        ▼
Receive JSON Response
        │
        ▼
Validate Output
        │
        ▼
Append to Dataset
        │
        ▼
Save CSV
```

This workflow continues until all resumes have been processed.

---

# 🛡️ Error Handling

While generating the dataset, several validation mechanisms were implemented.

The pipeline handles:

- Empty resumes
- Invalid OCR output
- LLM response errors
- JSON parsing failures
- Missing fields
- API exceptions
- Retry attempts

These checks ensured reliable dataset generation even when processing thousands of resumes.

---

# 🚀 Benefits of LLM Annotation

Compared to manual labeling, the automated annotation pipeline offers several advantages:

- Automatic resume understanding
- Consistent structured output
- Faster dataset creation
- Reduced manual effort
- Scalable processing
- Improved recommendation quality

---

# 📊 Technologies Used

| Component | Technology |
|------------|------------|
| OCR | EasyOCR |
| Initial LLM | Google Gemini API |
| Final LLM | Qwen/Qwen3-4B-2507 |
| Language | Python |
| Data Processing | Pandas |
| Progress Tracking | tqdm |
| Environment Variables | python-dotenv |
| Development Environment | VS Code |

---

# 💡 Why This Approach?

Traditional resume datasets require extensive manual labeling, which is time-consuming and difficult to scale.

By combining OCR with Large Language Models, this project automatically transforms raw resume text into structured information suitable for semantic recommendation systems.

This automated annotation pipeline not only accelerates dataset preparation but also creates richer and more meaningful resume representations for downstream AI tasks such as job recommendation, skill analysis, and semantic similarity search.



# 🤖 Chapter 5 – AI Recommendation Engine

The AI Recommendation Engine is the core component of this project. Instead of using a traditional machine learning classifier, the system relies on **semantic similarity search** to recommend suitable job roles.

The uploaded resume is converted into a numerical vector representation (embedding) using the **Sentence Transformer MiniLM model**. These embeddings are then compared with thousands of resumes stored in a **FAISS Vector Database** to identify the most similar resumes and recommend appropriate job roles.

This approach focuses on the meaning and context of resume content rather than exact keyword matching.

---

# 🧠 AI Recommendation Workflow

```text
Resume Upload
        │
        ▼
Resume Text Extraction
        │
        ▼
Sentence Transformer (MiniLM)
        │
        ▼
Generate Resume Embedding
        │
        ▼
FAISS Similarity Search
        │
        ▼
Find Top Similar Resumes
        │
        ▼
Extract Job Roles
        │
        ▼
Top AI Recommendations
```

---

# 🔹 Why Sentence Transformers?

Traditional keyword matching systems often fail when different words describe the same skill.

Example:

Resume A

Python, Flask, SQL

Resume B

Python, FastAPI, Database

Although the wording is different, both resumes represent Backend Development skills.

Sentence Transformers understand the **semantic meaning** of text instead of simply matching identical words.

This significantly improves recommendation quality.

---

# 🔹 MiniLM Model

This project uses the **all-MiniLM-L6-v2** Sentence Transformer model.

MiniLM converts each resume into a fixed-length embedding vector that captures the semantic meaning of the resume.

### Advantages

- Lightweight
- Fast inference
- High semantic understanding
- Excellent performance for similarity search
- Suitable for deployment

---

# 🔹 Resume Embeddings

Every resume is transformed into a numerical vector called an **embedding**.

Example

```text
Resume Text
        │
        ▼
Sentence Transformer
        │
        ▼
Embedding Vector
```

Example Vector

```text
[-0.34,
 0.18,
 0.61,
 ...
 384 Dimensions]
```

These embeddings preserve the meaning of the resume instead of simply storing words.

---

# 🔹 Why FAISS?

Comparing one resume against thousands of resumes directly would be computationally expensive.

FAISS (Facebook AI Similarity Search) provides extremely fast nearest-neighbor search for high-dimensional vectors.

Instead of scanning every resume sequentially, FAISS quickly finds the most similar embeddings.

Benefits include:

- High-speed similarity search
- Scalable to large datasets
- Memory efficient
- Optimized for vector search

---

# 🔄 Recommendation Process

The recommendation engine follows these steps:

```text
User Resume
      │
      ▼
Generate Embedding
      │
      ▼
Search FAISS Index
      │
      ▼
Retrieve Top Similar Resumes
      │
      ▼
Extract Job Roles
      │
      ▼
Rank Recommendations
      │
      ▼
Return Top Job Roles
```

---

# 🎯 Recommendation Logic

The system performs semantic matching rather than classification.

Process:

1. Convert uploaded resume into an embedding.
2. Search the FAISS vector index.
3. Retrieve the most similar resumes.
4. Extract job roles from similar resumes.
5. Rank job roles based on similarity.
6. Return the top recommendations.

---

# 📈 Why Semantic Similarity Instead of Classification?

Many resume classification models require thousands of labeled examples for every job role.

In contrast, semantic similarity offers several advantages:

- Better generalization
- Easier to extend
- Faster inference
- Handles unseen resumes effectively
- Understands contextual meaning

This makes it more suitable for real-world resume recommendation systems.

---

# ⚡ Performance Pipeline

```text
Upload Resume
        │
        ▼
OCR / Text Extraction
        │
        ▼
MiniLM Embedding Generation
        │
        ▼
FAISS Similarity Search
        │
        ▼
Top Job Recommendations
        │
        ▼
Real-Time Job Search
```

---

# 🏆 Advantages of the AI Engine

- Semantic understanding of resumes
- Fast recommendation generation
- Context-aware matching
- Scalable architecture
- Lightweight deployment
- High-quality recommendations

---

# 📌 AI Technologies Used

| Component | Technology |
|------------|------------|
| NLP Model | Sentence Transformers |
| Embedding Model | all-MiniLM-L6-v2 |
| Vector Search | FAISS |
| Programming Language | Python |
| Backend | FastAPI |
| Recommendation Technique | Semantic Similarity Search |

---

# 💡 Why This Architecture?

Instead of relying on keyword matching or traditional machine learning classification, this project combines **Sentence Transformers** with **FAISS** to build a scalable semantic recommendation engine.

This architecture enables the application to understand the meaning of resumes, identify similar profiles efficiently, and recommend relevant job roles with high speed and accuracy. It also provides a flexible foundation for future enhancements such as ATS scoring, skill-gap analysis, and LLM-powered resume feedback.



# ⚙️ Chapter 6 – Backend Development

The backend serves as the core processing unit of the application. It manages resume uploads, extracts text from resumes, communicates with the AI recommendation engine, retrieves real-time job opportunities, and sends the processed results back to the frontend.

The backend is developed using **FastAPI**, a modern high-performance Python web framework designed for building scalable RESTful APIs.

---

# 🏗️ Backend Architecture

```text
React Frontend
        │
        ▼
FastAPI Backend
        │
        ├────────────► Resume Upload
        │
        ├────────────► OCR Processing
        │
        ├────────────► AI Recommendation Engine
        │
        ├────────────► Live Job Search
        │
        └────────────► JSON Response
```

---

# 🚀 Why FastAPI?

FastAPI was selected because it provides excellent performance while keeping the backend lightweight and easy to maintain.

### Advantages

- High Performance
- Automatic API Documentation
- Built-in Data Validation
- Easy File Upload Handling
- REST API Support
- Asynchronous Processing
- Modern Python Framework

---

# 📂 Backend Project Structure

```text
backend
│
├── app
│   ├── main.py
│   ├── predictor.py
│   ├── recommendation.py
│   ├── ocr.py
│   ├── job_api.py
│   ├── job_formatter.py
│   ├── uploads
│   └── __init__.py
│
├── models
│
├── requirements.txt
│
└── Procfile
```

---

# 📌 Backend Modules

## main.py

Acts as the main entry point of the FastAPI application.

Responsibilities:

- Initialize FastAPI
- Configure CORS
- Register API routes
- Load AI model
- Handle requests
- Return responses

---

## predictor.py

Implements the AI recommendation engine.

Responsibilities:

- Load MiniLM Model
- Load FAISS Index
- Generate Embeddings
- Search Similar Resumes
- Return Recommended Job Roles

---

## ocr.py

Responsible for extracting text from uploaded resumes.

Supported formats:

- PDF
- DOCX

Responsibilities:

- Read uploaded file
- Extract resume text
- Return clean text

---

## job_api.py

Communicates with the external Job Search API.

Responsibilities:

- Search live jobs
- Receive API response
- Parse job information
- Return formatted jobs

---

## job_formatter.py

Formats predicted job roles before searching live jobs.

Example:

```text
Machine Learning Engineer

↓

Machine Learning Engineer Jobs
```

This improves search quality and relevance.

---

# 🌐 REST API Endpoints

## Home API

```http
GET /
```

Purpose

Checks whether the backend server is running.

Example Response

```json
{
    "message": "Resume Recommendation API Running Successfully"
}
```

---

## Resume Prediction API

```http
POST /predict
```

Purpose

Uploads a resume and returns AI-generated job role recommendations.

Input

- PDF Resume
- DOCX Resume

Output

```json
{
    "recommendations": [
        {
            "job_role": "Backend Developer",
            "score": 0.94
        }
    ]
}
```

---

## Live Job Recommendation API

```http
POST /live-jobs
```

Purpose

Fetches real-time job opportunities using the predicted job roles.

Input

```json
{
    "recommendations":[
        {
            "job_role":"Backend Developer"
        }
    ]
}
```

Output

```json
{
    "success": true,
    "jobs":[
        {
            "company":"Google",
            "job_title":"Backend Developer",
            "location":"California"
        }
    ]
}
```

---

# 📄 Resume Processing Workflow

```text
User Upload Resume
        │
        ▼
Receive File
        │
        ▼
Validate Extension
        │
        ▼
Save Temporary File
        │
        ▼
Extract Resume Text
        │
        ▼
Generate AI Recommendation
        │
        ▼
Return Prediction
        │
        ▼
Delete Temporary File
```

---

# 🔒 File Validation

The backend validates every uploaded resume before processing.

Supported formats:

- PDF
- DOCX

Maximum upload size:

```text
10 MB
```

If validation fails, the API returns an appropriate error message.

---

# 🛡️ Error Handling

The backend includes exception handling for multiple scenarios.

Examples include:

- Invalid file format
- Empty resume
- OCR failure
- AI prediction failure
- External API failure
- Internal server errors

Meaningful HTTP responses are returned to the frontend to improve the user experience.

---

# 🔄 Backend Processing Flow

```text
Request Received
        │
        ▼
Validate Request
        │
        ▼
Process Resume
        │
        ▼
Predict Job Roles
        │
        ▼
Search Live Jobs
        │
        ▼
Return JSON Response
```

---

# ⚡ Performance Optimization

Several techniques were used to improve backend performance.

- MiniLM model loaded only once during startup
- FAISS index loaded into memory
- Resume database loaded once
- Temporary files automatically removed
- FastAPI asynchronous request handling
- Lightweight REST architecture

These optimizations reduce response time and improve scalability.

---

# 📦 Backend Dependencies

The backend uses the following major Python libraries.

| Library | Purpose |
|----------|----------|
| FastAPI | REST API Framework |
| Uvicorn | ASGI Server |
| Sentence Transformers | Resume Embeddings |
| FAISS | Similarity Search |
| Pandas | Data Processing |
| NumPy | Numerical Operations |
| Requests | API Communication |
| python-dotenv | Environment Variables |
| Pydantic | Data Validation |
| shutil | File Handling |
| uuid | Unique File Names |

---

# 💡 Backend Summary

The backend acts as the intelligence layer of the application by integrating OCR, AI-based recommendation, and real-time job search into a single REST API service.

Its modular architecture ensures scalability, maintainability, and efficient communication between the frontend, AI recommendation engine, and external job search APIs.


# 🎨 Chapter 7 – Frontend Development

The frontend provides a modern, responsive, and user-friendly interface that allows users to upload resumes, receive AI-generated job recommendations, and explore real-time job opportunities.

The frontend is developed using **React** and **Vite**, enabling fast rendering, modular development, and an interactive user experience.

---

# 🏗️ Frontend Architecture

```text
User
   │
   ▼
React Application
   │
   ├────────────► Upload Resume
   │
   ├────────────► Validate File
   │
   ├────────────► Call FastAPI
   │
   ├────────────► Display AI Recommendation
   │
   └────────────► Display Live Jobs
```

---

# 🚀 Why React?

React was selected because it simplifies the development of interactive user interfaces through reusable components and efficient state management.

### Advantages

- Component-Based Architecture
- Fast Rendering
- Reusable Components
- Responsive UI
- Easy API Integration
- Efficient State Management

---

# ⚡ Why Vite?

Vite was chosen as the build tool because of its speed and lightweight development environment.

Advantages:

- Extremely Fast Development Server
- Instant Hot Reload
- Optimized Production Build
- Modern JavaScript Support

---

# 📂 Frontend Folder Structure

```text
frontend
│
├── src
│   ├── assets
│   ├── components
│   │
│   ├── Loader
│   ├── LiveJobs
│   ├── RecommendationPanel
│   ├── UploadResume
│   │
│   ├── services
│   │   ├── api.js
│   │   └── resumeService.js
│   │
│   ├── App.jsx
│   └── main.jsx
│
├── public
│
├── package.json
│
└── vite.config.js
```

---

# 🧩 Frontend Components

## UploadResume Component

This component is responsible for:

- Resume Upload
- File Validation
- Calling Backend APIs
- Displaying Loading Animation
- Mobile Auto Scroll

---

## RecommendationPanel Component

Displays the AI-generated job role recommendations returned by the backend.

Responsibilities:

- Display Recommended Roles
- Display Similarity Scores
- Responsive Layout

---

## LiveJobs Component

Displays current job openings related to the predicted job roles.

Information displayed includes:

- Company Name
- Job Title
- Location
- Employment Type
- Salary (if available)
- Apply Link

---

## Loader Component

Provides visual feedback while the application searches for live jobs.

This improves the overall user experience during API requests.

---

# 🔄 Frontend Workflow

```text
Upload Resume
        │
        ▼
File Validation
        │
        ▼
POST /predict
        │
        ▼
Display AI Recommendation
        │
        ▼
POST /live-jobs
        │
        ▼
Display Live Jobs
```

---

# 📄 Resume Upload

The frontend supports uploading resumes in:

- PDF
- DOCX

Validation includes:

- Supported File Types
- Maximum File Size (10 MB)
- Empty File Detection

---

# 🔄 API Communication

Axios is used to communicate with the FastAPI backend.

Main API calls include:

```text
POST /predict
```

Returns AI recommendations.

```text
POST /live-jobs
```

Returns real-time job opportunities.

---

# 🎯 User Experience Improvements

Several features were implemented to improve usability.

## 🤖 AI Loading Animation

Since AI prediction requires several seconds on the deployed server, an animated loading message was introduced.

Example:

```text
🤖 AI is analyzing your resume.
🤖 AI is analyzing your resume..
🤖 AI is analyzing your resume...
```

After prediction completes, the message changes automatically.

```text
🔍 Finding live jobs.
🔍 Finding live jobs..
🔍 Finding live jobs...
```

This provides continuous feedback while the application processes requests.

---

## 📱 Mobile Auto Scroll

On mobile devices, recommendation cards appear below the upload section.

To improve usability, the application automatically scrolls to the recommendation section after AI prediction completes.

Desktop users retain the original behavior without automatic scrolling.

---

## ⏳ Live Job Loader

Live job recommendations are fetched after AI prediction.

A dedicated loading component is displayed while jobs are being retrieved.

This allows users to immediately view AI recommendations while live jobs continue loading in the background.

---

# 📱 Responsive Design

The frontend is fully responsive and optimized for multiple screen sizes.

Supported Devices:

- Desktop
- Laptop
- Tablet
- Mobile

Responsive features include:

- Flexible Layout
- Responsive Cards
- Mobile Auto Scroll
- Responsive Buttons
- Mobile-Friendly Typography

---

# 🎨 UI Design Principles

The interface was designed with simplicity and usability in mind.

Key design goals:

- Clean Interface
- Easy Navigation
- Minimal Clicks
- Modern Appearance
- Fast Interaction
- Responsive Experience

---

# 📦 Frontend Libraries

| Library | Purpose |
|----------|----------|
| React | User Interface |
| Vite | Build Tool |
| Axios | HTTP Requests |
| CSS | Styling |

---

# 💡 Frontend Summary

The frontend serves as the interaction layer between users and the AI backend.

It enables users to upload resumes, receive intelligent job recommendations, explore real-time job opportunities, and interact with the application through a clean, responsive, and user-friendly interface.

Special attention was given to user experience through loading animations, responsive design, and automatic mobile scrolling, making the application intuitive across both desktop and mobile devices.



# ☁️ Chapter 8 – Deployment & DevOps

After successfully developing and testing the application locally, the next step was deploying it to the cloud so users could access it from anywhere.

The application follows a distributed deployment architecture where the frontend and backend are hosted on separate cloud platforms.

---

# 🏗️ Production Architecture

```text
                     User
                       │
                       ▼
            React Frontend (Vercel)
                       │
               HTTPS API Requests
                       │
                       ▼
          FastAPI Backend (Railway)
                       │
      ┌────────────────┼────────────────┐
      │                │                │
      ▼                ▼                ▼
 MiniLM Model      FAISS Index     RapidAPI
                                   (JSearch)
```

---

# 🚀 Deployment Strategy

The application was deployed using two different cloud platforms.

| Component | Platform |
|------------|----------|
| Frontend | Vercel |
| Backend | Railway |
| Source Code | GitHub |

Separating the frontend and backend provides better scalability, easier maintenance, and independent deployments.

---

# 📂 Version Control

Git and GitHub were used throughout the development process.

The repository stores:

- Frontend Source Code
- Backend Source Code
- AI Recommendation Engine
- Documentation
- Deployment Configuration

GitHub also provides automatic deployment integration with both Railway and Vercel.

---

# ⚛️ Frontend Deployment (Vercel)

The React application was deployed using Vercel.

Deployment Process:

```text
GitHub
    │
    ▼
Vercel
    │
Automatic Build
    │
    ▼
Production Website
```

### Deployment Steps

1. Connect GitHub Repository
2. Select Frontend Directory
3. Install Dependencies
4. Build React Application
5. Deploy Automatically

Every push to the main branch automatically triggers a new deployment.

---

# ⚙️ Backend Deployment (Railway)

The FastAPI backend was deployed using Railway.

Deployment Workflow

```text
GitHub
     │
     ▼
Railway
     │
Install Requirements
     │
     ▼
Load AI Model
     │
     ▼
Start FastAPI Server
```

Railway automatically redeploys the backend whenever changes are pushed to GitHub.

---

# 🔐 Environment Variables

Sensitive information such as API keys should never be stored directly in source code.

Railway Variables were used to securely store:

```text
RAPIDAPI_KEY
```

The backend reads the environment variable at runtime using:

```python
os.getenv("RAPIDAPI_KEY")
```

This improves security and simplifies deployment.

---

# 🔄 Continuous Deployment (CI/CD)

Every code update follows the same deployment workflow.

```text
Developer
      │
      ▼
Git Commit
      │
      ▼
GitHub Push
      │
      ├────────────► Railway Deploy
      │
      └────────────► Vercel Deploy
```

This automated deployment pipeline ensures that the latest version of the application is always available without manual server updates.

---

# 🔥 Deployment Challenges

During deployment, several real-world challenges were encountered and resolved.

## Challenge 1 – Render Out of Memory

Initially, the backend was deployed on Render.

However, loading the MiniLM model and FAISS index exceeded the free memory limit, causing deployment failures.

### Solution

The backend was migrated to Railway, which successfully handled the application's memory requirements.

---

## Challenge 2 – CORS Configuration

The React frontend and FastAPI backend were hosted on different domains.

Initially, browsers blocked API communication because Cross-Origin Resource Sharing (CORS) was not configured correctly.

### Solution

FastAPI's `CORSMiddleware` was configured to allow requests from the Vercel frontend.

---

## Challenge 3 – Environment Variables

The RapidAPI key worked locally using a `.env` file but initially failed after deployment because the production server did not have the required environment variable.

### Solution

The API key was added through Railway Variables, allowing the backend to access it securely during runtime.

---

## Challenge 4 – Frontend API Connection

During development, the frontend communicated with:

```text
http://127.0.0.1:8000
```

After deployment, this prevented the production frontend from reaching the backend.

### Solution

The API base URL was updated to the Railway backend URL.

---

## Challenge 5 – Mobile User Experience

On mobile devices, AI recommendations appeared below the visible screen after analysis completed.

### Solution

Automatic smooth scrolling was implemented to move users directly to the recommendation section after AI prediction.

---

## Challenge 6 – Loading Feedback

The deployed backend required several seconds to analyze resumes and fetch live jobs.

Without visual feedback, users might think the application had stopped responding.

### Solution

Two animated loading stages were introduced:

- 🤖 AI is analyzing your resume...
- 🔍 Finding live jobs...

This significantly improved the overall user experience.

---

# 📊 Deployment Advantages

The selected deployment architecture provides several benefits.

- Independent frontend and backend deployment
- Automatic deployment from GitHub
- Secure environment variable management
- Scalable cloud infrastructure
- Easy maintenance
- Faster development workflow

---

# 🔒 Security Considerations

Several security measures were implemented.

- API keys stored as environment variables
- Temporary uploaded files automatically deleted
- File type validation
- Maximum upload size restriction
- Backend request validation

---

# 📈 Production Workflow

```text
User Upload Resume
        │
        ▼
React Frontend (Vercel)
        │
HTTPS Request
        │
        ▼
FastAPI Backend (Railway)
        │
        ▼
Resume Processing
        │
        ▼
MiniLM Recommendation
        │
        ▼
RapidAPI Job Search
        │
        ▼
Return Results
        │
        ▼
Display Recommendations
```

---

# 💡 Deployment Summary

The application was successfully deployed using a modern cloud architecture with **Vercel** for the frontend and **Railway** for the backend.

Throughout deployment, multiple production-level challenges—including memory limitations, CORS configuration, environment variables, API connectivity, and mobile user experience—were identified and resolved.

The final deployment provides a stable, scalable, and user-friendly AI-powered web application capable of analyzing resumes and delivering real-time job recommendations.



# 🛠️ Chapter 9 – Challenges Faced & Solutions

Building a production-ready AI application involved several technical challenges across machine learning, backend development, frontend integration, cloud deployment, and user experience.

This chapter summarizes the major challenges encountered during development and the solutions implemented to overcome them.

---

# 🔍 Challenge 1 – Resume Dataset Availability

## Problem

Most publicly available resume datasets already contained processed labels or only raw resume text, making them unsuitable for semantic recommendation.

Additionally, many datasets did not represent real-world uploaded resumes.

## Solution

A custom dataset preparation pipeline was developed.

Workflow:

```text
Resume Images
      │
      ▼
EasyOCR
      │
      ▼
Resume Text
      │
      ▼
LLM Annotation
      │
      ▼
Structured Dataset
```

This produced a realistic dataset suitable for semantic similarity search.

---

# 🤖 Challenge 2 – Manual Resume Labeling

## Problem

Thousands of resumes required structured labels such as:

- Skills
- Education
- Experience
- Certifications
- Job Role

Manual annotation would have required significant time and effort.

## Solution

A Large Language Model (LLM) was integrated to automate the annotation process.

Initially:

- Google Gemini API

Later migrated to:

- Qwen/Qwen3-4B-2507

The LLM automatically generated structured JSON for every resume.

---

# ⚠️ Challenge 3 – Gemini API Rate Limits

## Problem

Google Gemini provided high-quality structured responses but imposed API rate limits, preventing continuous processing of thousands of resumes.

## Solution

The annotation pipeline was migrated to the **Qwen/Qwen3-4B-2507** model, enabling reliable large-scale resume annotation.

---

# 🧠 Challenge 4 – Selecting the Recommendation Approach

## Problem

A traditional machine learning classifier would require a large, balanced, and accurately labeled dataset for every job role.

This approach would be difficult to scale.

## Solution

Instead of classification, semantic similarity search was adopted.

Pipeline:

```text
Resume
     │
     ▼
MiniLM Embedding
     │
     ▼
FAISS Search
     │
     ▼
Top Similar Resumes
     │
     ▼
Recommended Job Roles
```

This approach offers better scalability and contextual understanding.

---

# 🚀 Challenge 5 – Model Loading Performance

## Problem

Loading the MiniLM model and FAISS index for every request significantly increased response time.

## Solution

Both the MiniLM model and FAISS index are loaded once during application startup and reused for all incoming requests.

This reduced prediction latency and improved backend performance.

---

# 📄 Challenge 6 – Resume Upload Validation

## Problem

Users could upload unsupported file formats or extremely large files, leading to processing failures.

## Solution

Backend validation was implemented to:

- Accept only PDF and DOCX files
- Restrict uploads to 10 MB
- Return meaningful error messages

---

# 🌍 Challenge 7 – Live Job Integration

## Problem

AI-generated job recommendations alone were not sufficient.

Users still had to manually search multiple job portals.

## Solution

RapidAPI's JSearch API was integrated to automatically retrieve live job opportunities based on the predicted job roles.

This became the primary unique feature of the application.

---

# ☁️ Challenge 8 – Render Deployment Failure

## Problem

The initial deployment used Render.

However, the MiniLM model and FAISS index exceeded the available memory limit, causing deployment failures.

## Solution

The backend was migrated to Railway.

Railway successfully handled the application's memory requirements and provided stable deployment.

---

# 🔐 Challenge 9 – Environment Variables

## Problem

The RapidAPI key worked correctly during local development but failed after deployment because production servers do not automatically use local `.env` files.

## Solution

Railway Variables were configured to securely store the API key.

The backend retrieves the key at runtime using environment variables.

---

# 🌐 Challenge 10 – CORS Configuration

## Problem

The frontend and backend were hosted on different domains.

Browsers blocked API communication because Cross-Origin Resource Sharing (CORS) was not configured correctly.

## Solution

FastAPI's CORSMiddleware was configured to allow requests from the deployed Vercel frontend.

---

# 🔗 Challenge 11 – Frontend API Connection

## Problem

During development, API requests pointed to:

```text
http://127.0.0.1:8000
```

After deployment, the production frontend could no longer communicate with the backend.

## Solution

The frontend API configuration was updated to use the Railway backend URL.

---

# 📱 Challenge 12 – Mobile User Experience

## Problem

On smaller screens, recommendation cards appeared below the visible viewport.

Users had to scroll manually after every prediction.

## Solution

Automatic smooth scrolling was introduced for mobile devices, directing users to the recommendation section immediately after AI prediction.

Desktop behavior remained unchanged.

---

# ⏳ Challenge 13 – Loading Feedback

## Problem

Cloud deployment increased response time.

Without feedback, users could assume the application had stopped responding.

## Solution

Animated loading messages were implemented.

Example:

```text
🤖 AI is analyzing your resume.
🤖 AI is analyzing your resume..
🤖 AI is analyzing your resume...

↓

🔍 Finding live jobs.
🔍 Finding live jobs..
🔍 Finding live jobs...
```

This significantly improved user experience.

---

# 📊 Challenge 14 – Responsive Design

## Problem

The application needed to provide a consistent experience across desktops, tablets, and smartphones.

## Solution

Responsive layouts, flexible cards, adaptive typography, and mobile-specific improvements were implemented to ensure usability on different devices.

---

# 🏆 Key Lessons Learned

Developing this project provided practical experience in:

- Full-Stack Web Development
- Artificial Intelligence
- Natural Language Processing
- OCR
- Semantic Similarity Search
- Large Language Models
- REST API Development
- Cloud Deployment
- Git & GitHub
- Debugging Production Issues
- Responsive UI Design
- User Experience Optimization

---

# 💡 Chapter Summary

Throughout the development process, multiple technical challenges were encountered across data preparation, AI modeling, backend development, frontend integration, deployment, and production environments.

Each challenge was analyzed systematically, and practical solutions were implemented to improve the application's reliability, scalability, and user experience.

These experiences not only strengthened the final application but also provided valuable hands-on knowledge of building and deploying real-world AI-powered software systems.



# 🚀 Chapter 10 – Future Enhancements

The current version of the AI Resume Analyzer successfully performs resume analysis, semantic job role recommendation, and real-time job searching. However, there are several opportunities to further enhance the system and improve its capabilities.

Future versions of the application will focus on providing more personalized career guidance, richer AI-powered insights, and a complete job search experience.

---

# 📈 Planned Features

The following features are planned for future releases.

---

## ⭐ ATS Resume Score

An Applicant Tracking System (ATS) score will be generated to evaluate how well a resume matches modern recruitment systems.

The ATS score may consider factors such as:

- Resume Structure
- Keyword Relevance
- Skills Matching
- Formatting
- Experience
- Education

This feature will help users optimize their resumes before applying for jobs.

---

## 💡 AI Resume Improvement Suggestions

The application will provide personalized suggestions for improving resumes.

Example suggestions:

- Missing Technical Skills
- Better Resume Summary
- Improved Project Descriptions
- Stronger Action Verbs
- Grammar Improvements
- Resume Formatting Tips

These recommendations will be generated using Large Language Models (LLMs).

---

## 🎯 Skill Gap Analysis

After predicting suitable job roles, the system will compare the user's skills against the skills required for those roles.

Example:

```text
Recommended Role:
Backend Developer

Your Skills:
✔ Python
✔ SQL
✔ FastAPI

Missing Skills:
✖ Docker
✖ Kubernetes
✖ AWS
```

This will provide users with a clear roadmap for career development.

---

## 📄 Resume PDF Report

Users will be able to download a complete resume analysis report.

The report may include:

- ATS Score
- Recommended Job Roles
- Resume Strengths
- Improvement Suggestions
- Skill Gap Analysis
- Live Job Recommendations

This report can be saved for future reference.

---

## 🔐 User Authentication

Future versions will include user accounts.

Features may include:

- User Registration
- Login
- Password Reset
- Profile Management

This will allow users to securely manage their resume analyses.

---

## 📚 Resume History

Logged-in users will be able to access previously uploaded resumes.

Benefits:

- Compare Resume Versions
- Track Improvements
- View Past Recommendations
- Resume Management

---

## 🌍 Multi-Language Support

The current application focuses on English resumes.

Future versions may support additional languages, enabling a broader range of users to benefit from the system.

---

## 🤖 Advanced LLM Integration

Future releases may integrate more advanced language models to provide:

- Career Guidance
- Interview Preparation
- Resume Rewriting
- Cover Letter Generation
- Personalized Learning Recommendations

This will transform the application into a complete AI-powered career assistant.

---

## 📊 Analytics Dashboard

A personal dashboard may be introduced to provide insights such as:

- Total Resume Uploads
- Previous Recommendations
- Frequently Suggested Job Roles
- Job Application Tracking
- Resume Improvement Progress

---

## 🔔 Job Alerts

Users will be able to subscribe to notifications for new job openings related to their preferred roles.

Possible notification channels include:

- Email
- Mobile Notifications
- Dashboard Alerts

---

## ❤️ Save Favorite Jobs

Users will be able to bookmark interesting job opportunities for later review.

Additional features may include:

- Favorite Jobs
- Applied Jobs
- Application Status Tracking

---

## 🌙 Dark Mode

To improve accessibility and user comfort, a dark mode theme will be introduced.

Users will be able to switch between light and dark themes according to their preference.

---

# 🔮 Long-Term Vision

The long-term goal of this project is to evolve from a resume analyzer into a complete AI-powered career development platform.

The future system will not only analyze resumes but also help users:

- Discover suitable career paths
- Improve their resumes
- Learn missing skills
- Prepare for interviews
- Track job applications
- Receive personalized career guidance

By combining Artificial Intelligence, Natural Language Processing, and real-time job market data, the platform aims to become a comprehensive assistant for students, fresh graduates, and professionals seeking career growth.

---

# 💡 Chapter Summary

The current version demonstrates the core functionality of AI-powered resume analysis and real-time job recommendations. Future enhancements will focus on expanding the platform with advanced AI capabilities, personalized career assistance, user management, and analytics.

These planned improvements will make the application more intelligent, scalable, and valuable for users throughout their career journey.
