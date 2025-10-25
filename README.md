
# 🧠 Research AI App – Intelligent Research Dashboard

A modern **AI-powered research assistant** built on the **Azure cloud stack**, designed to help users manage documents, query private data, and generate contextual insights — all in one place.  
This project demonstrates how **Next.js, Azure Functions, and Azure OpenAI** can be combined into a real, production-ready solution.

---

## 🚀 Overview

**Research AI App** is a unified platform for interactive research and document intelligence.  
It allows users to upload, search, and analyze documents using AI, powered entirely by **Azure’s serverless architecture**.

It’s part of a larger exploration into **AI-assisted knowledge management** — showing how intelligent systems can support research workflows while maintaining privacy and scalability.

---

## 🧩 Core Features

1. **Smart Document Management**
   - Upload, categorize, and search research files
   - Automatically extract key details and metadata

2. **AI-Driven Insights**
   - Ask natural-language questions about your data
   - Get contextual answers grounded in your own content

3. **Interactive Dashboard**
   - Clean, responsive interface built with Next.js 16 and Tailwind CSS
   - Real-time updates and API calls via Azure Functions

4. **Private AI Integration**
   - Uses Azure OpenAI for summarization, refinement, and context generation
   - Keeps all data within your Azure environment

5. **Modular Architecture**
   - Frontend: Static Web App (Next.js)
   - Backend: Azure Functions (Node.js)
   - Storage: Azure Blob + Cosmos DB

---

## 🏗️ Architecture


flowchart TD
    A[Frontend<br>(Next.js / Azure Static Web App)] -->|API Call| B[Backend<br>(Azure Functions)]
    B --> C[(Azure Blob Storage)]
    B --> D[(Azure Cosmos DB)]
    B --> E[Azure OpenAI<br>(Context + Summarization)]
    E --> B
    B -->|Response| A


This setup ensures a **fully serverless**, scalable solution where the frontend, backend, and AI services are all managed through Azure.

---

## ⚙️ Tech Stack

| Layer           | Service / Tool                | Purpose                     |
| --------------- | ----------------------------- | --------------------------- |
| **Frontend**    | Next.js 16, Tailwind CSS      | User Interface              |
| **Backend**     | Azure Functions               | API logic & orchestration   |
| **AI Services** | Azure OpenAI, Semantic Kernel | Contextual intelligence     |
| **Database**    | Azure Cosmos DB               | Persistent metadata storage |
| **Storage**     | Azure Blob Storage            | File management             |
| **Deployment**  | Azure Static Web Apps         | Hosting & CI/CD             |
| **Automation**  | GitHub Actions                | Continuous deployment       |

---

## 🧠 How It Works

1. **Upload Documents**
   Users upload research files or notes.

2. **Process & Store**
   Azure Functions handle ingestion and save structured data to Blob and Cosmos DB.

3. **Ask Questions**
   Queries are sent to the backend, where relevant context is fetched and passed to Azure OpenAI.

4. **Generate Responses**
   The system returns AI-generated answers grounded in uploaded data.

5. **Summarize & Refine**
   Optional document summarization and versioning supported.

---

## 📸 Screenshots

| Dashboard                             | Chat View                   | Upload Panel                    |
| ------------------------------------- | --------------------------- | ------------------------------- |
| ![Dashboard](./preview/dashboard.png) | ![Chat](./preview/chat.png) | ![Upload](./preview/upload.png) |

---

## 🌍 Deployment Setup

Deployed using **Azure Static Web Apps** (frontend) and **Azure Functions** (backend) — both under the same resource group for seamless API integration.

This approach simplifies auth, routing, and CI/CD through GitHub Actions, while maintaining cost efficiency.

---

## 🧭 Vision

> “AI shouldn’t replace human reasoning — it should extend it.”

The Research AI App is a prototype of how private, task-specific AI systems can transform how we organize, retrieve, and reason through our own data.

---

## 🧑‍💻 Author

**Oluwasegun Michael (mckings)**
IT Professional | AI Engineer | Azure Developer

🔗 [LinkedIn](https://www.linkedin.com/in/oluwasegunalabi)
✉️ [alabioluwasegun8@gmail.com](mailto:alabioluwasegun8@gmail.com)

---

## 🧱 License

MIT License — free to use, fork, or build upon.
Please credit the author where appropriate.

---

> *Built with Azure, powered by curiosity, and guided by precision.*



