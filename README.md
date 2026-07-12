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
