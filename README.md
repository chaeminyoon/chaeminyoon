<div align="center">

# Hi there, I'm Chaemin Yoon 👋

### **AI Researcher & Engineer**
*Maritime Safety AI & Production RAG Systems*

<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=1000&color=3776AB&center=true&vCenter=true&width=800&lines=I+turn+research+prototypes+into+production+systems.;Explainable+Deep+Learning+for+Maritime+Safety;Hybrid+RAG+Architecture+(Vector+%2B+Graph)" alt="Typing SVG" /></a>
<br/>

<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" />
<img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white" />
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" />
<img src="https://img.shields.io/badge/Neo4j-008CC1?style=flat-square&logo=neo4j&logoColor=white" />
<img src="https://img.shields.io/badge/ChromaDB-111111?style=flat-square&logo=databricks&logoColor=white" />
<img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />

</div>

<br/>

<table>
<tr>
<td width="60%" valign="top" style="padding: 20px 20px 20px 0;">


## 🔭 Current Focus

### 🌊 Maritime Traffic Risk Modeling
> *Architecting deep learning systems for proactive maritime safety.*
- **Core Tech:** ConvLSTM-Attention for spatio-temporal patterns.
- **XAI:** Attention Maps & ROC/AUC tuning for decision support.
- **Engineering:** Deterministic grid-based geospatial pipelines.

### 🧠 Advanced RAG Systems
> *Robust retrieval for ambiguous queries & noisy docs.*
- **Architecture:** Hybrid (VectorDB + Neo4j Knowledge Graph).
- **Stack:** Local LLMs (Ollama), metadata extraction, reranking.
- **Goal:** Solving ambiguity & minimizing hallucinations.
<br/>

</td>
<td width="40%" valign="top" style="padding-left: 20px;">



## 🧩 Languages

<div align="center">
<br/>

![Top Languages](https://github-readme-stats-salesp07.vercel.app/api/top-langs/?username=chaeminyoon&layout=compact&theme=radical&hide_border=true&card_width=375)
![GitHub Streak](https://streak-stats.demolab.com/?user=chaeminyoon&theme=radical&hide_border=true)
</div>


</td>
</tr>
</table>

---

## 💡 What I Bring

| Competency | Description |
| :--- | :--- |
| **End-to-end AI** | From raw data ingestion to deployment — **I ship complete systems**, not just notebooks. |
| **Interpretation-First** | Every model comes with explainability tools: attention maps, error analysis, thresholds. |
| **Production Mindset** | Config-driven experiments, versioned datasets (DVC), CI-ready code structure. |
| **Geospatial Expertise** | Grid-based aggregation, spatial joins, real-world operational constraints. |

---

## 🚀 Featured Projects

### 🚢 [MaritimeTrafficProject (AIS_dataprocessing)](https://github.com/chaeminyoon/AIS_dataprocessing)
**Interpretable deep learning for maritime collision risk prediction**
> **Operational Metrics:** ROC/AUC evaluation optimized with real-world alarm thresholds.<br/>
> **XAI Visualization:** Attention maps to interpret *why* and *where* risk is high.<br/>
> **Geospatial Pipeline:** Raw Shapefiles → Grid Indexing → Feature Aggregation.

### 📚 [Onpremise LLM: Local RAG Engine](https://github.com/chaeminyoon/python-onpremise-rag)
**Production-grade PDF → VectorDB pipeline for enterprise RAG**
> **Resumable Pipeline:** Fault-tolerant stages (Ingest → Clean → Chunk → Embed → Index).<br/>
> **Optimization:** Batch processing tuned for large-scale enterprise collections.<br/>
> **Evaluation:** Built-in framework to assess retrieval quality.

### 🔗 [Search System: GraphRAG Engine](https://github.com/chaeminyoon/python-news-knowledge-graph)
**Graph-augmented retrieval for ambiguous technical queries**
> **Graph Schema:** `Document ↔ Chunk ↔ Entity ↔ Topic` modeling in Neo4j.<br/>
> **Context Expansion:** Solves query ambiguity by traversing the graph.<br/>
> **Trustworthy AI:** Reranking and strict citation grounding.

---

## 📐 Production-Ready Structure
*I ensure reproducibility and scalability through this structure:*

```bash
project/
├── README.md          # Context: Problem → Method → Results
├── configs/           # Control: Experiment parameters (YAML/Hydra)
├── src/               # Logic: Modular, tested, decoupled core code
├── tests/             # Quality: Unit tests for critical functions
└── reports/           # Insight: Auto-generated plots & metrics
