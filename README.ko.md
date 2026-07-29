<p align="center">
  <a href="README.md">English</a> | <a href="README.ko.md">한국어</a>
</p>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg?v=2">
  <img alt="윤채민, AI 엔지니어" src="assets/banner-light.svg?v=2" width="100%">
</picture>

**서울 기반 AI 엔지니어 · 캐나다 이주 준비 중**  
캐나다 워킹홀리데이(IEC) 승인을 받았습니다. 시작 시점은 자유롭게 맞출 수 있습니다.  
[LinkedIn](https://www.linkedin.com/in/chaemin-yoon-0a35782b7/) · [dbscoals789@gmail.com](mailto:dbscoals789@gmail.com)

모델을 먼저 고르기보다 문제와 데이터의 구조를 먼저 봅니다. 문서에는 계층이 있고, 교통에는 기하 구조가 있고, 사고 기록에는 인과가 있습니다.
(주)지오시스템리서치에서 3년 차로 일하며 사내 AI 전환을 맡고 있고, 아래는 그 과정에서 나온 것들입니다.

<br>

## 문서 AI

**[Parse-Everything](https://github.com/chaeminyoon/Parse-Everything)** · 기존 파서에 환경영향평가 보고서를 넣으면 표가 깨졌고, 파서를 바꿔도 깨지는 위치만 달라졌습니다.
그래서 결과를 채점하고 이슈 유형에 따라 고치고, 점수가 떨어지면 되돌리는 루프를 만들었습니다.
본문 절반이 날아간 문서를 품질점수 **0.41 → 0.93**으로 복구합니다.

**[Doc-Vectorize-Pipeline](https://github.com/chaeminyoon/Doc-Vectorize-Pipeline)** · 매일 갱신되는 정부 공문을 폐쇄망 서버에서 처리하는 파이프라인을 구축했습니다.
공문 한 건을 문서·청크·첨부·허가정보 네 테이블로 분해해 넣어서 임베딩 검색과 조건 질의를 함께 씁니다.
검색 top-3 정확도 **0.85**를 달성했습니다.

## 시공간 예측

**[AIS-Traffic-Ops](https://github.com/chaeminyoon/AIS-Traffic-Ops)** · MLflow는 실험을 추적하지만 레지스트리의 모델이 지금 서빙되는 그 모델인지는 알려주지 않고, 실험과 서빙과 모니터링이 각각 다른 화면에 있었습니다.
그래서 모델별 버전의 레지스트리, 구조, 학습 수렴, 예측 비교, 시스템 연결 상태를 한 화면에 모았습니다.
승격은 production 심볼릭 링크를 바꾸면 끝나고, FastAPI 서버가 그 변경을 감지해 재시작 없이 새 모델을 올립니다.

**[AIS-Traffic-Model](https://github.com/chaeminyoon/AIS-Traffic-Model)** · 5분 간격 AIS 프레임 12장으로 다음 교통량 지도를 예측합니다.
대부분의 격자가 비어 있어 loss로는 판단이 안 돼서, 예측을 실제 교통량 스케일로 되돌려 격자끼리 비교하는 기준을 만들고 점유 F1과 SSIM으로 버전을 골랐습니다.
ConvLSTM 베이스라인에 시점을 고르는 attention과 항로 형태를 지키는 spatial U-Net 디코더를 얹어, 335,741 파라미터로 점유 F1을 **3.3배(0.17 → 0.55)**, SSIM을 **40%(0.56 → 0.78)** 올렸습니다.


## 검색

**[Maritime-GraphRAG](https://github.com/chaeminyoon/Maritime-GraphRAG)** · "부산항에 컨테이너선을 기항시키는 선사는?"은 조인이라 벡터 검색으로 풀리지 않습니다.
Neo4j에 문서·엔티티 이중 그래프를 쌓고 정답 있는 합성 데이터로 재보니 벡터 0.70, Text2Cypher **0.85**였습니다.
그런데 Text2Cypher는 3홉에서 0점이었습니다. 질문에 따라 검색방법별 정확도가 계속 달랐고, 그래서 라우터가 가장 잘 답할 수 있는 검색방법을 선택하게 만들었습니다.

**[RAG-Audit-Pipeline](https://github.com/chaeminyoon/RAG-Audit-Pipeline)** · 검색 품질이 떨어지는 원인은 대개 모델이 아니라 데이터입니다.
중복 문서는 MinHash/LSH로 후보 쌍을 좁힌 뒤 그 후보만 임베딩 코사인으로 확인해, 모델별로 보정한 임계값을 넘는 쌍만 제거합니다.
문서를 19% 덜어냈는데 NDCG@10은 0.927에서 0.936으로 올랐습니다. 정답 문서 오삭제는 0건이었습니다.

## 이상 탐지

**[Vehicle-Anomaly-Algorithm](https://github.com/chaeminyoon/Vehicle-Anomaly-Algorithm)** · 40개 지점 CCTV 영상 차량 궤적에서 역주행·급정거·지그재그·차로횡단을 찾습니다.
기본 LSTM 오토인코더는 F1 0.25였고, 차로 상대 좌표, 2D 방향장, 차로 횡단 정보를 추가하여 최종 **F1 0.85 / PR-AUC 0.97**이 됐습니다.
유형별로는 역주행 100%, 급정거 89%, 지그재그 70%, 차로횡단 46%를 잡아낼 수 있습니다.

**[CBM-Anomaly-Dashboard](https://github.com/chaeminyoon/CBM-Anomaly-Dashboard)** · 선박 추진축 진동 데이터에는 라벨이 없어서, 정상·결함을 아는 합성 데이터로 채점 기준을 만들었습니다.
회전기계 결함 4종(불평형, 정렬불량, 베어링 마모, 풀림)을 물리 기반으로 합성해 심었습니다.
임계값은 정상 데이터의 95% 분위수로만 잡고 테스트 라벨로 튜닝하지 않았습니다.
Dense 오토인코더가 **F1 0.93 / PR-AUC 0.975**로 불평형과 정렬불량을 100% 잡아냈습니다.

## 도구

**[Data-Analyze-MCP](https://github.com/chaeminyoon/Data-Analyze-MCP)** · 어떤 LLM에나 데이터 분석 도구 **60개**를 붙여줍니다.
데이터 분석, 전처리, 시각화를 자동으로 수행하고 데이터 유형별 최적의 차트를 제공합니다.
차트 팔레트는 색각이상 시뮬레이션과 배경 대비 검사를 통과해야 하고, 그 검사가 pytest로 CI에서 매 커밋 돌아갑니다.

<br>

## 학력

인하대학교 공학대학원 미래융합기술학과 빅데이터애널리틱스 전공, 공학석사 (2025)  
논문: LSTM 오토인코더를 활용한 차량 이상 궤적 식별 정확도 향상에 관한 연구

## 기술 스택

| | |
|:--|:--|
| **언어** | Python · SQL · TypeScript |
| **모델링** | TensorFlow / Keras · PyTorch · scikit-learn · ConvLSTM · U-Net · 오토인코더 · YOLOv8 |
| **LLM · 검색** | LangGraph · Neo4j · Text2Cypher · BGE-M3 · BM25 + dense RRF · MinHash/LSH · LangSmith |
| **데이터** | PostgreSQL + pgvector · SQLite · SQLAlchemy · PyMuPDF · lxml · Surya OCR |
| **서빙 · 운영** | FastAPI · Docker · MLflow · Prometheus · Grafana · Streamlit · pytest · CI |

---

캐나다에서 AI 엔지니어로 일할 자리를 찾고 있습니다. 워킹홀리데이(IEC) 준비 중이라 스폰서십 없이 시작할 수 있습니다.  
[LinkedIn](https://www.linkedin.com/in/chaemin-yoon-0a35782b7/) · [dbscoals789@gmail.com](mailto:dbscoals789@gmail.com)
