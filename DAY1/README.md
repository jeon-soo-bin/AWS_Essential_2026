# Day 1 - Cloud & AWS, SageMaker Canvas, Amazon Comprehend

## 📖 학습 목표

- Cloud Computing의 개념과 AWS 서비스 이해
- AWS AI/ML 서비스의 역할과 특징 학습
- Machine Learning 분류(Classification) 개념 이해
- Amazon SageMaker Canvas를 이용한 머신러닝 모델 구축
- Amazon Comprehend를 활용한 자연어 처리(NLP) 실습

---

# ☁️ Cloud Computing

## Cloud Computing이란?

Cloud Computing은 인터넷을 통해 서버, 스토리지, 데이터베이스, 네트워크, AI 서비스 등을 필요한 만큼 사용할 수 있는 컴퓨팅 방식이다.

기존에는 직접 서버를 구매하고 관리해야 했지만, 클라우드에서는 필요한 만큼만 사용하고 비용을 지불(Pay-as-you-go)한다.

### 장점

- 초기 인프라 구축 비용 절감
- 높은 확장성(Scalability)
- 높은 가용성(Availability)
- 빠른 서비스 배포
- 유지보수 부담 감소

---

# ☁️ AWS (Amazon Web Services)

AWS는 Amazon에서 제공하는 세계 최대 규모의 클라우드 플랫폼이다.

컴퓨팅, 스토리지, 데이터베이스, AI, 머신러닝 등 200개 이상의 서비스를 제공한다.

이번 교육에서는 다음 서비스를 사용하였다.

- IAM
- Amazon SageMaker
- Amazon Comprehend
- Amazon Bedrock
- Amazon Rekognition
- Amazon Textract

---

# 🔐 IAM (Identity and Access Management)

IAM은 AWS 리소스에 대한 접근 권한을 관리하는 서비스이다.

실습에서는

- AWS 계정 로그인
- MFA(다중 인증) 설정
- IAM Role 생성
- SageMaker 실행 권한 부여

등을 수행하였다.

---

# 🤖 Amazon SageMaker Canvas

## SageMaker란?

Amazon SageMaker는 머신러닝 모델을 개발, 학습, 배포할 수 있는 AWS 서비스이다.

이번 실습에서는 코드를 거의 작성하지 않고 머신러닝 모델을 만들 수 있는 **SageMaker Canvas**를 사용하였다.

### Canvas의 특징

- No-Code 머신러닝
- 데이터 업로드만으로 모델 생성
- 자동 데이터 분석
- 예측 결과 시각화
- 다양한 AWS 서비스와 연동 가능

---

## 실습 내용

### 1. SageMaker Studio 환경 구성

- SageMaker Domain 생성
- Studio 실행
- JupyterLab 생성
- IAM 권한 설정

---

### 2. 데이터 생성

Python을 이용하여 영화 데이터를 생성하였다.

생성된 주요 Feature

- budget
- runtime
- vote_average
- release_month
- director_popularity
- cast_popularity
- marketing_score
- sequel_flag

Target

- hit_10M
  - 천만 관객 돌파 여부

---

### 3. 데이터 전처리

생성한 데이터에서

- 이상치(Outlier) 제거
- CSV 저장

등의 전처리를 수행하였다.

---

### 4. Canvas 모델 구축

TMDB 영화 데이터를 이용하여

**영화가 천만 관객을 돌파할지 예측하는 Classification 모델**을 생성하였다.

모델 생성 과정

1. Dataset 생성
2. Target 지정 (hit_10M)
3. Feature 선택
4. Quick Build 실행
5. 예측 결과 확인

---

# 📚 Machine Learning Classification

Classification은 입력 데이터를 여러 클래스 중 하나로 분류하는 머신러닝 기법이다.

이번 실습에서는

```
영화 정보
↓

천만 관객 돌파 여부
YES / NO
```

를 예측하는 이진 분류(Binary Classification)를 수행하였다.

---

# 📝 Amazon Comprehend

## Amazon Comprehend란?

Amazon Comprehend는 AWS에서 제공하는 자연어 처리(NLP) 서비스이다.

머신러닝을 이용하여 사람이 작성한 텍스트를 자동으로 분석할 수 있다.

별도의 NLP 모델을 직접 학습하지 않아도 다양한 텍스트 분석 기능을 사용할 수 있다.

---

## 주요 기능

### 감성 분석 (Sentiment Analysis)

문장이

- Positive
- Negative
- Neutral
- Mixed

중 어떤 감정을 가지는지 분석한다.

예)

> "배송이 정말 빨라서 만족합니다."

→ Positive

---

### 개체명 인식 (Entity Recognition)

문장에서

- 사람
- 회사
- 장소
- 날짜
- 금액

등의 정보를 자동으로 추출한다.

예)

> "Amazon은 미국 시애틀에 본사를 두고 있다."

↓

- Amazon → Organization
- 미국 → Location
- 시애틀 → Location

---

### 키 구문 추출 (Key Phrase Extraction)

문장에서 핵심 키워드를 추출한다.

예)

> "AWS의 SageMaker는 머신러닝 플랫폼이다."

↓

- AWS
- SageMaker
- 머신러닝 플랫폼

---

### 언어 감지 (Language Detection)

입력된 문장이 어떤 언어인지 자동으로 판별한다.

예)

- 한국어
- 영어
- 일본어
- 프랑스어

---

### 토픽 모델링 (Topic Modeling)

대량의 문서에서

비슷한 주제끼리 자동으로 그룹화한다.

---

## 실습 내용

- 언어 감지 API
- 감성 분석 API
- 개체명 인식 API
- 키 구문 추출
- 토픽 분석

실습을 통해 AWS의 NLP 서비스를 직접 호출하고 결과를 확인하였다.

---

# 💡 배운 점

- Cloud Computing의 기본 개념과 AWS 서비스 구조를 이해하였다.
- SageMaker Canvas를 이용하여 No-Code 방식으로 머신러닝 분류 모델을 생성하였다.
- 데이터 전처리와 Feature 선택이 모델 성능에 중요한 영향을 미친다는 것을 확인하였다.
- Amazon Comprehend를 활용하여 자연어 처리 기능(감성 분석, 개체명 인식, 언어 감지 등)을 직접 실습하였다.
- AWS의 AI 서비스들은 별도의 모델을 직접 구현하지 않아도 API 호출만으로 다양한 AI 기능을 활용할 수 있다는 점을 경험하였다.
