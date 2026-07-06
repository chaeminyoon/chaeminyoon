<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img alt="Chaemin Yoon — AI Engineer. Systems that check their own work." src="assets/banner-light.svg" width="100%">
</picture>

I build AI systems that are accountable for their own output — document parsers that evaluate and repair their own failures, risk models that show their reasoning, and retrieval pipelines instrumented for measurement before they are tuned for demos.

Right now that means a document-AI platform: LLM parsing workflows with full-trace observability (Langfuse), experiment tracking (MLflow), and quality gates that decide whether an output ships, gets repaired, or gets rolled back — automatically.

<br>

## Selected work

### 01 · Self-healing document parsing

**[Parse-Everything](https://github.com/chaeminyoon/Parse-Everything)** — Most parsing pipelines fail silently: garbage goes in a database and nobody notices until a user does. This workflow treats every parse as a hypothesis. Outputs are scored against quality gates, failing sections are repaired with targeted re-prompts, and any repair that makes things worse is rolled back to the last good state.

<sub>Python · LLM orchestration · MLflow · Langfuse · MinIO · FastAPI</sub>

### 02 · Operating a forecasting model like a service

**[AIS-Traffic-Ops](https://github.com/chaeminyoon/AIS-Traffic-Ops)** — The MLOps half of a maritime traffic forecasting system: the model is wrapped in evaluation, serving, and monitoring workflows so that retraining and deployment are routine operations rather than events. Training a model is the easy part; this repository is about everything after.

<sub>Python · MLflow · FastAPI · Docker · monitoring</sub>

### 03 · Interpretable maritime risk forecasting

**[AIS-Traffic-Model](https://github.com/chaeminyoon/AIS-Traffic-Model)** — Short-term traffic forecasting from AIS grid sequences, with the model lineage documented as it evolved. ConvLSTM with attention over spatio-temporal grids; attention maps show *where* the model is looking, and alarm thresholds are tuned on ROC/AUC against real operational false-alarm budgets — because a safety model nobody trusts is a model nobody uses.

<sub>PyTorch · ConvLSTM + attention · XAI · geospatial pipelines</sub>

### 04 · Retrieval for questions vector search can't answer

**[python-news-knowledge-graph](https://github.com/chaeminyoon/python-news-knowledge-graph)** — Vector search retrieves what is *similar*; ambiguous questions need what is *related*. This engine builds a `Document ↔ Chunk ↔ Entity ↔ Topic` knowledge graph in Neo4j and traverses it to expand context, with reranking and strict citation grounding so every answer can be traced to a source.

<sub>Neo4j · vector + graph hybrid retrieval · reranking · citation grounding</sub>

### 05 · RAG that runs where the data can't leave

**[python-onpremise-rag](https://github.com/chaeminyoon/python-onpremise-rag)** — An enterprise RAG engine for air-gapped environments, built on LangGraph and local LLMs. The ingestion pipeline (ingest → clean → chunk → embed → index) is staged and resumable, because on a hundred-thousand-page collection, "restart from scratch" is not an error-handling strategy.

<sub>LangGraph · Ollama · ChromaDB · fault-tolerant batch pipelines</sub>

<br>

## How I work

**Evaluation is the product.** A model without a measurement harness is a demo. Every system above ships with its own evaluation loop — quality gates, retrieval metrics, or operational thresholds — before it ships features.

**Explainability is an interface, not a report.** Attention maps, repair logs, and citations exist so that the person operating the system can decide when to trust it and when to override it.

**Reproducibility is table stakes.** Config-driven experiments, versioned data, and pipelines that resume instead of restart. If a result can't be reproduced, it didn't happen.

<br>

## Stack

| | |
|:--|:--|
| **Languages** | Python · SQL · TypeScript |
| **Modelling** | PyTorch · TensorFlow · scikit-learn |
| **LLM systems** | LangGraph · Ollama · Neo4j · ChromaDB · Langfuse |
| **Operations** | FastAPI · Docker · MLflow · DVC · MinIO |

<br>

---

<sub>Seoul, KR (UTC+9) — open to AI engineering roles in Canada · <a href="mailto:cmyoon@geosr.com">cmyoon@geosr.com</a></sub>

<sub>No badges, no stat widgets. The repositories above are the résumé.</sub>
