---
title: "[Week9] 한국어 언어 모델 학습 및 다중 과제 튜닝"
permalink: /Boostcamp_AI_Tech/Week_9/
layout: category
author_profile: true
sidebar:
    nav: "docs"
---

### [Day37] KLUE 1 ~ 2강

- [01. 인공지능과 자연어 처리]({{site.url}}/boostcamp_ai_tech/week_9/day_37/01.-AI-and-NLP/)
- [02. 자연어의 전처리]({{site.url}}/boostcamp_ai_tech/week_9/day_37/02.-Preprocessing-of-Natural-Language/)
- [오피스아워 AI 신약 개발]({{site.url}}/boostcamp_ai_tech/week_9/day_37/OfficeHour-AI-drug-development/)

### [Day38] KLUE 3 ~ 5강

- [01. BERT 언어모델 소개]({{site.url}}/boostcamp_ai_tech/week_9/day_38/01.-Introduce-BERT-Language-Model/)
- [02. 한국어 BERT 언어모델 학습]({{site.url}}/boostcamp_ai_tech/week_9/day_38/02.-Train-Korean-BERT-Language-Model/)
- [03. BERT 기반 단일 문장 분류 모델 학습]({{site.url}}/boostcamp_ai_tech/week_9/day_38/03.-single-sentence-classification-based-BERT-train/)

### [Day39] KLUE 6 ~ 7강

- [01. BERT 기반 두 문장 관계 분류 모델 학습]({{site.url}}/boostcamp_ai_tech/week_9/day_39/01.-BERT-based-two-sentence-relationship-classification-model-training/)
- [02. BERT 언어모델 기반의 문장 토큰 분류]({{site.url}}/boostcamp_ai_tech/week_9/day_39/02.-Classification-of-sentence-tokens-based-on-the-BERT-language-model/)

### [Day40] KLUE RE task 대회

- [[오피스아워] Relation Extraction]({{site.url}}/boostcamp_ai_tech/week_9/day_40/OfficeHour-Relation-Extraction/)

### [Week9 피어세션 정리](https://github.com/sangmandu/SangSangPlus/tree/main/Meet-up%20log/Week%200)

---
### 학습회고

> Day 37

한국어 전처리 과정에 대한 실습코드를 통해서 굉장히 다양한 전처리 과정을 알아봤다.

아직 대회를 위한 baseline 코드도 보지 못했지만 대회에 굉장히 많은 도움을 받을 것 같다.

오늘은 강의를 정리하는데에도 시간이 많이 흘렀는데 얼른 집중해서 baseline 코드를 돌려봐야겠다.

> Day 38

강의를 들으면서 transformers 라이브러리를 사용하는 방법에 대해 배우고 있다.

실습코드가 너무 훌륭해서 너무 좋다고 생각한다.

얼른 baseline 코드를 수정해서 실험에 알맞게 변경하고 많은 시도를 해보고 싶다.

baseline 코드에서 xlm-roberta-large 모델을 돌려놓고 내일 테스트해보려한다.

20 epoch 돌리는데 8시간40분정도 걸린다. 

돌리는 동안 EDA 나 해봐야겠다.

> Day 39

6 ~ 7 강을 들으면서 BERT 모델을 활용해서 다양한 task 를 진행하는데에 필요하고 중요한 것은 데이터셋을 어떻게 
만들것이냐와 tokenizer 를 어떻게 사용할 것인가였다.

부스트캠프에 오기전 정말 궁금했던 내용들이 쫙 풀리는 신세계를 경험했다.

한방에 모든 task 에 대해서 잘 할 수는 없겠지만 실습코드를 보면서 차차 익혀나가면 언젠가 나도 NLP 전문가가 되어 있지
않을까 하는 생각을 해보게 된다.

대회 얘기로 넘어가면 대회 데이터를 가지고 EDA 를 어제부터 시작했다.

EDA 를 하다가 문득 새로운 아이디어가 떠올랐다.

![]({{site.url}}/assets/images/5b2ea144.png)

class 간 불균형이 엄청나게 심해보인다는 것이었다.

마스크 이미지 분류 대회에서도 클래스간 불균형이 심했는데 원래 그렇겠거니 하고 그냥 학습시켰었는데 이번엔 다른 방법을
써봐야겠다고 생각했다.

그래서 세운 하나의 가설은 no_relation vs org vs per 이렇게 3가지를 먼저 분류하는 모델을 만들어보는 것이다.

![]({{site.url}}/assets/images/d218291e.png)

이 3개의 클래스는 그래도 불균형의 정도가 완화되는 것처럼 보였다.

그런 뒤에 org 로 예측한 데이터에 대해서 다시 한번 org 의 세부 클래스를 예측하는 모델을 만들어보려한다.

![]({{site.url}}/assets/images/268d04df.png)

org 의 세부 클래스들도 물론 불균형이 있지만 30개의 label 을 분류하는 것보다는 이게 더 쉬울거라고 생각했다.

per 에도 마찬가지로 시각화를 하면 

![]({{site.url}}/assets/images/b32e178d.png)

이런 식의 분포를 띄고 있었고 확신할 순 없지만 시도해 볼 만한 가치가 있다고 생각한다.

이제 이 EDA 를 통해서 이런 아이디어를 발견했으니 baseline 코드를 수정해서 적용해봐야겠다.

> Day 40

Baseline 코드를 내 입맛에 맞게 다 뜯어고쳤다.

하루의 시간을 사용했지만 huggingface 에 대해서 이렇게 저렇게 내가 쓰고 싶은 기능을 추가해가면서 해보니 재밌었다.

저번 image classifcation 대회에서는 사용을 잘 해보지 못했던 wandb 를 Trainer 에서 사용하는 방법을 적용했다.

wandb 에서 train 이 도는 동안 자동으로 기록들을 관리해줘서 편할거라고 생각한다.

앞으로 내가 해볼 실험들과 결과들이 자동으로 저장될테니 아무 걱정없이 사용하려한다.

오늘은 강의를 미리 다 듣고서 실습문제도 풀어보려했는데 baseline 코드에 시간을 너무 많이 사용해서 원하는 실험으로
학습을 실행해놓고 실습코드도 다시 한번 훑어봐야겠다.

다들 왜저리 잘하는지 궁금하다.

얼른 쫓아가고 싶고 나만의 방법으로 좋은 성능이 나는 결과를 맡보고 싶다. ㅎㅎ

나의 가설이 맞기를!! 기대해본다.




