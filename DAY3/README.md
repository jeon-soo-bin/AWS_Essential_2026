# Day 3 - RAG(Retrieval-Augmented Generation) & Amazon Textract

## 📖 학습 목표

- RAG(Retrieval-Augmented Generation)의 동작 원리 이해
- 생성형 AI의 Hallucination(환각) 문제와 해결 방법 학습
- Amazon Textract를 이용한 문서 AI(Document AI) 이해
- 문서에서 텍스트, 테이블, 폼 데이터를 자동 추출하는 방법 실습
- RAG와 Textract를 결합한 AI 문서 검색 시스템 구조 이해

---

# 🤖 RAG(Retrieval-Augmented Generation)

## RAG란?

RAG(Retrieval-Augmented Generation)는 생성형 AI가 답변을 생성하기 전에
외부 문서(Database, PDF, 사내 문서 등)에서 관련 정보를 먼저 검색(Retrieval)한 뒤,
검색된 내용을 기반으로 답변을 생성(Generation)하는 기술이다.

기존 LLM은 학습된 데이터만을 기반으로 답변하지만,

RAG는

질문

↓

관련 문서 검색

↓

검색 결과를 LLM에 함께 전달

↓

최종 답변 생성

과정을 거친다.

---

# 왜 RAG가 필요한가?

일반적인 생성형 AI는

- 최신 정보 부족
- 기업 내부 문서 접근 불가
- Hallucination(잘못된 정보 생성)

문제가 존재한다.

RAG는 필요한 정보를 실시간으로 검색하여

- 최신 정보 활용
- 사내 문서 활용
- 정확도 향상

이 가능하다.

---

# RAG 동작 과정

1. 사용자가 질문 입력

↓

2. 질문을 Embedding으로 변환

↓

3. Vector Database에서 관련 문서 검색

↓

4. 검색된 문서를 Prompt에 포함

↓

5. LLM이 답변 생성

---

# RAG의 장점

- 최신 정보 반영 가능
- 기업 내부 데이터 활용 가능
- Hallucination 감소
- 모델 재학습 없이 새로운 문서 추가 가능

---

# Amazon Textract

## Textract란?

Amazon Textract는 OCR(Optical Character Recognition)을 기반으로

PDF, 이미지, 스캔 문서에서

- 텍스트
- 테이블
- 폼(Key-Value)
- 체크박스
- 서명

등을 자동으로 추출하는 AWS의 Document AI 서비스이다.

기존 OCR과 달리 문서의 구조까지 이해한다는 것이 가장 큰 특징이다.

---

# OCR과 Textract의 차이

기존 OCR

- 텍스트만 추출

예)

```
이름 : 홍길동
```

↓

단순 문자열

---

Textract

↓

Key : 이름

Value : 홍길동

처럼 문서 구조를 함께 인식한다.

또한

- 테이블 구조
- 체크박스
- 서명

등도 자동으로 분석할 수 있다.

---

# Textract 주요 API

## DetectDocumentText

문서의 텍스트만 추출

사용 예시

- 기사
- 이메일
- 일반 문서

---

## AnalyzeDocument

문서의 구조까지 분석

FeatureTypes

- TABLES
- FORMS
- QUERIES

를 통해

- 표
- Key-Value
- 질문 기반 정보 추출

이 가능하다.

---

## AnalyzeExpense

영수증 및 송장을 분석하여

- 상호명
- 날짜
- 총 금액
- 품목

등을 자동 추출한다.

활용 사례

- 자동 경비 처리
- ERP 연동
- 가계부 앱

---

## AnalyzeID

신분증을 분석하여

- 이름
- 생년월일
- 신분증 번호
- 만료일

등을 자동 추출한다.

활용 사례

- 비대면 계좌 개설(KYC)
- 온라인 체크인
- 렌터카 인증

---

# Textract 실습

Python(boto3 SDK)을 이용하여

- DetectDocumentText
- AnalyzeDocument

API를 호출하였다.

JSON 형태의 응답을 분석하여

- Line
- Word
- Table
- Key-Value

데이터를 확인하였다.

---

# RAG + Textract

Textract는 문서를 구조화된 데이터로 변환하고,

RAG는 변환된 문서를 검색하여

LLM이 정확한 답변을 생성하도록 도와준다.

예시

PDF 업로드

↓

Textract

↓

텍스트 추출

↓

Embedding 생성

↓

Vector DB 저장

↓

사용자 질문

↓

관련 문서 검색

↓

LLM 답변 생성

---

# 활용 사례

- 사내 문서 검색 시스템
- 계약서 질의응답
- 논문 검색
- 의료 기록 검색
- 금융 문서 분석
- 고객센터 FAQ 챗봇

---

# 💡 배운 점

- RAG는 생성형 AI의 Hallucination 문제를 줄이기 위한 대표적인 기술이며, 외부 문서를 검색하여 보다 신뢰도 높은 답변을 생성할 수 있다는 점을 이해하였다.
- Embedding과 Vector Database를 이용하여 질문과 의미적으로 유사한 문서를 검색하는 과정을 학습하였다.
- Amazon Textract는 기존 OCR과 달리 문서의 구조(테이블, 폼, 체크박스 등)를 함께 인식할 수 있어 다양한 문서 자동화 업무에 활용될 수 있음을 이해하였다.
- Python과 boto3를 이용하여 Textract API를 호출하고 문서를 구조화된 JSON 형태로 분석하는 방법을 실습하였다.
- Textract와 RAG를 함께 활용하면 PDF나 계약서, 영수증과 같은 문서를 AI가 이해하고 질의응답까지 수행하는 Document AI 시스템을 구축할 수 있음을 배웠다.
