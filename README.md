<h1 align="center">Hi, I'm David Banoth 👋</h1>
<p align="center"><b>GenAI Engineer @ Oatmeal AI</b> · Building production agentic AI for agriculture<br/>Fremont, CA · Open to GenAI Engineer roles (Bay Area / Remote)</p>

---

### 🧑‍💻 About me
- I design and ship **multi-agent LLM systems** that run in production, with an emphasis on **safety boundaries**: specialist agents stay read-only, and every write goes through a human-approval gate.
- My day-to-day: **LangGraph** orchestration, **RAG** on Firestore vector search, **Gemini** on **Vertex AI**, and **FastAPI** services on **GCP / Cloud Run** shipped through **Docker + GitHub Actions**.
- I came into AI engineering from **application support and analytics** (SQL diagnostics, Grafana dashboards), so I care about observability, uptime, and data you can trust.
- 🎓 M.S. Business Analytics, **University of the Pacific** (2024)

---

### 🌱 Featured work

#### [Saige: AI Agricultural Advisory Assistant](https://github.com/dbanoth/Saige-AI-Agricultural-Advisory-Assistant) · *production @ Oatmeal AI*
A conversational farm assistant covering crops, livestock, weather, precision agriculture, and market news. **I designed and built the backend:** the agent graph, the retrieval pipeline, the API, and the write-approval boundary.
- **Supervisor graph (LangGraph):** hybrid keyword + LLM router that can call **multiple specialists in one turn**, then a synthesizer merges their answers with citations
- **Human-in-the-loop writes:** specialists are read-only ReAct loops; changes become **proposals** → deterministic **policy gate** → farmer approves / edits / rejects → only **allowlisted tools** execute (LangGraph interrupts + checkpoints)
- **RAG:** Firestore vector search + `text-embedding-004` across crop, livestock, product-docs, and news collections, with graceful fallback
- **Precision ag:** answers grounded in the farmer's own fields (vegetation indices, water/irrigation, alerts, scouting) with charts
- **Crop-photo scans:** local vision model + Gemini vision return a diagnosis card
- **API:** FastAPI with JWT auth, SSE streaming, Redis rate limiting (20 req/min/thread), health and readiness probes
- **Memory and state:** Redis (short-term memory + checkpoints), Firestore (chat history), SQL (proposal audit trail)

#### [hitl-agriculture-agent](https://github.com/dbanoth/hitl-agriculture-agent): human-in-the-loop diagnostic advisor
An earlier agentic advisor that diagnoses crop and plant issues through guided, multiple-choice Q&A.
- LangGraph state machine + Gemini structured output (Pydantic) → FastAPI → **Next.js / TypeScript** frontend
- Redis message buffer, Firestore chat history, RAG and embedding sync, weather integration
- **pytest** suite (unit + integration), **Docker / docker-compose**, and **GitHub Actions** workflows for test and deploy

#### Oatmeal Farm Network: production platform contributions
- Regular contributor to Oatmeal's backend and platform repos (SAIGE lives in the OFN codebase)
- Ship changes through reviewed, merged pull requests to the production backend
- Building a **SAIGE usage-metering dashboard** in Oatmeal's internal org portal, fed by backend usage data

#### [CHAT-BOT](https://github.com/dbanoth/CHAT-BOT): Groq + Streamlit chatbots
Two small LLM chat apps on Llama 3.1 via Groq: a minimal chatbot and a version that logs conversations to Supabase.

---

### 🛠️ Tech stack

| Area | Tools |
|---|---|
| **LLMs & agents** | LangGraph, LangChain, Google Gemini 2.5 Flash Lite, Vertex AI, Groq (Llama 3.1), ReAct, multi-agent supervisor patterns, HITL interrupts |
| **RAG** | Firestore Vector Search, `text-embedding-004`, Vertex AI Vector Search |
| **Backend** | Python, FastAPI, Pydantic v2, SSE streaming, JWT auth, Redis |
| **Data** | BigQuery, Firestore, SQL, Supabase |
| **Cloud & DevOps** | GCP, Cloud Run, Docker, docker-compose, GitHub Actions CI/CD, pytest |
| **Frontend** | React, Next.js, TypeScript, Streamlit |
| **Observability** | Grafana, SQL diagnostics |

---

### 📫 Reach me
Open to **GenAI / AI Engineer** roles. Happy to walk through how SAIGE handles safe agent writes.

<!-- Add your links: -->
<!-- [LinkedIn](https://www.linkedin.com/in/YOUR-HANDLE) · [Email](mailto:you@example.com) -->
