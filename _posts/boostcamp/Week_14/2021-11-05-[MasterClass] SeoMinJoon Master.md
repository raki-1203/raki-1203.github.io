---
title: "Day_64 [마스터클래스] 서민준 마스터"

categories:
  - Boostcamp_AI_Tech/Week_14
tags:
  - 마스터클래스
---

# [마스터클래스] 서민준 마스터

## MRC 대회 토론왕 발표 - 김은란 캠퍼

Dense Retrieval

passage_hidden_vector 의 transpose 를 진행함에 있어서 view 를 사용시 생각과 다르게 변경됨

작은 예제 코드를 활용해서 실제 transpose 의 vector 를 비교해 오류 찾기 성공

## 1등 KiYOUNG2 조 - 김태욱 캠퍼

![]({{site.url}}/assets/images/boostcamp/126f1afe.png)

elastic search 가 성능이 가장 좋아서 이걸 사용

wiki 데이터 전처리

해당 data 의 title 을 context 에 붙여줌

pororo 사용해서 question answer 새롭게 생성

query 를 변형해서 새로운 데이터 만들어줌

context 에 정답토큰을 제외하고 중요한 token 을 masking

pivot translation 을 통해 데이터를 제작

Samsung SDS 사용한 모델을 찾았네? 대단....쓰

train data 에 정답이 포함되어 있는 문장 앞 뒤에 punctuation 을 추가해줌

결과로는 별로 좋지 않았음 해당 문장에만 학습할 때 사용해서 과적합이 나지 않았나 생각해봄

## 2등 쿼터백조 - 정민지 캠퍼

preprocessing 전처리를 통해 성능이 높아짐을 확인

retrieval 는 elastic search 를 활용

shingle, stemmer 사용

pororo 를 이용해 NER tagging 을 진행

reader

wiki document 를 이용해 data 를 늘림

data augmentation 을 위해 negative sampling 을 함

정답이 없음으로 학습함

question generation title 이 같은 context 는 합쳐서 사용

질문에 답이 있는 경우는 제외

post-processing 2가지 수행

top-k passage split

answer score 계산 방식 변경

마지막 방법은 ensemble 

## 자원 발표팀 CLUE 팀 - 김강민 캠퍼 & 이종혁 캠퍼

pororo question generation task 가 있음

생성한 데이터의 검수를 하면서 의문점 발생

wiki data 에서 title 이 context 의 앞쪽에 title 이 분포하는 bias 를 확인할 수 있었음

NER 을 활용해서 뽑힌 하나의 객체를 뽑아서 질문을 생성했음

또다른 이슈가 생김

question 에 맞는 answer 가 정확히 align 되지 않는 경우가 생김

qa 모델에 사용하면 잘 못된 학습을 할거라는 생각을 했다가 pseudo labeling 을 통해서 해결해보려고 함

앙상블 후 pandas 활용해서 잘 못맞추는 json 파일은 제거해서 만듦

## 마스터 피드백 & 리뷰

### 1등 발표 피드백

approach 를 하는 방법론을 쫙 펼친게 인상깊었음

잘 안됐던 이유는 정답을 보고 정답이 포함되어있는 문장에 underline 을 해주는데 sentence 가 정답을
아는 상태로 들어가기 때문에 inference 와 train 시의 mismatch 가 발생함

답을 보지 않고도 underline 을 하는 방법을 찾는다면 좋은 가설일 것 같음

- 실제 사용할 때는 유사도를 기준으로 underline 해줬음

curriculum learning 을 진행할 때 model 이 겹치는 정도로 쉬운것을 판단한게 인상깊었음

logit(확률값)을 보는것도 있을 것 같음

logit 순서대로 쉽다고 볼 수 있음

최종적인 ensemble 이 공평하게 한 것이 잘된것도 overfitting 때문에 된 것 같음

### 2등 발표 피드백

preprocessing 을 좀 더 제대로 하는것이 잘 한 것 같음

elastic search 를 쓰면서 잘 된 이유를 생각해보자면 DPR 은 NaturalQA 에 대해서 실험했고 

SQuAD 같은 경우는 주요 실험이 아니었음 KLUE 나 KorQuAD 같은 경우는 sparse 가 더 성능이 잘 나옴

데이터 augmentation 같은 경우도 데이터가 별로 없으니 잘 사용한 것 같음

logit 2개를 더하는 것과 logit 의 확률을 곱하는건 다름

normalize 를 해준 확률을 곱하다보니 더 robust 해지는 결과가 있었던 것 같음

### 자원 발표 피드백

데이터가 워낙 작다보니 어떻게든 data augmentation 을 시켜야하고 많이 신경쓴것으로 보임

그렇기 때문에 DPR 이 data 가 적을때 잘 학습이 안되는걸 겪은 것 같음

sentencebert 를 썼을때 top-1 accuracy 가 상당히 높았음

그거에 비해 정답을 찾는게 너무 떨어져서 의문이긴 함

## 사전질문 답변

![]({{site.url}}/assets/images/boostcamp/23f1ae7f.png)

면접을 잘 볼 수 있는 방법으로는 공통적으로는 프로젝트 경험이고 그 프로젝트 경험이 resume 에 들어가있는 것임

예를들어 NLP 를 하는 팀인데 가장 중요하게 봤던 것은 BERT 를 아는 것에 끝나는게 아니라 BERT 를 사용해서
무엇을 한거에 대해서 면접에서 잘 얘기할 수 있는가가 중요

실패한 경험을 면접때 할 수 있냐 없냐는 굉장한 차이임

resume 에 그런것들이 포함되어 있는게 가장 중요함

했던 프로젝트들을 실패한거라도 제대로 고민했다라면 그거에 대해서 얘기하는 것 만큼 좋은게 없음

현업에서는 well-define 되어있는 eval metric 이나 데이터가 없는 경우가 많음

정답이 없는 경우다보니 불확실한 상황에 익숙해질 필요가 있음

나만 불확실한게 아니다라는 생각이 중요

![]({{site.url}}/assets/images/boostcamp/4291e311.png)

가장 인상깊었던 것은 스타트업에 있는 CTO 분과 연구실의 석사 한명과 함께 비디오검색 대회에 나감

input 은 text 인데 찾아내는게 video 임

재밌었던 것은 NLP 에서 text 검색에서 쓰이는 방법론들이 video 에 대해서도 잘 적용이 되었다는 점이었음

text 검색이 좀 더 발전되어있고 video 검색은 덜 발전되어 있는데 text 검색의 방법을 적용하자

두번째는 선택과 집중이었는데 대회가 video 검색 뿐만 아니라 captioning 과 qa 인데 하나만 집중하자고
전략을 세웠음

세번째는 몇천만원 정도의 예산을 사용할 수 있었는데 computer 를 사지말고 cloud 를 활용하자였음

한달반동안 8000만원을 썼음

2~3년 동안 안정적으로 돌리는게 목적이라면 컴퓨터를 사는게 맞다

짧은 기간동안 이 대회의 결과를 통해 투자를 받으려면 cloud 를 사용하는게 맞다

대회에서 retrieval 에서 1등을 했음

큰 회사들을 대상으로 잘 했던 경험임

8000만원 어치의 리소스는 어느 정도의 리소스인가요?

v100 8개 짜리가 1시간에 on-demand 로 4만원 쯤 함

gpu 100개를 200시간 돌린거라고 보면 됨

![]({{site.url}}/assets/images/boostcamp/2402846d.png)

대회가 얼만큼 유명한지가 중요한 것 같음

대회의 특성을 resume 에 써주는게 좋음 어떤 사람이 참가했고 몇명이 참가했다라는 정보를 쓰는게 좋음

요즘은 어떤 GPU 를 사용했고 얼마의 resource 를 사용했는지 적는게 좋음

![]({{site.url}}/assets/images/boostcamp/d45bbc15.png)

저도 자주 그래요 ㅎㅎ

피곤해지는게 어쩔 수 없는 것 같음

방법이 있다기보다는 원래 힘든거라고 생각하는게 좋을 것 같고 대회를 여러개 하는건 나중에 자랑할만한 일인 것 같음

8천만원을 클라우드에 투자하실때 컴퓨터를 구매했으면 우승에 실패해도 몇년간 활용할 수 있었을텐데 그래도 
클라우드로 도전하신건  되게 마스터님이든 회사든 과감한 선택이였던 것 같습니다 혹시 그 판단을 하게되었거나 
회사를 설득할 수 있었던 특별한 근거가 있었나요?  단순히 자신감만으로 대회를 잘할 수 없다는걸 이번에 뼈저리게 
느껴서 특히 궁금합니다

연구실에서 컴퓨터를 구입하고 있지 않음

서버를 구입하고 나면 3~4년 후에는 자산이 되긴하는데 당장에서는 퍼포먼스를 내기 쉽지 않음

현시점에 잘하는게 중요하다는 생각이 있어서 

스타트업 같은 경우는 정부에서 받은 지원금이 있어서 

연구실 같은 경우 올해 연구를 통해서 내년의 연구를 할 수 있어서 선순환 구조를 만들기 위해서 했고
스타트업도 마찬가지라고 생각함 6개월 길면 1년에 결과를 내야하는데 2년뒤에 금전적인 득이 된다고 하는점이
와닿지 않는다고 볼 수 있음

자신감만이라기 보다는 상황자체가 그렇게 하게 만들었던 것 같음

![]({{site.url}}/assets/images/boostcamp/5baa7881.png)

영어는 중요하다고 생각함

영어를 잘해야겠다고 생각하는 것 보다는 목적을 영어에 두지말고 수단으로서 보는게 좋은 것 같음

paper 를 보면서 모르는 단어가 나오면 그때그때 찾아보고 paper 를 보기위해서 영어를 잘해야겠다고 생각하는게
중요함

목적을 위한 수단으로서 영어를 공부하는게 효율적이라고 생각이 됨

## 마지막으로 한마디!

진짜 어려운 문제였고 기술의 발전때문이긴 하지만 여러분이 하는 문제가 2년 전에는 같은 모델을 summit 했다면
SOTA 였을것임

정말 빨리 바뀌는 거여서도 하지만 굉장히 hige-tech 를 하신거고 잘 complete 하신거는 자랑스러워 하셔도
좋을것 같음

application 영역으로 확장할 수 있는 다양한 통로가 있는 분야이기도 하고 어쨌든 NLP 에 관심이 있다면
한번쯤 해봐야하는 분야이기도하고 이 수업을 들으신 것을 후회하지 않았으면 좋겠고 앞으로 어떤 일을 하시든 특히
취업을 하실때도 도움이 되었으면 좋겠습니다.
