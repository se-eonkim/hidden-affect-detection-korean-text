# 말투에 숨겨진 감정, GPT로 읽어내기
### Hidden Affect Analysis in Korean Text via GPT
> 📄 [발표자료 보기](https://github.com/se-eonkim/hidden-affect-detection-korean-text/blob/main/Hidden_Affect_Analysis__Presentation.pdf)
---

## The Problem with Existing Approaches & Research Motivation

언어는 감정을 드러내는 동시에 감춘다.  
"괜찮아"는 위로일 수도, 거리두기일 수도, 체념일 수도 있다.

감정 분석의 일반적인 접근은 두 가지다:
- 규칙 기반 — 특정 어휘 목록으로 감정을 분류
- 모델 기반 — 레이블된 데이터로 감정을 예측

둘 다 같은 한계를 공유한다:  
**표현된 감정**은 잡지만, **숨겨진 표현 전략**은 놓친다.

예를 들어, "그냥 좀 힘들었어"에서  
'힘들었어'는 감정 어휘로 잡히지만,  
'그냥'과 '좀'이 그 감정을 **의도적으로 희석**하고 있다는 건 잡히지 않는다.

이 프로젝트는 그 간극을 파고든다.

> "AI는 언어의 표면이 아닌, 표현 방식 자체를 읽을 수 있는가?"

## Web
<img width="531" height="190" alt="image" src="https://github.com/user-attachments/assets/8c2175d8-25f6-49ef-baf7-5c034fdb1dc4" />

---

## Design Rationale

감정은 문맥에 따라 다르게 숨는다.  
일기에서의 회피와 사과문에서의 회피는 구조가 다르다.

이를 포착하기 위해 세 가지 설계 원칙을 적용했다:

**1. 문맥 유형별 독립 프롬프트 스키마**  
동일한 문장도 글 유형(일기/대화/공적 글)에 따라  
다른 해석 기준을 적용해야 한다는 전제에서 출발.

**2. 언어 구조를 감정 신호로 정의**  
어휘 빈도가 아닌 문법 구조를 분석 단위로 삼음:
- 수동태 → 책임의 외재화
- "그냥", "좀" → 감정 희석 전략
- 간접 표현 → 거리두기 신호

**3. 심리학 이론을 해석 기준으로 내재화**  
GPT가 감정을 분류하는 것이 아니라  
심리학적 프레임으로 해석하도록 설계:
- Freud 방어기제 — 억압·투사·합리화 패턴
- Gross 감정 조절 모델 — 표현 억제 vs 재평가
- Speech Act 이론 — 발화의 표면 의미와 수행적 의도 분리
- 애착 유형 — 회피형·불안형 언어 패턴

---

## Analysis Output
- 감정 어휘 분류 (정서어 / 회피어)
- 감정 진심도 점수 (직접성 / 책임 명확성 / 회피 지수)
- 총평 — GPT의 언어 구조 해석

<img width="602" height="304" alt="image" src="https://github.com/user-attachments/assets/b2ba658d-99fa-4e99-9132-8ce8ec59ae62" />

<img width="605" height="306" alt="image" src="https://github.com/user-attachments/assets/2f021d96-d3f2-41db-b102-b160795204d7" />

---

## Limitations
- 긴 글은 분석 품질 저하
- 감정 해석은 맥락에 크게 좌우됨
- 정량적 검증 기준 부재

---

## Tech Stack
- Python, Streamlit, GPT API
