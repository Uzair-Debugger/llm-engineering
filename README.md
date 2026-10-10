# 🚀 LangChain & LLM Application Engineering Journey

Welcome to my personal engineering portfolio for Large Language Model (LLM) application development. 

Rather than just consuming theory, I built this repository to document my hands-on journey of writing code, debugging, and implementing core AI concepts from scratch. My goal is to bridge the gap between theoretical AI and practical, production-minded software engineering.

> **Status:** This is an ongoing, multi-part personal project. I am actively building, testing, and expanding this codebase as I dive deeper into the LLM ecosystem.

---

## 🗺️ Project Roadmap

- [x] **Part 01: Core Components, Prompt Engineering & Basic Agents** *(Current)*
- [ ] **Part 02: Advanced RAG & Vector Database Optimization** *(In Progress)*

---

## 🛠️ Part 01: What I Built & Implemented

In this first phase, I focused on understanding the foundational architecture of LLM applications. I moved beyond simple API calls to build stateful, context-aware, and tool-using applications using **LangChain** and **IBM watsonx.ai**.

### 📓 Notebook 1: Prompt Engineering & LCEL Pipelines
**File:** `1-prompt-engineering-and-langchain-templates.ipynb`

I explored how to effectively communicate with LLMs and structure complex workflows using LangChain's modern **LCEL (LangChain Expression Language)**.
* **Prompting Strategies Implemented:** Zero-shot, One-shot, Few-shot, Chain-of-Thought (CoT), and Self-Consistency.
* **LCEL Architecture:** Built modular, composable pipelines using the pipe (`|`) operator, replacing legacy `LLMChain` paradigms with modern `Runnable` components.
* **Practical Applications Built:** 
  * Text summarization and classification agents.
  * Context-aware Question Answering (QA) bots.
  * SQL code generation from natural language.
  * Role-playing conversational agents.

### 📓 Notebook 2: RAG Foundations, Memory & Autonomous Agents
**File:** `2-langchain-documents-retrieval-chains-and-agents.ipynb`

I engineered a full Retrieval-Augmented Generation (RAG) pipeline and built autonomous agents capable of executing external logic.
* **Data Ingestion & Processing:** Implemented Document Loaders (PDF, Web) and engineered Text Splitters (`CharacterTextSplitter`, `RecursiveCharacterTextSplitter`) to optimize context windows.
* **Vector Search & Retrieval:** Integrated **ChromaDB** for vector storage. Implemented advanced retrieval strategies, including the **Parent Document Retriever**, to solve the trade-off between precise embedding search and maintaining broad contextual relevance.
* **Stateful Conversations:** Engineered conversational memory using `InMemoryChatMessageHistory` and `RunnableWithMessageHistory` to maintain context across multi-turn interactions.
* **Tool-Calling Agents:** Built autonomous agents using `create_agent`. I wrote custom Python tools (a secure AST-based Calculator and a Text Formatter) and configured the LLM to act as a reasoning engine to decide *when* and *how* to execute these deterministic tools.

---

## 💡 Key Engineering Takeaways

Through building this project, I developed a practical understanding of several critical LLM engineering concepts:
1. **The Shift to LCEL:** Transitioned from older, rigid chain structures to the highly flexible, functional LCEL pattern using `RunnablePassthrough.assign()` for complex multi-step data routing.
2. **RAG Trade-offs:** Learned firsthand that simply chunking text isn't enough; implementing strategies like Parent-Document retrieval drastically improves the LLM's ability to answer complex queries without losing context.
3. **Agent Execution vs. Generation:** Understood the critical distinction between an LLM *requesting* a tool call (AIMessage) and the application actually *executing* the Python function (ToolMessage) to return deterministic results.
4. **Model Parameter Tuning:** Experimented extensively with `temperature`, `top_p`, and `max_new_tokens` to control the trade-off between creative generation and factual consistency.

---

## 💻 Tech Stack

* **Language:** Python 3.11+
* **Orchestration Framework:** LangChain (LCEL, Agents, Retrievers)
* **LLM Provider:** IBM watsonx.ai (Granite, Llama models)
* **Vector Database:** ChromaDB
* **Data Processing:** PyPDF, LangChain Text Splitters
* **Environment Management:** `python-dotenv`

---

## ⚙️ Setup & Local Execution

If you want to run my implementations locally, follow these steps:

### 1. Clone the Repository
```bash
git clone https://github.com/Uzair-Debugger/llm-engineering.git
cd llm-engineering
```

### 2. Configure Environment Variables
This project uses **IBM watsonx.ai**. You will need an IBM Cloud account to generate your credentials. 
Create a `.env` file in the root directory:
```env
IBM_API_KEY=<your-ibm-watsonx-api-key>
IBM_URL=<your-watsonx-url>
IBM_PROJECT_ID=<your-watsonx-project-id>
```

### 3. Install Dependencies
```bash
pip install "langchain==1.4.2" \
            "langchain-core==1.6.4" \
            "langchain-community==0.4.2" \
            "langchain-ibm==1.1.0" \
            "langchain-experimental==0.4.2" \
            "langchain-chroma==1.1.0" \
            "langchain-classic==1.0.8" \
            "langchain-text-splitters==1.1.2" \
            "ibm-watsonx-ai==1.7.2" \
            "chromadb==1.5.9" \
            "pypdf==6.19.0" \
            "python-dotenv==1.2.3" \
            "pydantic==2.13.5" \
            "tenacity==9.1.4"
```

### 4. Run the Notebooks
Open the Jupyter Notebooks in your preferred IDE (VS Code, JupyterLab) and run the cells sequentially.

---

## 📬 Connect with Me

I am actively looking for opportunities to apply these skills in a professional environment. If you're building with LLMs or have feedback on my implementations, I'd love to connect!

**Syed Muhammad Uzair**  
*Software Engineer | LLM Application Developer*  
🔗 [GitHub](https://github.com/Uzair-Debugger) | 🔗 [LinkedIn](https://www.linkedin.com/in/syed-muhammad-uzair-/?lipi=urn%3Ali%3Apage%3Ad_flagship3_feed%3BwsWLNnKIR4i2Rl5kD6tE6A%3D%3D)

---
*Built with curiosity, caffeine, and a lot of debugging.* ☕🐛
