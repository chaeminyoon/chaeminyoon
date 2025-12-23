# Hi there, I'm Chaemin Yoon 👋

### **AI Researcher & Engineer** | Maritime Safety AI & Production RAG Systems

> **"I turn research prototypes into reliable, interpretable, production-ready systems."**

I bridge the gap between academic research and practical software engineering. My expertise lies in building **Explainable Deep Learning models** for maritime safety and architecting **Hybrid RAG systems** (Vector + Graph) for enterprise document intelligence.

---

## Current Focus

### Maritime Traffic Risk Modeling
*Architecting deep learning systems for proactive maritime safety and collision avoidance.*
- **Core Tech:** ConvLSTM-Attention networks for spatio-temporal pattern recognition.
- **Explainability (XAI):** Implementing Attention Maps to visualize risk factors and tuning operational thresholds (ROC/AUC) for real-world decision support.
- **Engineering:** Building deterministic grid-based geospatial pipelines.

### Advanced RAG Systems
*Designing robust retrieval pipelines for ambiguous queries and noisy technical documents.*
- **Architecture:** Hybrid Retrieval utilizing **VectorDB (ChromaDB)** for semantic search and **Knowledge Graph (Neo4j)** for structured context.
- **Stack:** Local LLMs (Ollama), metadata extraction, and sophisticated reranking layers.
- **Goal:** Solving query ambiguity, ensuring citation grounding, and minimizing hallucinations.

---

## What I Bring

| Competency | Description |
| :--- | :--- |
| **End-to-end AI Development** | From raw data ingestion to deployment — **I ship complete systems**, not just Jupyter notebooks. |
| **Interpretation-First Design** | Every model I build comes with explainability tools: attention maps, error analysis, and operational thresholding. |
| **Production Mindset** | Config-driven experiments, versioned datasets (DVC), CI-ready code structure, and fully reproducible results. |
| **Geospatial Expertise** | Handling complex spatial data: Grid-based aggregation, spatial joins, and real-world operational constraints. |

---

## Tech Stack

<div align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" />
  <br/>
  <img src="https://img.shields.io/badge/Neo4j-008CC1?style=for-the-badge&logo=neo4j&logoColor=white" />
  <img src="https://img.shields.io/badge/ChromaDB-111111?style=for-the-badge&logo=databricks&logoColor=white" />
  <img src="https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
</div>

---

## Featured Projects

### [AIS_dataprocessing](git@github.com:chaeminyoon/AIS_dataprocessing.git)
**Interpretable deep learning for maritime collision risk prediction**
> A spatio-temporal risk modeling system designed for operational decision support, featuring attention-based explainability.

* **Operational Metrics:** ROC/AUC evaluation optimized with real-world alarm thresholds.
* **XAI Visualization:** Attention maps to interpret *why* and *where* the model predicts high risk.
* **Geospatial Pipeline:** Robust processing from Raw Shapefiles → Grid Indexing → Feature Aggregation.
* **Reproducibility:** Fully config-driven experiments with deterministic data splits.

### [Onpremise LLM: Local RAG Engine](git@github.com:chaeminyoon/python-onpremise-rag.git)
**Production-grade PDF → VectorDB pipeline for enterprise RAG**
> An end-to-end CLI tool for ingesting, cleaning, and indexing large-scale document collections into ChromaDB.

* **Resumable Pipeline:** Fault-tolerant stages (Ingest → Clean → Chunk → Embed → Index).
* **Incremental Updates:** Smart handling of new/modified files using dataset manifests.
* **Optimization:** Batch processing tuned for large-scale enterprise collections.
* **Evaluation:** Built-in framework to assess retrieval quality and chunking strategies.

### [Search System: GraphRAG Engine](git@github.com:chaeminyoon/python-news-knowledge-graph.git)
**Graph-augmented retrieval for ambiguous technical queries**
> A Hybrid RAG system combining semantic vector search with knowledge graph traversal to handle complex domains.

* **Graph Schema:** Detailed modeling of `Document ↔ Chunk ↔ Entity ↔ Topic ↔ Citation` in Neo4j.
* **Context Expansion:** Solves query ambiguity by traversing the graph to find related entities.
* **Trustworthy AI:** Implements Reranking and strict citation grounding to reduce hallucinations.
* **Domain Focus:** Optimized for policy, regulation, and complex technical documentation.

---
---

### Stats

<div align="left">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=chaeminyoon&layout=compact&theme=radical&card_width=400" alt="Top Languages" />

</div>

