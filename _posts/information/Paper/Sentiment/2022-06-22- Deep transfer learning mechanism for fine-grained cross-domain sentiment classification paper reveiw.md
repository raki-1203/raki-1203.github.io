---
title: "Deep transfer learning mechanism for fine-grained cross-domain sentiment classification"

categories:
  - Sentiment
tags:
  - Paper
---
  
# Deep transfer learning mechanism for fine-grained cross-domain sentiment classification paper review

CONNECTION SCIENCE - 2021

[Deep transfer learning mechanism for fine-grained cross-domain sentiment classification](https://www.tandfonline.com/doi/full/10.1080/09540091.2021.1912711)

cross-domain sentiment classification 이란 target domain 에서 감정의 정도 분류를 돕기위해 source domain 에서 
유용한 정보를 이용하는 것임

상대적으로 적은 target domain data 에 대해서 분류 성능을 향상시키기 위해 양이 많은 source domain data 를 이용해서 
유용한 정보를 얻어내고 전이시키는 방법에 대한 논문임

## 1. 저자가 뭘 해내고 싶어했는가?

존재하는 방법들의 대부분은 source domain 과 target domain 사이의 변하지 않는 특징을 뽑아내는 것에 집중함 

하지만 이런 방법들은 target domain 에서 레이블이 없는 데이터를 더 잘 활용할 수 없음

이런 문제를 해결하기 위해, 세분화된 cross-domain sentiment classification 을 위한 
Deep Transfer Learning Mechanism(DTLM) 을 소개함

## 2. 이 연구의 접근에서 중요한 요소는 무엇인가?

### Contributions

1. context 를 인코딩하기 위해 사전학습된 BERT 를 사용하고 두개의 domain 사이의 feature 적응 문제를 해결하기 위한
수단으로서 KL Divergence 방법을 사용
2. target domain 에서의 label 이 없는 샘플을 처리하고 모델이 보지 못한 데이터에 대해서 일반화 능력을 강화하기 위해 
**entropy minimisation, semi-supervised learning 방법 그리고 consistency regularisation 을 소개**
3. 풍부한 양의 source domain 으로부터 학습된 지식을 이용하고 target domain 에서 부족한 label 된 데이터의 문제를 
해결하기 위해 soruce domain 으로 ACSA(Aspect-Category Sentiment Analysis) 데이터셋을 사용

### Main Idea

#### Sentiment Classifier

세분화된 감성 분석 task 는 source domain 에 대한 aspect 에 기반함

이 때, aspect 는 이 두개의 논문에서 제안된 모델을 사용해서 추출한다고 함 

- [Aspect Term Extraction with History Attention and Selective Transformation(2018)](https://arxiv.org/abs/1805.00760)
- [Hierarchical Attention Transfer Network for Cross-Domain Sentiment Classification(2018)](https://ojs.aaai.org/index.php/AAAI/article/view/12055)

BERT 는 다른 domain 의 text data 를 공유된 feature space 로 매핑하기 위한 feature encoder 로서 소개됨

세분화된 감성 분석 task 를 BERT 에 적용하기 위해, aspect 와 category 는 review text 와 결합된 "sentence" (문장)으로서 
여겨짐

그리고 두 문장(aspect 와 category(문장 1), review text(문장 1)) 사이의 "relationship" (관계) (감정의 정도)를 
예측하는 것으로 변환됨

![](../../../../assets/images/paper/sentiment/e4578eda.png)

위 그림에서 볼 수 있듯이 

`[CLS] tokenized Review [SEP] tokenized Aspect`

이와 같은 형태로 입력이 들어가고 마지막 hidden state 들 중 [CLS] 토큰 위치의 `C` 를 이용해 Sentiment classifier 를 
통과시킴

이 때, 예측값과 실제값 사이의 차이인 cross-entropy loss 를 최소화 시키면서 모델을 최적화함

#### Domain-adaptive model

cross-domain 문제에서 학습 데이터와 테스트 데이터는 IID(Independent and Identical Distribution) 가정을 만족시키지
못할 수 있고 이 두 샘플은 다르지만 관련이 있음

다른 domain 은 다른 feature space 분포를 가지기 때문에, cross-domain 구현의 열쇠는 source domain 과 target domain 
사이의 차이점을 제거하는 것임

계산을 단순화하기 위해, embedding space 에서 sample feature 분포의 평균값의 거리를 계산하기 위한 KL divergence 를 
사용함

![](../../../../assets/images/paper/sentiment/fe05d0a2.png)

작성중입니다.







