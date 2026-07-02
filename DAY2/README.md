# Day 2 - Amazon Rekognition & Amazon Bedrock

## 📖 학습 목표

- Computer Vision(컴퓨터 비전)의 기본 개념 이해
- Amazon Rekognition을 이용한 이미지 분석 AI 실습
- Rekognition API를 활용한 객체, 얼굴, 텍스트 인식
- Amazon Bedrock을 이용한 생성형 AI(LLM) 활용
- Foundation Model을 API 형태로 사용하는 방법 이해

---

# 👁️ Computer Vision

## Computer Vision이란?

Computer Vision은 이미지나 영상을 분석하여 사람이 눈으로 인식하는 것처럼 사물이나 장면을 이해하는 AI 기술이다.

대표적인 활용 분야

- 얼굴 인식
- 자율주행
- 의료 영상 분석
- 스마트 팩토리
- CCTV
- 쇼핑 이미지 검색

---

# 📷 Amazon Rekognition

## Rekognition이란?

Amazon Rekognition은 AWS에서 제공하는 Computer Vision 서비스이다.

딥러닝 기반의 이미지 분석 모델을 AWS에서 미리 학습해 두었기 때문에,
사용자는 API를 호출하는 것만으로 다양한 이미지 분석 기능을 사용할 수 있다.

### 특징

- 별도의 모델 학습이 필요 없음
- 높은 정확도
- API 기반 사용
- 이미지와 동영상 모두 분석 가능

---

# 🔍 Rekognition 주요 기능

## 1. DetectLabels

이미지 속 객체를 자동으로 인식한다.

예)

사진

↓

- Person
- Car
- Building
- Tree

등을 신뢰도와 함께 반환한다.

활용 사례

- 사진 자동 분류
- 쇼핑 상품 카테고리 분류
- 이미지 검색

---

## 2. DetectFaces

이미지 속 얼굴을 감지하고 분석한다.

분석 가능한 정보

- 얼굴 위치
- 연령 추정
- 성별 추정
- 웃음 여부
- 안경 착용 여부
- 감정(Happy, Sad 등)

활용 사례

- 사진 필터
- 광고 분석
- UX 리서치

---

## 3. CompareFaces

두 얼굴이 동일 인물인지 비교한다.

활용 사례

- Face ID
- 금융 본인 인증
- 출입 통제 시스템

---

## 4. DetectText (OCR)

이미지 속 글자를 추출한다.

예)

사진 속

```
WELCOME
```

↓

텍스트 반환

활용 사례

- 번호판 인식
- 영수증 인식
- 메뉴판 번역
- 문서 OCR

---

## 5. Content Moderation

부적절한 이미지를 자동으로 감지한다.

예)

- 폭력
- 성인 콘텐츠
- 노출 이미지

활용 사례

- SNS
- 커뮤니티
- 쇼핑몰

---

## 6. PPE Detection

산업 현장에서

- 안전모
- 마스크
- 안전조끼

등을 제대로 착용했는지 검사한다.

활용 사례

- 스마트 공장
- 건설 현장
- 산업 안전 관리

---

## 7. Celebrity Recognition

유명 인사를 자동으로 인식한다.

활용 사례

- 방송
- 뉴스
- 미디어 검색

---

# 🧠 Custom Labels

기본 모델이 인식하지 못하는 객체를 직접 학습시키는 기능이다.

실습에서는

- 프로젝트 생성
- 이미지 업로드
- Bounding Box 지정
- Label 생성
- 모델 학습

과정을 수행하였다.

이를 통해 특정 로고나 특정 객체만 인식하는 사용자 지정 모델을 만들 수 있다.

---

# 💻 Rekognition API 실습

Python에서 boto3 SDK를 이용하여 Rekognition API를 호출하였다.

실습한 기능

- DetectLabels
- DetectFaces
- DetectText
- CompareFaces

API 응답(JSON)을 분석하여

- 객체 이름
- Confidence
- Bounding Box

등을 출력하였다.

---

# 🤖 Amazon Bedrock

## Amazon Bedrock이란?

Amazon Bedrock은 다양한 생성형 AI 모델(Foundation Model)을 하나의 플랫폼에서 사용할 수 있도록 제공하는 AWS 서비스이다.

별도의 GPU 서버를 구축하거나 모델을 직접 학습하지 않아도 API 호출만으로 생성형 AI를 사용할 수 있다.

---

## Foundation Model

Foundation Model(FM)은 대규모 데이터를 사전 학습한 범용 AI 모델이다.

대표적인 모델

- Amazon Nova
- Claude (Anthropic)
- Llama (Meta)
- Mistral AI
- Cohere

Bedrock에서는 이러한 모델을 하나의 API 인터페이스로 사용할 수 있다.

---

# Bedrock 실습

이번 실습에서는

- Bedrock Runtime 생성
- Foundation Model 선택
- Prompt 작성
- 모델 호출
- 응답(Response) 출력

과정을 수행하였다.

Python SDK(boto3)를 이용하여 생성형 AI API를 직접 호출하는 방법을 학습하였다.

---

# Prompt Engineering

생성형 AI의 결과는 Prompt에 따라 크게 달라진다.

좋은 Prompt의 요소

- 역할(Role) 지정
- 목적(Task) 명확화
- 출력 형식 지정
- 예시(Few-shot)

등을 포함하면 더욱 정확한 결과를 얻을 수 있다.

---

# 💡 배운 점

- Computer Vision 기술이 이미지와 영상 데이터를 분석하는 핵심 기술임을 이해하였다.
- Amazon Rekognition은 별도의 모델 학습 없이 API만으로 객체, 얼굴, 텍스트 등을 인식할 수 있다는 점을 확인하였다.
- Custom Labels 기능을 이용하면 특정 기업 로고나 제품처럼 일반 모델이 인식하지 못하는 객체도 직접 학습시킬 수 있다는 것을 배웠다.
- Python과 boto3를 이용하여 Rekognition API를 호출하고 JSON 형태의 응답을 처리하는 방법을 익혔다.
- Amazon Bedrock을 통해 다양한 생성형 AI 모델을 하나의 플랫폼에서 사용할 수 있으며, Foundation Model을 직접 구축하지 않고도 생성형 AI 기능을 애플리케이션에 쉽게 적용할 수 있음을 이해하였다.
- Prompt를 어떻게 작성하느냐에 따라 생성형 AI의 응답 품질이 크게 달라진다는 점을 실습을 통해 확인하였다.
