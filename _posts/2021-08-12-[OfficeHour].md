---
title: "Day_9 오피스아워 (과제해설) - 이주용, 이하경, 류영표 멘토"

categories:
  - Boostcamp_AI_Tech/Week_2/Day_9
tags:
  - 오피스아워
---

# 오피스아워 (과제해설) - 이주용, 이하경, 류영표 멘토

## 선택과제 해설 session

> 선택과제 guide 들어가며

- 선택과제는 지금 다 해야한다는 아니다.
- 현업에서 많이 쓰이고 있는 Trend

1. 논문에서 제안하는 모델과 나온 수식들을 어떻게 코드로 옮긴느지, 직간접적으로 경험해보는 것만 해도 아주 좋은 공부
2. 논문구현은 주위 석박사생들도 어려워하는 작업이라, 아직 PyTorch 강의도 제대로 못들으신 상황에 너무 낙심할 필요 절대 없습니다.
3. 물론, 코스 전체 기간이 끝날때는 전부 소화시킬 수 있게 절대 포기하지 마세요.
(강의 및 과제 구성이 어디가서 찾기 힘들 정도로 정말 좋습니다.)

### 선택과제 1) Vision Transformer - intro

- 선택 이유?
  - 대부분의 이미지넷 sota 모델이 VIT거나 Transforemr 기반으로 되어있음

- 이미지를 9개의 patch로 나누는 작업을 먼저 진행
  - self.rearrange = Rearrange('b c (num_w p1) (num_h p2) -> b (num_w num_h) (p1 p2 c) ', p1=patch_size, p2=patch_size)
  - patch로 나누는 코드

- 너무 어려움 이해가 안됨...........

### 선택과제 2) Adversarial autoencoder

- AutoEncoder
  - 레이블이 없는 데이터로 학습하는 unsupervised learning

- 뭔소린지........

### 선택과제 3) Mixture Density Network

- Uniform 분포는 모든 분포를 만들 수 있음
- 다봉 분포에는 mixture model을 씀
- 가장 대표적인데 GMM
- 복잡한 데이터는 우리가 알고 있는 분포로는 fitting이 안됨

---
# Q&A

> 딥러닝 시작할 때 어떤 논문 위주로 시작하면 좋을지 궁금합니다.

- RNN -> LSTM -> GRU -> Transformer

> 아직 딥러닝에 대해 감이 안잡히는데 하나하나 이해하기 보다는 일단 해보는게 중요할까요?

- 쉬운거부터 하나하나 이해하는게 중요할 듯
- 해보는건 당연히 중요하고 그러면서 하나하나 이해하는게 중요

> 공부한 걸 정리할 때 어떤 매체에, 어느 기준으로 (날짜별/항목별 등) 정리하셨는지 궁금

- notion 같은거 몰랐을 때 excel로 정리
- 요즘은 notion이나 github blog에 정리하고 있음
- ipad 에 논문을 정리해서 심심할 때 읽고 정리

> 이해가 안되는 문제를 만났을 때 바로 질문하는 편이신가요? 아니면 몇 날이고 찾아보다가 질문하시는 편이신가요?

- 원래는 바로 질문을 했었다가 그러면 안되는걸 깨닫고 찾아보다가 질문
- 시간을 투자하는 만큼 재산이 되는 것 같아서 찾아보긴 함
- 디버깅은 하루정도 혼자 투자하고 수식이나 이런 것들은 한두시간 투자하다가 물어봄
- 캠프를 듣는 시간내에 많이 질문하는게 좋은 듯

> 지금 캠퍼가 됐다면?

- 옆에 사람과 비교하지 말 것
- 강의를 미루지 말 것

> 회사에 갔다가 다시 학교로 돌아가는것에 대해?

- 훨신 더 시간을 save 하는 거라고 생각
- 스킬을 쌓고 박사과정을 듣는 것이기 때문에 더 많이 도움이 된다고 생각함
  - 아는 분이 일을 하다보니 어떤 분야랑 어떤 연구를 주제로 정해야 될지 많이 잡혔다고 해서 박사학위를 준비

> 실제 현업에서는 어느 정도의 모델을 사용하는지 궁금

- facebook data center infra team 에서 GPU center를 짓고 있는데 큰 모델을 training 하고 큰 모델을 research 하기 위해서 짓고 있음
- 현업에서는 서비스하기 쉬운 모델을 사용하지만 
- 큰 리소스를 요구하는 모델들을 많이 연구하는 추세

> 아직 PyTorch에 익숙하지 않아 예시를 보고 따라하는 식의 구현은 얼추 따라할 수 있지만 zero-base부터 구현하라고 하면 아직 고민이 많이 됩니다. 이번주 예제들을 복기해보는 방식으로 공부를 하고 있는데 혹시 도전할만한 다른 데이터셋과 문제같은게 준비된 사이트들이 있을까요?

- 캐글이나 데이콘
- 너무 조급해하지 말고 부스트캠프에서 진행하는 P-stage 잘 따라가면 될 것 같다는 생각
- 다음주에 PyTorch 강의가 준비되어 있으니 조급해하지 말기

---
## 최근 동향

- Transformer 가 계속 사용 중




