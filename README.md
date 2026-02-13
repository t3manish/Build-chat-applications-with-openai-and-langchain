# 🤖 Building a Q&A Chatbot with AI

I took the “Build Chat Applications with OpenAI + LangChain” path and turned lessons into a working Q&A chatbot — starting from the raw OpenAI API, then leveling up with LangChain, LCEL, and a full RAG pipeline. I followed the 365 Data Science materials and did the practicals end‑to‑end, so this README is all results, no boilerplate.

The repo snapshot below shows the exact modules I worked through (OpenAI API, Model Inputs/Outputs, LCEL, RAG) plus my Q&A bot notebooks and course PDFs.

---

### 🛠️ First Steps I Nailed

*   Spun up a dedicated conda environment (`langchain_env`) to isolate dependencies and keep projects clean.
*   Registered the env as a Jupyter kernel for seamless notebook runs.
*   Configured the OpenAI API key via environment variables for secure, portable access.
*   **Goal:** build a chatbot from scratch with the OpenAI API first; no LangChain magic until I understood the fundamentals.

### 🧩 OpenAI Chat Basics I Mastered

*   **Message roles:** `system`, `user`, `assistant` — and how role design shapes behavior.
*   Built a fun baseline: a sarcastic persona controlled via the `system` prompt.
*   Tuned responses with:
    *   **Temperature** (creativity/entropy)
    *   **Max tokens** (budget and verbosity)
    *   **Streaming** (token‑by‑token UX and latency control)

### 🎛️ Model Inputs I’m Comfortable With

*   `ChatOpenAI` configuration and safety‑first defaults.
*   System/Human/AI messages and multi‑turn context control.
*   Prompt Templates & Values that make prompts reproducible.
*   Chat Prompt Templates (single/multi‑message).
*   Few‑Shot Chat Message templates to “show, not tell” behavior.

### 📤 Model Outputs I Can Shape

*   `String Output Parser` for direct, clean text.
*   `Comma‑Separated List Parser` for structured lists from LLMs.
*   `Datetime Output Parser` for normalized time extraction.

### 🔗 LCEL Superpowers I Use

*   Piping `Prompt → Model → Output Parser` for clean, testable chains.
*   Batching and Streaming for throughput and UX.
*   **Runnables:**
    *   `Runnable` / `RunnableSequence`
    *   `RunnablePassthrough` for threadable context
    *   `RunnableParallel` to run independent chains concurrently (hello, speed!)
    *   `RunnableLambda` for quick custom functions
*   Piping chains together and graphing runnables for clarity.
*   Chain decorators to keep logic readable and modular.

### 📚 RAG Pipeline I Built (End‑to‑End)

*   **Indexing:**
    *   Document loading with `PyPDFLoader` and `DOCX2TXT`.
    *   Splitting via `CharacterTextSplitter` and `MarkdownHeaderTextSplitter`.
*   **Embedding & Storage:**
    *   OpenAI embeddings → Chroma vector store.
    *   Document inspection and vectorstore maintenance.
*   **Retrieval:**
    *   Similarity Search and MMR for diverse, relevant context.
    *   Vectorstore‑backed retrievers with flexible `k` and scoring.
*   **Generation:**
    *   Stuffing retrieved docs into prompts with guardrails.
    *   Response generation with streaming for snappy UX.

### 🔥 Project Highlight: My LangChain Q&A Bot

*   **Use Case:** Q&A over a Tableau course PDF (plus supplementary notes).
*   **Pipeline:**
    *   Ingested course materials (e.g., `Introduction_to_Tableau.pdf`) and created embeddings with GPT‑4 class embeddings.
    *   Stored vectors in ChromaDB, managed and inspected collections.
    *   Wired up a Retriever → LLM chain with LCEL for clean, debuggable flow.
    *   Enabled streaming responses so answers start appearing instantly.
*   **Result:** Ask anything about the Tableau course and get grounded, explainable answers sourced from the material — not hallucinations. The repo tree shows the RAG + Q&A notebooks alongside course assets.

### 💡 What I Can Do Now

*   Stand up chatbots from scratch with the OpenAI API, then scale with LangChain.
*   Design prompts and personas that actually stick to instructions.
*   Build production‑ready RAG stacks: loaders → splitters → embeddings → vectorstore → retriever → generator.
*   Optimize for speed, cost, and quality with streaming, batching, and LCEL patterns.
*   Deliver explainable answers with source grounding and retriever diagnostics.

---

### 🙌 Thanks to 365 Data Science

I took this project from 365 Data Science’s materials and they taught me LLM basics the hands‑on way — I practiced every step, compared models, and shipped real results. If you want someone who can convert LLM theory into a working chatbot and RAG system fast, that’s what I do.

