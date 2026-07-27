# RAG Retrieval Lab

A modular research and development laboratory for testing, evaluating, and benchmarking **Retrieval-Augmented Generation (RAG)** techniques, custom chunking strategies, and vector store configurations.

---

## Featured Projects & Experiments

### MedQuad Medical RAG (PoC)
* **Goal**: Accurate medical Q&A over reliable health literature (NIH, MedlinePlus, Cancer.gov).
* **Chunking Strategy**: Structured Question & Answer atomic chunking (`chunk_overlap=0`).
* **Vector Store**: ChromaDB with OpenAI `text-embedding-3-small`.
* **Pipeline & LLM**: Built with LangChain Expression Language (LCEL) and `gpt-4o-mini`.

---

## Project Structure

```text
rag-retrieval-lab/
├── RAG_LangChain.ipynb     # MedQuad RAG implementation pipeline
├── requirements.txt        # Core dependencies
├── .gitignore              # Environment and local data isolation
└── README.md               # Project documentation