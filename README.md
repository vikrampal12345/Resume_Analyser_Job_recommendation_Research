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
