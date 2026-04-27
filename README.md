# 말투에 숨겨진 감정, GPT로 읽어내기
### Hidden Affect Analysis in Korean Text via GPT
> 📄 [발표자료 보기](https://github.com/se-eonkim/hidden-affect-detection-korean-text/blob/main/Hidden_Affect_Analysis__Presentation.pdf)
---

## Overview

> "AI는 인간의 무의식적 언어 전략을 어떻게 포착할까?"

언어는 감정을 드러내기도, 숨기기도 한다.  
우리는 감정을 표현하면서도 감춘다 — 수동태로 책임을 흐리고,  
"그냥", "좀"으로 감정을 희석하고, 형식으로 진심을 가린다.

이 프로젝트는 그 숨겨진 언어 전략을 GPT로 포착할 수 있는지를 탐구한다.  
단순 감정 분류가 아니라, **표현 방식 자체를 해석의 대상**으로 삼았다.


## Web
<img width="531" height="190" alt="image" src="https://github.com/user-attachments/assets/8c2175d8-25f6-49ef-baf7-5c034fdb1dc4" />

---

## Design Principle

감정은 문장 유형마다 다르게 숨는다.  
일기에서의 회피와, 사과문에서의 회피는 구조가 다르다.

→ 글 유형(일기 / 대화 / 공적 글)별로 **독립적인 프롬프트 스키마** 설계  
→ GPT가 감정을 '분류'가 아니라 **'해석'** 하도록 구성

---

## Theoretical Framework

심리학 이론을 해석 기준으로 직접 설계:

- **Freud 방어기제** — 감정 회피·투사·합리화 패턴 탐지
- **Gross 감정 조절 모델** — 표현 억제 vs 재평가 전략 구분
- **Speech Act 이론** — 발화의 표면 의미와 수행적 의도 분리
- **애착 유형 분석** — 회피형·불안형 언어 패턴 식별

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
