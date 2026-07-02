# AWS_Essential_2026

2026 AWS Essential 교육 과정 실습 내용을 정리한 저장소

## 📅 교육 개요
- 기간 : 방학 중 3일 집중 교육
- 교육 시간 : 총 18시간 (3일 × 6시간)
- 목적
  - AWS 클라우드 서비스 이해
  - AWS AI/ML 서비스 실습
  - 생성형 AI 및 문서 AI 활용 경험
---

# Day 1
## ☁️ Cloud & AWS 소개
### 학습 내용
- Cloud Computing 개념
- AWS 주요 서비스 소개
- AWS 계정 생성
- IAM 사용자 및 권한 관리
- SageMaker 도메인 생성
---
## 🤖 Amazon SageMaker Canvas
### 학습 내용
- Machine Learning(Classification) 개요
- SageMaker Canvas 활용

### 실습
- TMDB 영화 데이터를 이용한 흥행 성공 예측 모델 구현
- Kaggle 공개 데이터 활용

---

## 📝 Amazon Comprehend
### 학습 내용
- 감성 분석(Sentiment Analysis)
- 개체명 인식(Entity Recognition)
- 토픽 모델링(Topic Modeling)

### 실습
- 다양한 Comprehend API 활용
- 텍스트 분석 실습
---

# Day 2
## 🧠 Amazon Bedrock (1)

### 학습 내용
- Amazon Bedrock 소개
- Foundation Model 이해
- 자연어 처리(NLP) 기초
- 프롬프트 엔지니어링

### 실습
- Bedrock 기반 미니 프로젝트
---

## 🖼 Amazon Rekognition

### 학습 내용
- 이미지 분석 AI
- 이미지 라벨 감지
- 얼굴 분석 API
- 커스텀 라벨 모델

### 실습
- Rekognition API 활용

---

# Day 3

## 💬 Amazon Bedrock (2)

### 학습 내용
- RAG(Retrieval-Augmented Generation)
- Knowledge Base 구축

### 실습
- Bedrock 기반 생성형 AI 구현

---

## 📄 Amazon Textract

### 학습 내용
- 문서에서 텍스트 추출
- 키(Key) / 값(Value) 추출
- 테이블 데이터 추출

### 실습
- Textract API를 이용한 OCR 및 문서 분석

---

# 🛠 사용 기술

- AWS
- Amazon SageMaker Canvas
- Amazon Comprehend
- Amazon Bedrock
- Amazon Rekognition
- Amazon Textract
- Python

---

# 📌 학습 목표
- AWS 클라우드 서비스 이해
- AI/ML 서비스 활용 능력 향상
- 생성형 AI 활용 경험 습득
- AWS 기반 AI 애플리케이션 개발 기초 학습

---

# 💭 가장 흥미로웠던 내용

이번 교육에서 가장 흥미로웠던 내용은 **RAG(Retrieval-Augmented Generation)**였다.

처음에는 생성형 AI가 모든 정보를 알고 답변한다고 생각했지만, RAG는 먼저 관련 문서를 검색한 뒤 그 내용을 기반으로 답변을 생성한다는 점이 인상 깊었다. 이를 통해 생성형 AI의 Hallucination(환각)을 줄이고, 최신 정보나 기업 내부 문서까지 활용할 수 있다는 점을 이해할 수 있었다.

특히 질문과 문서를 **벡터(Embedding)** 로 변환하여 의미적으로 유사한 문서를 검색한다는 과정이 가장 흥미로웠다. 단순히 같은 단어를 찾는 것이 아니라, **의미가 비슷한 단어들이 벡터 공간에서 가까운 위치에 표현된다**는 개념이 인상 깊었고, AI가 문장의 의미를 수학적으로 표현하여 활용한다는 점이 신기하게 느껴졌다.

또한 학교 홈페이지에서 사용하는 AI 챗봇 역시 이러한 RAG 구조를 활용하여 학교 규정이나 공지사항을 검색한 뒤 답변을 생성하는 방식일 수 있겠다는 생각이 들었다. 이번 실습을 통해 생성형 AI 서비스를 구현하기 위해서는 단순히 LLM만 사용하는 것이 아니라, 검색 시스템과 데이터베이스를 함께 구성하는 것이 중요하다는 점을 배울 수 있었다.
