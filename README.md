# RAG Retrieval Lab

A modular research and development laboratory for testing, evaluating, and benchmarking **Retrieval-Augmented Generation (RAG)** techniques, custom chunking strategies, and vector store configurations.

---

## Project Overview: MedQuad Medical RAG (PoC)

This Proof of Concept (PoC) project demonstrates a highly accurate medical Question & Answer system. By leveraging reliable health literature (NIH, MedlinePlus, Cancer.gov) through the MedQuad dataset, the system mitigates Large Language Model (LLM) hallucinations and provides grounded, context-aware medical responses. 

## System Architecture & Tech Stack

*   **Orchestration:** LangChain (implemented via LCEL - LangChain Expression Language for optimized pipeline execution)
*   **Vector Store:** ChromaDB (for efficient local semantic search and document retrieval)
*   **Embeddings:** OpenAI `text-embedding-3-small` (for high-dimensional semantic representation)
*   **Generative Model:** OpenAI `gpt-4o-mini`
*   **Environment:** Python, Jupyter Notebook

## Data Processing & Chunking Strategy

Standard character or token-based splitting often degrades the context in highly technical domains like healthcare. To address this, the project implements a custom data ingestion architecture:
*   **Strategy:** Structured Question & Answer atomic chunking.
*   **Parameters:** `chunk_overlap=0`
*   **Rationale:** Medical data requires strict precision. By treating each Q&A pair from the MedQuad dataset as an atomic, indivisible unit, the retrieval phase guarantees that semantic meaning is preserved without introducing noise from overlapping, irrelevant text chunks.

## Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/duyqu-chan/rag-retrieval-lab.git](https://github.com/duyqu-chan/rag-retrieval-lab.git)
   cd rag-retrieval-lab

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txtpip install -r requirements.txt

3. **Environment Setup:** Ensure you have your OpenAI credentials ready. Create a .env file in the root directory.
   ```bash
   OPENAI_API_KEY="your_api_key_here"

4. **Execution:** Launch Jupyter environment and execute RAG_LangChain.ipynb to initialize the ChromaDB vector store, embed the medical literature, and query the LCEL chain.

## Project Structure

rag-retrieval-lab/
├── RAG_LangChain.ipynb     # End-to-end MedQuad RAG implementation pipeline
├── requirements.txt        # Core dependencies (LangChain, ChromaDB, OpenAI, etc.)
├── .gitignore              # Environment and local data isolation
└── README.md               # Technical project documentation
