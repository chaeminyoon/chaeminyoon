<p align="left">
  <a href="README.md">English</a> | <a href="README.ko.md">한국어</a>
</p>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg?v=2">
  <img alt="Cheamin Yoon, AI Engineer" src="assets/banner-light.svg?v=2" width="100%">
</picture>

**AI Engineer in Seoul, preparing to relocate to Canada**  
Approved for a Canadian IEC working holiday permit. No sponsorship or LMIA required, and my start date is flexible.  
[LinkedIn](https://www.linkedin.com/in/chaemin-yoon-0a35782b7/) · [dbscoals789@gmail.com](mailto:dbscoals789@gmail.com)

I look at the structure of the problem and the data before picking a model. Documents have hierarchy, traffic has geometry, accident records have causation.
Three years in at GeoSystem Research, I lead the company's AI transition, and everything below came out of that work.

<br>

## Document AI

**[Parse-Everything](https://github.com/chaeminyoon/Parse-Everything)** · Existing parsers broke the tables in Korean environmental-impact reports.
Switching parsers only moved the breakage.
So I built a loop that scores its own output, routes each repair by what broke, and rolls back the moment a repair makes the score worse.
On a document missing half its body text, quality goes from **0.41 to 0.93**.

**[Doc-Vectorize-Pipeline](https://github.com/chaeminyoon/Doc-Vectorize-Pipeline)** · Government documents, updated daily and processed on an air-gapped server.
Each one is split across four tables, one for the document itself and the rest for chunks, attachments, and the permit fields pulled out of the text, so that embedding search and structured queries run against the same record.
Top-3 retrieval accuracy is **0.85**.

## Spatiotemporal forecasting

**[AIS-Traffic-Ops](https://github.com/chaeminyoon/AIS-Traffic-Ops)** · MLflow tracks experiments, but it won't tell you whether the model sitting in the registry is the one currently being served, and experiments, serving, and monitoring each lived on a different screen.
So I put the registry, model architecture, training convergence, prediction comparison, and system connection status for every version on one screen.
Promotion is a change to the `production` symlink, and the FastAPI server picks that up and swaps the model in without a restart.

**[AIS-Traffic-Model](https://github.com/chaeminyoon/AIS-Traffic-Model)** · Twelve AIS frames at five-minute intervals go in, the next traffic map comes out.
Most cells are empty, so loss couldn't tell me much. I built a standard that inverse-transforms predictions back to real traffic scale and compares them against the actual grid, then ranked versions on occupancy F1 and SSIM.
On a ConvLSTM baseline, attention picks which time steps matter and a spatial U-Net decoder holds the shipping-lane shapes; at 335,741 parameters that lifted occupancy F1 by **3.3× (0.17 → 0.55)** and SSIM by **40% (0.56 → 0.78)**.

## Retrieval

**[Maritime-GraphRAG](https://github.com/chaeminyoon/Maritime-GraphRAG)** · "Which carriers send container ships to Busan?" is a join.
Vector search doesn't do joins.
So I built a two-layer Neo4j graph over documents and typed entities, and measured it on synthetic data with known answers: vector 0.70, Text2Cypher **0.85**.
Then Text2Cypher scored zero on 3-hop questions. No retriever wins everywhere, so a router reads each question and sends it to the retriever best suited to answer it.

**[RAG-Audit-Pipeline](https://github.com/chaeminyoon/RAG-Audit-Pipeline)** · When retrieval quality drops, the cause is usually the data rather than the model.
Duplicates go through MinHash/LSH first to narrow the candidate pairs, then only those candidates get checked by embedding cosine, and only pairs above a threshold calibrated for that model are removed.
Cleaning took **19%** of the corpus out and NDCG@10 still rose from 0.927 to 0.936. Not one gold document was deleted by mistake.

## Anomaly detection

**[Vehicle-Anomaly-Algorithm](https://github.com/chaeminyoon/Vehicle-Anomaly-Algorithm)** · Wrong-way driving, sudden stops, zigzagging, and lane-crossing, found in vehicle tracks from CCTV at 40 sites.
A baseline LSTM autoencoder scored F1 0.25. Adding lane-relative coordinates, a 2D direction field, and lane-crossing counts brought that to **F1 0.85 / PR-AUC 0.97**.
By type it catches wrong-way at 100%, sudden stops at 89%, zigzagging at 70%, and lane-crossing at 46%.

**[CBM-Anomaly-Dashboard](https://github.com/chaeminyoon/CBM-Anomaly-Dashboard)** · Propulsion-shaft vibration comes without labels.
So the scoring standard runs on synthetic data where both normal and faulty are known, with four classic rotating-machinery faults injected from their physical signatures: unbalance, misalignment, bearing wear, and looseness.
Thresholds come from the 95th percentile of normal scores alone, never tuned on test labels.
A dense autoencoder reached **F1 0.93 / PR-AUC 0.975** and caught unbalance and misalignment at 100%.

## Tools

**[Data-Analyze-MCP](https://github.com/chaeminyoon/Data-Analyze-MCP)** · **Sixty** data-analysis tools any LLM can call.
It profiles, cleans, and plots automatically, picking a chart type that fits the data, and every palette it draws with has to clear color-vision-deficiency simulation and background-contrast checks that pytest runs in CI on every commit.

<br>

## Education

M.E., Big Data Analytics Program, Graduate School of Engineering, Inha University (2025)  
Thesis: Improving the Accuracy of Vehicle Anomalous Trajectory Identification Using an LSTM Autoencoder

## Stack

| | |
|:--|:--|
| **Languages** | Python · SQL · TypeScript |
| **Modelling** | TensorFlow / Keras · PyTorch · scikit-learn · ConvLSTM · U-Net · autoencoders · YOLOv8 |
| **LLM · retrieval** | LangGraph · Neo4j · Text2Cypher · BGE-M3 · BM25 + dense RRF · MinHash/LSH · LangSmith |
| **Data** | PostgreSQL + pgvector · SQLite · SQLAlchemy · PyMuPDF · lxml · Surya OCR |
| **Serving · ops** | FastAPI · Docker · MLflow · Prometheus · Grafana · Streamlit · pytest · CI |

---

I'm looking for AI engineering work in Canada. The IEC working holiday permit means I can start without sponsorship.  
[LinkedIn](https://www.linkedin.com/in/chaemin-yoon-0a35782b7/) · [dbscoals789@gmail.com](mailto:dbscoals789@gmail.com)
