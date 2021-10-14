---
title: "Day_48 [오피스아워] 강의 설계 의도 및 AMA(Ask Me Anything)"

categories:
  - Boostcamp_AI_Tech/Week_11/Day_48
tags:
  - 오피스아워
---
  
# [오피스아워]  강의 설계 의도 및 AMA(Ask Me Anything) - 조대현 멘토

## 성능을 올리고 싶은가요?

![]({{site.url}}/assets/images/12a85acf.png)

passage 를 무한정 늘리면 또 안되고 적당히 늘려야 하는듯

generation 과 extraction 을 앙상블 할 수 있음

두가지로 해석될 수 있음

output 들이 있을 때 여러가지 모델을 앙상ㅂ르할 때 extraction 결과랑 generation 결과가 나오면 
BLEU 스코어 같은 걸로 필터링할수도 있고 룰베이스로 걸러서 어떤 모델꺼를 선택할지를 정하는 방법

extraction 과 generation 모델을 단일모델로 합칠 수 있음

두가지 loss function 을 한번에 모델이 쓸 수 있음

extraction base 나 generation base 모두 encoder 를 사용하기때문에 

두가지 모델의 backpropagation 을 하나로 묶을 수 있기때문에 시도해보면 좋을 것 같음

## 2. 미세먼지

### 2.1 black

![]({{site.url}}/assets/images/b4cd6e4c.png)

알아서 엔터도 해주고 ''도 바꿔주고 등등

### 2.2 github .

![]({{site.url}}/assets/images/e396f3f0.png)

깃허브 페이지에서 . 을 누르면 직접 수정할 수 있음

소스코드 까볼때 아주 좋음

![]({{site.url}}/assets/images/ea5ffc19.png)

### 2.3 Arguments + Dataclass

![]({{site.url}}/assets/images/b30dafad.png)

![]({{site.url}}/assets/images/38c0e93a.png)

![]({{site.url}}/assets/images/ee6aaa2a.png)

![]({{site.url}}/assets/images/afb3c43a.png)

### 2.4 Contextmanager

![]({{site.url}}/assets/images/c884e76d.png)

![]({{site.url}}/assets/images/1f48178b.png)

![]({{site.url}}/assets/images/7dd42ec6.png)

![]({{site.url}}/assets/images/869f0a62.png)

![]({{site.url}}/assets/images/af68efdc.png)

![]({{site.url}}/assets/images/9743df5d.png)

![]({{site.url}}/assets/images/8f616330.png)

![]({{site.url}}/assets/images/d478c68e.png)

---

# 사전질문

![]({{site.url}}/assets/images/7371cb40.png)

QA 라는 task 자체를 푸는게 한정되어 있음

그래서 리팩토링할 때 모델의 구조변경이나 이런 것들이 어려울 수 있음

기존의 QA 푸는 방식을 그대로 사용하되 굉장히 다양한 generative 모델과 extraction 모델을 만들어서 앙상블하는걸 추천함

baseline 코드가 너무나 어렵거나 문제가 있는건 아니기 때문에 추가할 수 있을 것 같음

BERT 위에 linear layer 2개를 쌓아서 start token 을 뽑고 end token 을 뽑고 하는걸 바꾸는건 쉽지않음

왜냐면 QA 에서 무조건 사용해야하기 때문에

참고자료는 아까 소개한 주소들을 보면 좋을 것 같음

![]({{site.url}}/assets/images/549bc9e8.png)

paperswithcode 를 확인해보면 뭔가 architecture 를 새롭게 제안하기보다는 기존의 모델의 사이즈를 키워서 잘 풀었어라는 논문이 많음

새로운 architecture 를 찾기는 쉽지 않음

그런데 찾아볼 코드들은 여기 사이트에서 찾아보면 됨

다른 task 에서부터 정보를 가져와서 사용할수도 있음

MRC 슬랙 채널에 MRC 모델 이외의 걸 사용해서 여러가지 task 를 풀 수 있도록 모델을 사용할 수 있음

MRC Challenge 에서 korquad 로 fine-tuning 된 것은 허용할 것 같음

기학습 가중치가 제한이 없기 때문에 korquad 로 fine-tuning 된 모델을 사용해도 됨

MRC 모델 이외의 inference 하는것도 가능함









