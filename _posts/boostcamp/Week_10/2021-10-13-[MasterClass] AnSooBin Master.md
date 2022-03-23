---
title: "Day_47 [마스터클래스] 안수빈 마스터"

categories:
  - Boostcamp_AI_Tech/Week_11/Day_47
tags:
  - 마스터클래스
---

# [마스터클래스] 안수빈 마스터

** 시각화(+HCK) 연구??

시각화는 무엇을 연구하나요? ~~(시각화도 연구할 게 있나요?)~~

- **시각화**, 이쁘고 AI 와 다르게 '디자인'스럽고 재미는 있는데...
  - 실제로 도움이 되는 시각화는 어떤 것이 있고, 어떻게 해야할까?
  - 어떻게 연구로 확장할 수 있을까?
- AI 논문을 읽기만 하다 ... 관련 논문을 쓰는 입장이 되니 바뀌는 시야!
- 시각화 대표 학회인 IEEE VIS 를 통해 시각화 연구를 가볍게 소개한다.

## 시각화란?

![]({{site.url}}/assets/images/boostcamp/0b205477.png)

## $M^2$Lens: Visualizing and Explaining Multimodal Models for Sentiment Analysis

![]({{site.url}}/assets/images/boostcamp/d904ffa3.png)

기존 AI 논문은 모델을 만들고 모델의 결과가 다른 모델보다 좋다는 것을 table 로 만들어 비교분석한다면 
Vis 논문은 이 시각화가 왜 필요한지를 기술함

## Introduction + Background (1)

리뷰어에게 설득해보기

- 이 논문이 **풀고자 하는 문제가 중요**한 이유 (다양한 어플리케이션)
  - 관련 학회의 논문 수 등에 대한 통계치 사용
- 기존에 풀던 방식과 **현 논문이 푸는 방식이 다른 점** (기존 논문의 한계점)
- 문제를 푸는 기술의 전문성 (이 분야에 최신 기술을 도입했다!)
  - 실제 해당 분야의 전문가가 긍정적을 인터뷰 함

## Introduction + Background (2)

- Sentiment Analysis
  - Customer analysis / Social Robots / Political Campaings
- Unimodal 과 Multimocal 이 다름
  - channel 에서 발생할 수 있는 interaction 이 존재
  - Video / Text / Audio / 고차원 데이터를 살피기 어려움
  - 특히나 다른 타입간의 interaction 을 dominance, complement, conflict 로 나뉘어 본다.
- 전문가 인터뷰(domain experts)를 진행함

## Design Requirements (1)

풀고자 하는 문제를 구체화하자.

- 문제를 구체화하는 방법은 다양하다.
- 내가 중요하다고 생각한다!는 전혀 설득력이 없다.
- 가장 좋은 설득력은 **실제 사용자에 대한 인터뷰** 이다.
- 어떤 점을 뽑아야 하나
  - Goal : 하고 싶은 목표(예.. developer 와 user 의 이해를 돕고 싶다.)
  - Task : 목표를 이루기 위해 해야하는 일(모델의 성능 확인)
  - Requirements : 시스템이 만족해야 하는 상황(예. 모델의 성능을 확인할 수 있어야 한다.)
  - 일반적으로 3개 이상의 Task 나 Requirements 를 정의하고 시작한다.

## Design Requirements (2)

- **To understand user's general needs and formulate design requirements**, we surveyed
**prior visualization techniques for interpreting machine learning models** [2, 3, 7, 10,
26, 31, 32, 39, 53, 83] and multimodal language analysis [4, 41, 69, 70, 76, 79]. Also,
**we worked closely with a researcher in NLP** and multimodal machine learning (who is also a
coauthor of this paper) for about **five months to collect his feedback and iteratively refine 
the design requirements**

## Design Requirements (3)

- **R1 : Show the model performance**
  - Q1 : What are the overall error distributions for model predictions?
  - Q2 : What are the instances that are predicted with large/small errors?
- **R2 : Reveal the contributions of modalities to the model predictions**
  - Q3 : How does each modality influence  the model predictions?
  - Q4 : Which modalities dominate the model predictions?
  - Q5 : How do dominant/complementary/confliciting modalities influence the model predictions?
- **R3 : Identify the influences of multimodal features for the model predictions**
  - Q6 : What are the feature sets that significantly contribute to positive/negative sentiment predictions
  - Q7 : What features are considered important by the model? Are they plausible for prediction?
- **R4 : Support multi-level and multi-faceted exploration of the multimodal model behaviros**


## System (1)

Requirements 를 어떤 식으로 만족시켰는가?

![]({{site.url}}/assets/images/boostcamp/8d5a5455.png)

시각화 시스템은 interactive 를 제공해야하고 항상 좌측에 있는 메뉴바나 상단에 있는 메뉴바를 사용해서 사용자가
선택할 수 있게 만들어둠

여러가지 view 를 통해서 결과들을 보여줌

## System (2)

![]({{site.url}}/assets/images/boostcamp/6ca410de.png)

## System (3)

![]({{site.url}}/assets/images/boostcamp/92a0f4f6.png)

## System (4)

![]({{site.url}}/assets/images/boostcamp/cfc33072.png)

![]({{site.url}}/assets/images/boostcamp/d60c0c43.png)

T-SNE 로 시각화함

전문가들은 zoom-in, zoom-out 해서 보니 도움이 되었다라는 의견 있음

## Evaluation (1)

정당성을 증명하기 위한 가장 중요한 과정

- 실험 참가자는 누구인가? (Participants)
  - Domain Expert / General users / AMT 등 ...
- 어떤 Task 로 실험을 진행했는가? (Task & Dataset)
  - 비교군, Within / Between 등에 대한 고려
- 어떤 순서대로 실험을 진행했는가? (Procedure)
- 평가를 어떻게 진행했는가? (Measure)
  - 정성평가 / 정량평가
  - 측정된 값을 어떤 통계를 지니는가 (Result)
- **이 모든 것을 통해 얻은 결론이 무엇인가?**

## Evaluation (2)

System workflow / Visual designs and interactions / Improvement

![]({{site.url}}/assets/images/boostcamp/e2ad084a.png)

## 시각화(HCI) 논문의 즐거움!

User-centered Research!

- HCI/VIS 분야의 논문을 읽으면 얻는 장점
  - Problem solving 이 아닌 Problem 제시부터 이를 풀어가는 과정
  - 실사용자와 가까운 연구 / 산업과의 연결
  - 다양한 분야 적용
  - 시각적 즐거움
    - 물론 디자인을 못해도 괜찮습니다. 방법론 초점 연구도 많습니다!
- **좀 더 시야를 넓혀 덕업일치하는 AI Researcher / AI Developer 가 되시길 바랍니다**

--- 

# Q&A

![]({{site.url}}/assets/images/boostcamp/043fac04.png)

배운 것이 소용없어질 일은 전혀 없을 거다라고 생각하고 시각화와 AI 쪽을 연결하는일이 굉장히 어렵다고 생각함  
실제로 EDA 를 하는것과 모델링을 하는거는 전혀 다름  
우리가 정말 아무것도 알 수 없을 때 데이터의 특징들을 살펴보는 bottom-up 방식이 있고  
두번째는 결과가 안나오는 것 같은데 question based 인 방법이 있는데 강의에서는 bottom-up 방식이어서  
top-down 시각화 강의는 어려운 것이 너무 대회나 데이터에따라서 분야에 specific 하기 때문에 질문하는 방법을 잘 해야한다고 생각함  
질문을 잘하는 방법은 kaggle 이나 Dacon 에서 feature engineering 을 잘 하는 solution 을 많이 봐야한다고 생각함  
솔루션을 봤는데 구현할 수 없으면 안되니까 bottom-up 도 잘 알아야하고 항상 우수 solultion 을 많이 봐야한다고 생각함

![]({{site.url}}/assets/images/boostcamp/eb9aba8e.png)

1) https://www.kaggle.com/subinium/awesome-visualization-with-titanic-dataset
   - 색과 여백을 잘 활용해서 나만의 시각화를 만들었어서 추천
2) https://www.kaggle.com/subinium/tps-aug-simple-eda
   - 사람들이 진짜로 원하는 EDA 가 뭘까를 고민하면서 대회에 참가했을 때 가장 필요하다고 생각된 시각화라고 생각해서 추천

![]({{site.url}}/assets/images/boostcamp/dc89eecb.png)

지금 대학원에서 진행하고 있는 프로젝트를 좋아함  
지금 하고 있는게 구글이나 유튜브보면 AI 컨텐츠가 너무 많은데 이 컨텐츠만 잘 활용해도 AI 를 잘 할 수 있다라는 생각으로 시작한 프로젝트이고 
이런 프로젝트보다 중요한것은 내가 어떤 사람에게 기여할 수 있느냐가 중요한데 교육쪽이 중요하다고 생각함

그래서 요새는 카카오프로젝트에 굉장히 집중하고 있음

![]({{site.url}}/assets/images/boostcamp/f924e94f.png)

포트폴리오보다 이력서, CV 를 작성하는데 overlink 해서 태그로 관리하고 있고 이력서는 git 에서 관리하고 있음 
[링크](https://github.com/subinium/CV/blob/master/CV.pdf)

추천드리는 글은 우아한형제들 에서 쓴 [링크](https://techblog.woowahan.com/2531/) 를 추천함

본인이 얼마나 이 분야에대해서 생각이 깊은지와 협업을 잘하는지에 대해서 보니 열심히하면 안되는 사람은 없다고 생각함

어차피 요새는 경력의미없고 코딩테스트 통과한다음에 면접해보면 이 사람이 얼마나 잘하는지 보임

![]({{site.url}}/assets/images/boostcamp/5214a2e0.png)

궁금한점에 대해서 육하원칙으로 다 써봄  
일단 줄글로쓰고 어떤 부분을 모르겠고 어떤부분이 왜 이해가 안되는거같고 어떤 부분이 다른 사례가 있을 것 같고 이런 정보들을 다 써보고
공통점을 찾는 편

전체적인 information 에 대해서 structure 를 못만든다고 생각이되는데 많은 정보를 읽는게 도움이 된다고 생각함

너무 text 를 안읽고 단편적인 정보를 받다보니까 전반적인 정보를 구조화 못시키는 것 같고 좋은 글을 많이 읽었으면 좋겠고 좋은 글은 책이라고 생각함

> 강연을 들으면서, 논문의 시각화가 모델이 어떻게 작동하는지 조금 더 잘 이해할 수 있도록 도와준다는 면에서 XAI가 떠올랐는데, 
> HCI, Viz 분야에서 AI 관련 키워드로 진행되는 연구는 보통 XAI에 관한 연구인지 궁금합니다!

보통은 XAI 연구로 진행되고 어떻게 하면 시각화로 보조할 것인가로 연구가 많이 진행되고 있고 그래도 XAI 가 더 위주인 것 같음

![]({{site.url}}/assets/images/boostcamp/341779aa.png)

현업 developer 들은 Matplotlib 을 잘 쓰는 사람은 별로 없다고 보고 오히려 wandb 같은 경우가 이런 상황을 targeting 해서 만든 것인데
기획단 분들에게는 어떤 것을 줘도 상관이 없음 그 분들은 개발자를 많이 상대하는 분들이라서 matplotlib 을 사용해도 되고 다른 것을 사용해도 되지만
그 안에 있는 내용들이 중요함 라인, 축이 의미하는게 어떤것인지 명확한게 중요함

개발자는 회사마다 어떤걸 정해서 사용하는 것 같음

visual component 가 있고 이해하는데 필요한 요소가 무엇인지를 더 이해하는 것이 좋은 것 같음

> UI/UX 디자인이 중요하듯이 자기를 판다는 관점에서 깃허브 readme 프로필을 시각적으로 멋있게 꾸며보고 싶지만, 아이디어가 잘 떠오르지 않습니다. 
> 마스터님은 아이디어가 떠오르지 않으실 때 보통 어떤 것에서 영감을 받으시는지 궁금합니다. 그리고 괜찮은 디자인 소스들을 얻을 수 있는 곳 중에 
> 추천해주실만한 플랫폼이나 사이트가 있는지 궁금합니다!

github 프로필은 멋있어보이지만 그냥 정형화되어있음

지나치게 많이 꾸미는 것에 대해서 부정적임

한게 없는데 과장하면 좀 부끄러움 그래서 사람들이 사용하는 
[배지 리스트](https://github.com/subinium/Misc-Cheatsheet/blob/master/web/github.md)를 만들어놔서 사용하는 편임

시각화에서 유명한 교수님이 계신데 [이 분 github page](https://github.com/rougier)을 보면서 잘 꾸며야지라고 생각함

> 시각화는 왜 조금씩 다른 라이브러리가 많을까요....
사용법도 미묘하게 다르고 장단점도 있어서... 확실히 좋은 무언가가 있어서 그거 하나로 통일했으면 좋겠는데...

오히려 하나로 통일되면 복잡해서 못 쓰는 사람이 생긴다고 함

파이썬의 특징인것 같기도 함

> (시각화와 직접적으로 관련된 질문은 아니지만) 채용시장에서 엔지니어와 리서치의 경계가 모호해서 방향을 잡기 어렵다고 느꼈습니다. 
> 인턴을 하실때 ML파트의 포지션이 어떤 식으로 구성되어있는지 여쭤보고 싶습니다!

네카라쿠배에서는 완전히 research 를 하는 분들은 없었던 것 같음

완벽하게 research 를 하는분들은 소수인 것 같고 본인이 하고 싶은게 뭔지를 아는게 중요한 것 같음

정말 실력이 있으면 원하는 research 가 있다면 걸 회사의 방향과 비슷한걸로 하게해줌

