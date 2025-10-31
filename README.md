
# 🧠 Hybrid RAG System – Private AI Research Assistant

A privacy-first **Retrieval-Augmented Generation (RAG)** system designed to learn from your **own documents, URLs, and policies** — not the public internet.  
This project was built to demonstrate the full scope of the **Microsoft Azure AI Engineer Associate** learning path in a real, practical solution.

## 🚀 Overview

This solution represents a **hybrid RAG architecture** that:
- **Retrieves** knowledge from private documents, files, and URLs.
- **Generates** insights and answers using Azure OpenAI models.
- **Refines** existing content (like policies or procedures) into improved versions.
- Runs entirely within a **secure Azure environment** — no external data exposure.

It’s a step toward building AI systems that **learn what you feed them**, without compromising control or compliance.

---

## 🧩 Core Features

1. **Private Knowledge Ingestion**
   - Upload internal documents (PDF, DOCX, TXT)
   - Fetch and parse data directly from URLs
   - Automatically extract and store meaningful content

2. **Smart Retrieval**
   - Uses Azure AI Search and OpenAI embeddings for semantic search
   - Supports vector-based document retrieval and ranking

3. **Contextual Generation**
   - Answers questions using context from private data
   - Keeps reasoning transparent and grounded in your content

4. **Document Refinement**
   - Suggests improved or updated versions of uploaded documents
   - Maintains version history (v1.0 → v2.0) in secure Blob Storage

5. **Full Azure Stack Integration**
   - Azure Functions (Backend logic)
   - Azure OpenAI (LLM + embeddings)
   - Azure AI Search (Vector indexing)
   - Azure Blob Storage (Data persistence)
   - Azure Static Web Apps (Frontend deployment)

---

## 🏗️ Architecture

    User SPA (React/Next/Static Web Apps)
    ├─ Auth: Azure AD / B2C (OIDC)
    ├─ Upload UI -> API Gateway (API Management or Static Web Apps serverless backend)
    └─ Query UI -> Query API

    API Layer (Azure Functions / Azure App Service)
    ├─ Orchestration: Durable Functions for long jobs (ingest, reindex)
    ├─ Ingest endpoint -> Blob Storage (raw docs) -> Ingest pipeline trigger (Event Grid)
    └─ Query endpoint -> Retrieval + LLM pipeline

    Ingest pipeline:Blob Storage (raw files) 
   
    -> Azure Function (extract text: pdf, docx, txt, pptx) 
    -> Text splitter & metadata (filename, author, upload date, tags) 
    -> Embedding generation (Azure OpenAI embeddings or Azure Cognitive Services embeddings) 
    -> Store: Azure Cognitive Search with vector store + fields for metadata + pointers to blob URIs
 
    Query pipeline:
    User query -> Azure Function
    -> Semantic ranking + vector search (Azure Cognitive Search) returning top K docs/snippets + score
    -> Optional reranker (smaller model or BM25 hybrid)
    -> LLM prompt assembly (include top-k snippets and instruction to refuse outside docs)
    -> Azure OpenAI (or local LLM) for answer + provenance block
    -> Post-process: source extraction, answer confidence, QA checks
    -> Return answer + citations + source snippets + retrieval log

    Monitoring & security:
    Key Vault for secrets
    App Insights / Log Analytics
    Azure Policy / RBAC
    Data governance: blob encryption, retention, PII detection with Azure Purview or custom classifier



---

## ⚙️ Tech Stack

| Layer               | Service / Tool                                   | Purpose                                |
| ------------------- | ------------------------------------------------ | -------------------------------------- |
| **Frontend**        | React / Next.js (Static Web App)                 | User interface                         |
| **Backend**         | Azure Functions (Python or Node.js)              | API endpoints, ingestion, query logic  |
| **Vector Search**   | Azure AI Search                                  | Index and retrieve document embeddings |
| **Storage**         | Azure Blob Storage                               | File and version management            |
| **LLM**             | Azure OpenAI (GPT-4o or GPT-35-turbo)            | Generation and refinement              |
| **Embedding Model** | text-embedding-ada-002 or text-embedding-3-small | Semantic vector representation         |

---

## 🧠 How It Works

1. **Upload or Link**
   Add a document or URL for ingestion.

2. **Embed and Index**
   The backend extracts text, generates embeddings, and indexes it in Azure AI Search.

3. **Query and Retrieve**
   When you ask a question, the system fetches top-matching results using vector similarity.

4. **Generate Answer**
   Azure OpenAI combines context with your question to produce a grounded, clear response.

5. **Refine and Save**
   You can request a refined version of any document — stored as a new version for review.

---
## 🌍 Live Demo & Video

🔹 **Deployed App:** [https://yourapp.azurewebsites.net](https://yourapp.azurewebsites.net)  
🔹 **Demo Video:** [Watch on YouTube](https://youtube.com/your-demo-link) 
Coming soon: Live demo and walkthrough video

> The demo showcases how the system learns from uploaded company documents and URLs, retrieves relevant insights, and refines documents into improved versions — all inside Azure’s private environment.

## 💰 Credit Optimization

To stay within Azure’s **$200 free credit**, use:

* **Consumption plan** for Functions (serverless cost-saving)
* **GPT-4o-mini** or **GPT-35-turbo** for inference
* **text-embedding-3-small** for embeddings
* Regularly clean unused files and indices

---

## 🧩 Future Enhancements

* Multi-user role support (via Azure Entra ID)
* Multi-tenant data isolation for organizations
* Integration with Microsoft Teams for internal Q&A
* Real-time analytics dashboard

---

## 🧭 Vision

The **Hybrid RAG System** is more than a demo — it’s a proof of concept for:

> “AI that learns *your world*, not the world’s noise.”

By combining everything from Azure AI Engineer Associate concepts — model deployment, AI Search, OpenAI, Functions, and Storage — this project shows what enterprise-grade, private AI assistants can look like.

---

## 🧑‍💻 Author

**Oluwasegun Michael (mckings)**
AI Engineer | Azure Enthusiast | Front-End Engineer

Built as part of the **Microsoft Certified: Azure AI Engineer Associate** learning journey.

---

## 🧱 License

MIT License. You are free to fork, build, and experiment — just keep it open and ethical.

```


