

# 🤖 Enterprise AI Knowledge Assistant

An enterprise document-based AI chatbot built using **Retrieval-Augmented Generation (RAG)**.  
The system allows users to ask questions about enterprise documents and receive grounded answers generated using relevant information retrieved from the document knowledge base.

---
## 👥 Project Team

This project was developed collaboratively by a cross-functional team covering project leadership, frontend engineering, backend engineering, AI/RAG workflows, and deployment.

| Role | Team Members | Primary Contribution |
|---|---|---|
| 🎯 **Team Lead** | **Shirish Srivastava** | Project leadership, coordination, architecture oversight, and deployment |
| 🎨 **Frontend Development** | **Rohan**, **Saloni Mehta**, **Prashant Mondhe** | User interface, frontend application development, dashboard and frontend integration |
| ⚙️ **Backend Development** | **Ayush Bhagat**, **Harsh Roy**, **Umesh**, **Sumit**, **Sushant Pandey** | Backend APIs, AI/RAG workflow integration, document processing, retrieval, business logic, and backend services |
| 🚀 **Deployment** | **Shirish Srivastava**, **Rohan** | Application deployment, environment configuration, and production setup |

### 🧩 Team Contribution Overview

- **Project Leadership — Shirish Srivastava:** Led overall project coordination and contributed to architecture and deployment activities.
- **Frontend Team — Rohan, Saloni Mehta & Prashant Mondhe:** Developed the web-based user interface and integrated the frontend with the application backend.
- **Backend Team — Ayush Bhagat, Harsh Roy, Umesh, Sumit & Sushant Pandey:** Worked on backend services, API development, document ingestion, AI/RAG workflows, retrieval, grounding, verification, and supporting application logic.
- **Deployment — Shirish Srivastava & Rohan:** Handled deployment-related configuration and application rollout.

---



# 🎯 Project Objectives

The main objectives of this project are:

- Build an enterprise document-based AI assistant.
- Allow users to query organizational knowledge using natural language.
- Retrieve relevant information from enterprise documents.
- Implement Retrieval-Augmented Generation (RAG).
- Generate grounded answers using Google Gemini.
- Provide document and source citations with responses.
- Support enterprise knowledge across multiple departments.
- Provide a modern web-based user interface.
- Provide an administrative governance interface.
- Support document ingestion and indexing.
- Apply access-control and role-aware knowledge retrieval.
- Provide a scalable architecture for future agentic workflows and external connectors.
- Keep API credentials and sensitive configuration secure using environment variables.

---

# 🧩 Key Capabilities

### 🔎 Enterprise Knowledge Search

Users can ask natural language questions about internal organizational knowledge instead of manually searching through multiple documents.

### 📚 Document-Based Question Answering

The assistant retrieves relevant information from indexed enterprise documents and uses that information as context for answer generation.

### 🤖 Generative AI

Google Gemini is used to synthesize natural-language responses based on retrieved enterprise evidence.

### 📌 Grounded Responses

The system is designed to generate answers using retrieved evidence rather than relying only on the model's general knowledge.

### 🔗 Citations and Sources

Responses can include source information so users can understand where the answer originated.

### 🔐 Access-Aware Knowledge

The architecture supports role, department, confidentiality, and access-scope information as part of the AI workflow.

### 🛠️ Administrative Management

The project includes an administrative interface for managing users, departments, documents, settings, storage, and activity information.

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────────────┐
                         │      Enterprise Users       │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │       Frontend / UI         │
                         │       Next.js Application   │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │       Backend API            │
                         │          FastAPI             │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │      Query Processing        │
                         │ Classification / Routing    │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │     Knowledge Retrieval     │
                         │ Hybrid Search / Reranking   │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │      Retrieved Evidence     │
                         │ Documents / Relevant Chunks │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │     Grounded Synthesis       │
                         │        Google Gemini         │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │   Verification & Citations  │
                         │ Grounding / Claims / Sources│
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │     Final Enterprise Answer │
                         │       + Source Citations    │
                         └─────────────────────────────┘
```

---

# 🔄 End-to-End Workflow

```text
Enterprise Documents
        ↓
Document Ingestion
        ↓
Document Processing
        ↓
Embedding / Indexing
        ↓
Vector Database
        ↓
User Query
        ↓
Query Classification
        ↓
Access / RBAC Evaluation
        ↓
Hybrid Retrieval
        ↓
Evidence Reranking
        ↓
Grounding Validation
        ↓
LLM Synthesis
        ↓
Citation Validation
        ↓
Claim Verification
        ↓
Response Formatting
        ↓
Grounded Answer + Sources
```

---

# 🧠 AI / RAG Workflow

The AI workflow is organized into multiple stages.

### 1. Query Classification

The incoming user query is analyzed to determine the appropriate processing path.

Examples include:

- Enterprise knowledge queries
- General questions
- Queries requiring clarification
- Queries requiring access validation

### 2. Authorization

The workflow can evaluate information such as:

- User designation
- Department
- Confidentiality level
- Access scope
- Allowed knowledge domains

### 3. Retrieval

Relevant enterprise information is retrieved from the indexed knowledge base.

The retrieval layer contains components for:

- Hybrid search
- Document retrieval
- Evidence reranking
- Knowledge filtering

### 4. Grounding

Retrieved evidence is evaluated before being used for final answer generation.

### 5. Synthesis

The retrieved evidence and user question are provided to the generative AI layer.

Google Gemini generates the final response using the available enterprise context.

### 6. Verification

The generated response can pass through verification stages for:

- Grounding
- Citations
- Claims
- Evidence consistency

### 7. Response Formatting

The final response is formatted for presentation to the user together with available source information.

---

# 📚 Enterprise Knowledge Domains

The repository contains knowledge organized around multiple enterprise areas, including:

```text
HR
Engineering
Sales
Project Management
Operations
Support
Business Analysis
Enterprise Processes
```

Example knowledge sources include:

- Employee policies
- Engineering guides
- Project execution manuals
- Sales capability documents
- Incident escalation procedures
- Business analysis documents
- Enterprise forms and records

---

# 📥 Document Ingestion Pipeline

The backend contains a document ingestion pipeline responsible for preparing enterprise knowledge for retrieval.

```text
Document
   ↓
Document Ingestion
   ↓
Processing
   ↓
Embedding / Indexing
   ↓
Vector Database
   ↓
Retrieval
```

Relevant implementation areas include:

```text
backend/
└── GenAI/
    └── ingestion_pipeline/
        ├── ingest_documents.py
        └── embedding_jobs/
            └── vector_indexer.py
```

---

# 🔎 Retrieval System

The retrieval layer is organized into reusable components.

```text
backend/
└── GenAI/
    └── ai_workflows/
        └── rag_retrieval/
            ├── hybrid_search.py
            ├── reranker.py
            ├── retriever.py
            └── __init__.py
```

The retrieval architecture supports:

- Semantic retrieval
- Search-based retrieval
- Evidence reranking
- Relevant-context selection
- Vector database integration

---

# 🧠 Grounded Synthesis

The synthesis layer combines the user query with retrieved enterprise evidence.

```text
User Query
     +
Retrieved Evidence
     ↓
Grounded Synthesis
     ↓
Google Gemini
     ↓
Generated Enterprise Response
```

Implementation area:

```text
backend/
└── GenAI/
    └── ai_workflows/
        └── grounded_synthesis/
            ├── synthesis_engine.py
            └── __init__.py
```

The objective is to reduce unsupported responses by grounding generated answers in retrieved enterprise information.

---

# 🔗 Citation System

The project contains dedicated components for managing response sources.

```text
backend/
└── GenAI/
    └── ai_workflows/
        └── citation_builder/
            ├── citation_builder.py
            ├── citation_formatter.py
            ├── citation_validator.py
            └── __init__.py
```

The citation layer is responsible for supporting:

- Source construction
- Citation formatting
- Citation validation
- Source-aware responses

---

# ✅ Verification Layer

The system contains verification components for evaluating generated responses.

```text
backend/
└── GenAI/
    └── ai_workflows/
        └── verification/
            ├── claim_verifier.py
            ├── grounding_validator.py
            └── __init__.py
```

The verification workflow can be used to evaluate:

- Whether generated claims are supported by evidence
- Whether responses remain grounded
- Whether source information is valid
- Whether unsupported information should be rejected

---

# 🧭 Query Classification

The query classification layer determines how incoming requests should be handled.

```text
backend/
└── GenAI/
    └── ai_workflows/
        └── query_classification/
            ├── query_classifier.py
            ├── rbac_classifier.py
            └── __init__.py
```

This layer provides the foundation for:

- Query classification
- Knowledge routing
- RBAC-aware classification
- Future agentic decision-making

---

# ⚙️ Backend API

The backend is implemented using **FastAPI**.

Main application:

```text
backend/app.py
```

The API exposes a health endpoint and query endpoints.

### Health Check

```http
GET /
```

Example response:

```json
{
  "status": "ok",
  "message": "Enterprise GPT Backend is active"
}
```

### Query Endpoint

```http
POST /api/query
```

An equivalent route is also available:

```http
POST /query
```

Request:

```json
{
  "query": "What is the employee leave policy?",
  "designation": "HR Operations Lead"
}
```

Response:

```json
{
  "status": "success",
  "answer": "Generated enterprise-grounded answer...",
  "citations": []
}
```

The `designation` field is optional and currently has a default value configured by the backend.

---

# 🚨 API Validation

The backend validates incoming requests.

For example, an empty query is rejected:

```http
400 Bad Request
```

Example:

```json
{
  "detail": "Query cannot be empty."
}
```

Pipeline failures are returned as server errors rather than silently returning an invalid response.

---

# 🖥️ Frontend

The project contains a Next.js-based frontend application.

```text
Frontend/
├── app/
│   ├── page.js
│   ├── login/
│   │   └── page.js
│   └── dashboard/
│       ├── page.js
│       └── ...
├── components/
├── lib/
├── models/
├── public/
├── package.json
└── next.config.mjs
```

The frontend provides the user-facing application layer for interacting with the Enterprise GPT system.

---

# 🛡️ Admin Panel

The project also includes an administrative management interface.

```text
backend/
└── backend/
    └── admin_panel/
        ├── app/
        │   └── admin/
        │       ├── activity-logs/
        │       ├── dashboard/
        │       ├── departments/
        │       ├── documents/
        │       ├── settings/
        │       ├── Storage/
        │       └── users/
        │
        ├── components/
        ├── data/
        ├── lib/
        └── types/
```

The administrative interface provides areas for:

- Dashboard
- Users
- Departments
- Documents
- Activity logs
- Storage
- Settings
- Permissions
- Administrative controls

---

# 🗂️ Repository Structure

```text
Infosys-AI-Knowledge-Assistant-Enterprise-GPT/
│
├── README.md
├── DEPLOYMENT.md
│
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   ├── Procfile
│   ├── railway.json
│   ├── runtime.txt
│   │
│   ├── api/
│   │   ├── auth.py
│   │   ├── database.py
│   │   ├── crud/
│   │   ├── models/
│   │   ├── routers/
│   │   ├── schemas/
│   │   └── services/
│   │
│   ├── config/
│   │   ├── db_config.py
│   │   ├── env_config.py
│   │   ├── llm_config.py
│   │   ├── logger_config.py
│   │   └── supabase_config.py
│   │
│   ├── GenAI/
│   │   ├── ai_workflows/
│   │   │   ├── citation_builder/
│   │   │   ├── grounded_synthesis/
│   │   │   ├── orchestration/
│   │   │   ├── query_classification/
│   │   │   ├── rag_retrieval/
│   │   │   └── verification/
│   │   │
│   │   └── ingestion_pipeline/
│   │       ├── ingest_documents.py
│   │       └── embedding_jobs/
│   │
│   ├── data/
│   ├── uploads/
│   ├── demo/
│   └── vector_db/
│
└── Frontend/
    ├── app/
    ├── lib/
    ├── models/
    ├── public/
    ├── package.json
    └── next.config.mjs
```

---

# 🧰 Technology Stack

## Frontend

- Next.js
- React
- JavaScript
- CSS
- Node.js

## Backend

- Python
- FastAPI
- Uvicorn
- Pydantic

## AI / RAG

- Google Gemini
- Retrieval-Augmented Generation
- Semantic Search
- Hybrid Search
- Reranking
- Grounded Synthesis
- Claim Verification
- Citation Validation

## Database / Storage

- Vector database
- SQLite / relational database components
- Document storage

## Development

- Git
- GitHub
- npm
- Python virtual environments

---

# 🔐 Environment Variables

API credentials should be provided through environment variables rather than hard-coded in source code.

Example:

```text
GOOGLE_API_KEY=your_api_key
GEMINI_API_KEY=your_api_key
```

Depending on the configured environment, the backend can also recognize:

```text
OPENAI_API_KEY=your_api_key
```

### Important

Never commit real API keys, passwords, tokens, or other secrets to GitHub.

Use environment-specific configuration for development and production.

---

# 🚀 Running the Backend Locally

Navigate to the backend directory:

```powershell
cd backend
```

Create a virtual environment:

```powershell
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

Configure the required environment variables.

Run the application:

```powershell
python app.py
```

The API will run using the configured port, with `8000` used by default when no deployment `PORT` is supplied.

---

# 💻 Running the Frontend Locally

Navigate to the frontend:

```powershell
cd Frontend
```

Install dependencies:

```powershell
npm install
```

Start the development server:

```powershell
npm run dev
```

The frontend can then communicate with the backend API.

---

# 🔄 Example Query Flow

Example user question:

```text
What is the employee leave policy?
```

The system processes the request approximately as follows:

```text
User Question
      ↓
FastAPI
      ↓
Query Classification
      ↓
Access / RBAC Evaluation
      ↓
Knowledge Retrieval
      ↓
Evidence Reranking
      ↓
Grounding
      ↓
Google Gemini
      ↓
Citation Validation
      ↓
Claim Verification
      ↓
Final Answer
```

---

# 🏢 Enterprise Use Cases

The architecture can support enterprise scenarios such as:

### HR

- Employee policies
- Leave information
- HR procedures
- Employee documentation

### Engineering

- Architecture documentation
- Engineering guides
- Technical procedures
- Operational documentation

### Sales

- Sales assets
- Capability documents
- Business information
- Customer-facing knowledge

### Project Management

- Project manuals
- Execution procedures
- Process documentation
- Project knowledge

### Operations

- SOPs
- Incident procedures
- Operational processes
- Escalation workflows

---

# 🔐 Security Considerations

Enterprise AI systems require strong security controls.

The project architecture considers:

- Role-based access control
- Department-based access
- Confidentiality restrictions
- Environment-based secrets
- API validation
- Grounded responses
- Citation validation
- Audit and activity logging
- Safe handling of insufficient evidence

The current backend CORS configuration is permissive for development. Production deployments should restrict allowed origins to trusted frontend domains.

---

# 🧠 Agentic Architecture Direction

The system is structured so that the RAG pipeline can evolve into a more advanced agentic workflow.

Future orchestration can allow the system to decide whether a request should:

```text
                 User Query
                      ↓
               Query Analysis
                      ↓
             ┌────────┴────────┐
             ↓                 ↓
        General Query      Enterprise Query
                               ↓
                         Authorization
                               ↓
                         Tool Selection
                               ↓
                    ┌──────────┼──────────┐
                    ↓          ↓          ↓
                Retrieval   Connector   Knowledge
                    ↓          ↓          ↓
                    └──────────┼──────────┘
                               ↓
                         Evidence Merge
                               ↓
                       Grounded Synthesis
                               ↓
                         Verification
                               ↓
                       Final Response
```

This provides a foundation for future agentic orchestration and controlled tool selection.

---

# 🔌 MCP and External Connectors

The broader architecture is designed to support future integration with external enterprise knowledge systems and tools through controlled connectors.

Potential integrations include:

```text
Enterprise Databases
Document Management Systems
Internal APIs
Knowledge Platforms
Business Applications
Cloud Storage
Enterprise Search Systems
```

Connector access should be governed by authentication, authorization, tool permissions, logging, and data-access policies.

---

# 📊 Monitoring and Evaluation

An enterprise knowledge assistant should be evaluated using measurable quality and reliability metrics.

Potential evaluation metrics include:

- Retrieval relevance
- Retrieval recall
- Answer correctness
- Groundedness
- Citation accuracy
- Unsupported-claim rate
- Query success rate
- Response latency
- System reliability
- User feedback
- Knowledge coverage

The architecture also provides a foundation for usage and quality monitoring.

---

# 🧪 Testing

Testing should cover both individual components and end-to-end workflows.

Important scenarios include:

```text
Valid enterprise query
Invalid query
Empty query
General question
Knowledge question
Insufficient evidence
Unauthorized knowledge request
Missing documents
Retrieval failure
LLM failure
Citation validation failure
Claim verification failure
API failure
Frontend-backend communication
```

---

# 📦 Deployment

Deployment configuration is included in the repository.

Backend deployment-related files include:

```text
backend/
├── Procfile
├── railway.json
└── runtime.txt
```

Additional deployment documentation is available in:

```text
DEPLOYMENT.md
```

A production deployment should include:

- Secure environment variables
- Restricted CORS origins
- Proper database configuration
- Persistent vector storage
- Logging and monitoring
- Authentication and authorization
- Error handling
- Resource limits
- Production-grade secrets management

---

# 🌱 Future Enhancements

Potential future improvements include:

- Advanced LangGraph-based agent orchestration
- MCP-based enterprise connectors
- More sophisticated tool selection
- Multi-source retrieval
- Metadata-aware retrieval
- Freshness-aware ranking
- Automated document refresh
- Document archival
- Improved RBAC enforcement
- Enterprise SSO / OIDC
- Advanced evaluation pipelines
- User feedback loops
- Hallucination detection
- Response quality scoring
- Observability and tracing
- Usage analytics
- Cost optimization
- Scalable production vector infrastructure

---

# 🤝 Collaboration

This repository is developed as a collaborative project.

The codebase is organized into separate frontend, backend, AI workflow, ingestion, retrieval, administration, and deployment components so that different parts of the system can be developed and integrated independently.

Recommended collaboration practices:

```text
Create a focused change
        ↓
Test locally
        ↓
Commit the change
        ↓
Push to GitHub
        ↓
Open Pull Request
        ↓
Review
        ↓
Merge
```

---

# 📌 Project Vision

The long-term vision is to build a secure and scalable **Enterprise GPT platform** that transforms scattered organizational knowledge into an accessible, searchable, governed, and citation-backed source of information.

```text
Scattered Enterprise Knowledge
              ↓
        Unified Ingestion
              ↓
       Intelligent Indexing
              ↓
       Knowledge Retrieval
              ↓
        Agentic Processing
              ↓
       Grounded Generation
              ↓
      Verified AI Response
              ↓
      Enterprise Knowledge
          at Scale
```

---
# 🎥 Demo & Project Video

### 🚀 Live Demo

👉 **[Try the Enterprise AI Knowledge Assistant](https://infosys-ai-knowledge-assistant-ente.vercel.app)**

### 🎬 Project Demo Video

👉 **[Watch the Project Demo Video](https://drive.google.com/file/d/1eLrlb5lARE1fOb4WXK3Z7G8DuveXEBQV/view?usp=sharing)**


---


# 📄 License

This project is intended for educational, demonstration, and development purposes.

See the repository license and project documentation for additional information.

---

# ⭐ Enterprise AI Knowledge Assistant

**Search less. Understand more. Make enterprise knowledge accessible through AI.**
