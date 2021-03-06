---
title: "Day_33 [오피스아워] NLP 선택과제 해설"

categories:
  - Boostcamp_AI_Tech/Week_7
tags:
  - 오피스아워
---
  
# [오피스아워] NLP 선택과제 해설 - 문영기 멘토님

대학원을 굳이 갈 필요는 없다 그러나 실력은 중요하다

AI 분야는 공부를 하는 만큼 대우나 연봉이 달라짐

## 필수과제 4번

`from typing import List, Dict, Uple, Sequence, Any`

파이썬 코드의 가장 큰 장점은 코드를 만들기 쉽다는 장점이 있음

동적타이핑이 가능함

그렇지만 문제는 코드만 봤을 때 이 코드가 어떻게 작동되는지 알 수 없음

코드를 돌려보거나 간단히 찍어보는 방법으로 알아보게 되는데

Type Hint 를 써줌으로써 이런 문제를 해결 가능

클래스나 함수 만들 때 input 이 뭐고 output 이 뭔지를 알려주는 용도

코드를 혼자보지 않기 때문에 Type Hint 를 쓰는게 좋음

좋은 코드는 주석없이 이해할 수 있는 코드가 좋은 코드

많은 사람들과 협업을 하기 때문에

![]({{site.url}}/assets/images/boostcamp/40c39d1b.png)

idx2word 를 list 로 만들었는데 dictionary 로 만들어도 됨

word2idx 는 Dictionary 인데 key 가 string 이고 value 는 integer 이다.

이런 느낌임

선택으로 List Comprehension 을 활용해서 짧은 코드를 작성해보세요 라는 문제가 있는데

대용량 데이터를 처리할 때 List Comprehension 을 많이 사용

Bucketing

계산할 수 있는 computing resource 를 아낄 수 있음

조심해야할 것은 test 에 따라서는 bucketing 을 해서 성능이 저하될 수 있음

문장의 길이가 비슷한 문장은 비슷한 의미를 가지게 되면 

bucketing 끼리는 의미가 비슷한 현상이 일어날 수 있음

그런 경우에서는 성능이 떨어질 수 있음

일정한 sequence 가 비슷한 애들끼리 뭉쳐놓는 방법 말고 bucket 을 만드는 방법이 있음

특정 길이를 기준으로 정규분포해서 그 길이에 맞게 bucket 을 만든다던지 하는 경우가 있음

이걸 하는 이유는 bucketing 을 했을 때 성능이 떨어지는 경우가 있기 떄문

Collate Function

배치마다 패딩을 적절하게 넣을 수 있게끔 해

모든 배치에 대해서 max_length 를 고정해 두면 계산이 비효율적일 수 있음

각 배치마다 max_length 를 능동적으로 잡아주는 역할을 하는게 collate_function 이라고

이해하면 됨

## 선택과제 3번

out of vocabulary 문제가 모델의 성능을 좌우하는 문제라고 할 수 있음

알아서 잘 만들면 됨

## 선택과제 2번

fairseq 은 잘 쓰지 않음

CLI argument 가 너무 많아짐

## 선택과제 1번

datasets 허깅페이스에서 데이터만을 처리한 라이브러리를 만듦

데이터 전처리하는 파이프라인을 불러올 수 있음

지금 모델에서는 DistilBert 를 사용함

![]({{site.url}}/assets/images/boostcamp/66c1f20f.png)

distilBERT 말고 다른걸 써보고 싶으면 hugging face 에서 검색해서 사용하면 됨

training arguments 와 config 는 다름

docs 들어가서 Models 에서 configuration 을 잘 찾아서 모델을 구성하면 됨

토크나이징에 대해서는 sub-word 로도 끊어보고 음절로도 끊어서 해보면 좋을 듯

---

공부를 하는 이유는 각자의 행복을 위해서 하는건데

AI 분야에서는 내가 열심히해서 좋은 성과를 얻어내서 조직에서 좋은 평가를 받고

연봉이 올라가고 연봉이 올라가면서 입소문이 나면서 누구한테 멘토링을 해달라

강의르 해달라 책을 써달라 라는 요청을 받게되면 돈이 많이 벌리고

재밌어지고 하면서 점점 더 빠져들게 됨

그런데 이렇게 빠져들다보면 사람이 각박해질 수 있음

점점 더 신경질적이 된다거나 그런 등등

이런 징조가 있다면 조심

이거 안하면 안될 것 같다는 강박이 생기게 되면 

쉬는게 자연스러워야 하는데 모든게 일처럼 되는 때가 오는데

모든 일이 일처럼 되는 그런 상황이 올수도 있음

그렇게 될 수도 있다는걸 미리 인지하고 조심

진짜 Top class 의 사람들은 언제나 밝고 친절하고 웃고 있더라

그래서 다들 웃고있으면 좋겠음

이런 경우가 온다면 빠르게 심리상담이나 친구들과 상담을 하면서 푸는게 좋을 듯

---

협업을 하기 위한 마음가짐에는 내가 틀릴 수 있다라는 마음가짐

내가 잘하는 사람이 되어서 잘하는 사람과 일하는게 Best 그러면 협업이 틀어질 일이 없음

그런데 지금 할 수 있는 것은 아침마다 미팅을 하는게 좋음

규칙을 정해서 누가 안한다하면 뭐라한다던지, 

또는 무조건적인 반대가 아니라 이런저러한 설명과 함께 다른 방안을 추천 

감정에 휩싸이면 안됨

---

공부를 효율적으로 하는 것도 중요하지만 마음속에서 이거는 알아야 할 것 같은데 시간이 없으니
지금은 넘어가자라고 생각하는 것들을 해보는게 좋음

모든 회사나 기업들은 잘하는 사람을 뽑고 싶어함

점수를 잘 맞은 사람이 아니라

그러면 잘하는 사람은 누구냐?

스스로 공부를 깊게 깊게 해서 그런 루틴을 가지고 있는 사람이고

이런 사람이 창의적이고 잘하는 사람이라고 생각함







