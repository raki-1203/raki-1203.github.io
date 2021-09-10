---
title: "Day_20 [오피스아워] Image classificaion 경진대회 solution 공유"

categories:
  - Boostcamp_AI_Tech/Week_5/Day_20
tags:
  - 오피스아워
---

# [오피스아워] Image classificaion 경진대회 solution 공유

## 아이디어를 실현할 방법론은 어떻게 탐색하셨나요?

- 어디서 들었던 적이 있어서 생각이 남
- Naver 에서 비슷한 해커톤 대회가 있었음
- 거기서 착안을 많이 했었음

## Backbone 설정하실 때 다 가져다 써보신건가요?

- 이전에 만들었던 코드가 있었고
- 하드웨어가 부족해서 다해보진 못했고 이전에 잘 됐던 네트워크 모델 하나랑
- timm 에서 업데이트 되는 모델보고 paper도 보고 pretrained 된게 있으면 쉽게 가져와서 썼음

## Arcface loss 한번더 설명

- 선하나가 하나의 클래스
- 모델을 통해서 나온 feature extraction 과 선과의 내적을 구해서 가까운 정도를 봄?

## CNN structure에서 embedding layer size 를 512로 설정하신 특별한 이유가 있을까요?

- 적정 수준을 넘어가면 성능이 비슷하므로 실험을 해보는 게 좋을 듯
- 하드웨어가 돌아갈만한 정도?

## 의사결정의 경계를 정하는 노하우가 있을까요?

- thresholds 라는 개념이 포함되지 않음
- validation 을 잘 짜서 validation score 가 높은 쪽으로 thresholds 를 설정할 것 같음
- 리더보드에 계속 제출해보면서 설정할 것 같음

## 데이터를 보고 이 데이터는 어떠한 방식으로 전처리를 해야겠다라는 생각이나 접근 방법을 정하시는지 알 수 있을까요?

- 보는 이미지들을 어떤 부분에서 집중해야할지 정의가 되야 할 듯
- 이 문제를 푸는데 있어서 뽑아내야할 특징들이 뚜렷해야 하는게 우리한테 유리
- 예를들어서 아스팔트에 균열이 있는 것을 detecting 해야 한다고 하면
- 사람이 보더라도 특징이 뚜렷하게 나오는 전처리 방법을 적용하는게 좋을 듯
- Data augmentation 하는 방법은 가장 좋은 것은 Test Dataset 에서 유사하게 나올 수 있게 Noise, Flip, 위치 변경 등
- Image Compression, Gaussian Blur, Cutout 를 이용하게 되면 이미지가 흐릿해지면서 모델의 성능이 오르는 효과가 있는 듯
- 특정 Feature 에 Overfit 하는 것을 막을 수 있음

## OVerfitting 되는 상황이면 어떤 것 부터 바꿔보시나요?

- 전처리가 가장 효과가 좋다고 생각
- 모델 architecture & HyperParameter 에도 문제가 있다고 생각하지만
- 근본적으로는 데이터에 답이 있다고 생각함

## 21 페이지 간단하게 다시 설명해주실 수 있을까요?

- Train data 이미지 하나가 vector 로 만들어지는 것임 extract 되는거라고 생각하면 되고
- vector size 는 512가 되고 밑으로는 샘플수가 될 것
- n x 512 Train features set 이 구성이 되고
- Test feature를 CNN으로 extract 하는데 embedding layer 에서 하는 것임
- Train featrues 와 Test feature의 Cosine similarity 를 비교해서 가장 가까운애를 선택

## Validation dataset 을 구축할 때 train split 같은 방법으로 나눴을 때 성능이 너무 잘나와서 저희가 쓰는 방법론이 제대로 작동하는지 확인이 어렵다면 어떻게 해야 validation dataset을 구축하면 좋을까요?

- train score, validation score, test score 가 나오는데 validation 에서도 잘 나오고 test set 에서도 잘나오는게 우리가 이상향으로 잡는 방향
- validation score 가 test score 가 잘 연결되지 않는다면 validation set 과 test set 이 다른지 확인하고
- 코드가 잘못 됐을 확률이 높음

- 편법아닌 편법은 인간 labeling을 해서 Test set을 보고 하는 방법은 치팅이라서 시도 안했고
- Train set 에서 Test set 이랑 가장 비슷한게 뭐냐라고 생각해서 어렵게 만들어야 함

## 주피터, ide 뭘 쓰시나요?

- 주피터는 간단하게 확인할 수 있는 값들  (distribution) 이런 것들은 주피터에서 작업
- 나머지 외적인 것들은 script 로 짜서 작업을 함
- albumentation demo 에서 대충 감을 잡음

## 서비스 관점에서

- 코사인 유사도를 구하는 operation 이 오래 걸릴 수 있어 문제가 있음

## 신제품이 나왔을 때 클래스 추가는 어떻게 할 수 있을까요?

- Transfer Learning 이 가능하기 때문에 잘 되지 않을까 싶음

## 현업에서 Train set 과 Test set 이 다른 경우가 많은가요?

- POC 단계에서 만들어진 데이터는 퀄리티가 좋지 않기 때문에 데이터가 얻어지는 파이프라인이 여러군데라고 하면 좀 퀄리티가 안좋음
- 그런 경우도 있지만 다 다름

## shake-up

- 없었다.

## metric learning 을 하면 어느 정도 적은 이미지로도 괜찮은 성능을 보장하는 것으로 아는데 현업에서는 실제로 그런 점을 고려해서 모델링하기도 하나요?

- 현업에서는 few-shot learning 을 고려하는 곳이 있음
- anormaly detection
- 학습데이터로는 정상데이터로만 학습을 시키고 그걸 이용해서 inference 를 하는데 정상이미지가 들어오면 정상이미지 그대로 나올거고
- 비정상이미지가 들어오면 정상이미지로 유도가 되기 때문에 그 차이를 보고 결정을 내림
- 여기서 thresholds 가 필요
- 그렇게 적용하기는 어려운 것 같음 제약이 많아서

## inference time 까지 고려하는 대회는 그럼 현장의 그런 사정들을 고려할 수 있을까요?

- inference time 을 고려하는 대회가 많았었는데 이런게 많이 없어짐
- 대회 운영 관점에서 그렇게 하면 좋긴 한데 형평성의 방향에서 안될 수도 있고 에러가 많이 남
- competition 에서는 제어가 힘드니까

## 짬밥은 어떻게 쌓이나요?

- 대회 관심이 많아서 아침에 Solution 을 보다거나 Discussion 을 보는 방향으로 확인했고
- 여러 대회를 나가보는게 가장 좋고
- Solution 을 읽는데에만 그치는게 아니고 내 생각을 투영해보는게 가장 많이 배우는 것 같음
- 그냥 수용하는게 아니라 자기만의 언어로 생각해보는게 도움이 될 듯
- 아니면 아예 컨셉을 잡아서 비관적으로 이거는 잘 못 됐을거야라는 생각으로 접근하는 방법
    - 그렇지만 이 방법은 근거가 필요함

## augmentation 을 할 때 gan 을 사용하기도 하는 걸로 아는데 현업에서도 종종 사용되나요?

- 아직 나는 해본적 없음
- 뱅갈리 대회에서는 gan 을 이용해서 augmentation을 했는데
- 가능했던 이유는 데이터가 높은 정도의 precision 을 갖는게 아니고 문자 정도의 글씨이기 때문에 가능했던걸로 아는데
- gan 이라는 것도 학습데이터가 많아야 학습되는건데 이걸 이용해서 augmentation(데이터증강기법) 을 하는 것은 앞뒤가 안맞는다고 생각함
- train 할 때 gan 은 잘 학습이 될까라는 생각

## train set과 validation set의 분포를 비슷하게 설정을 하는 것이 좋다고 하셨는데 데이터의 클래스 분포가 많이 불균형한 상태라도 validation set을 train set의 분포와 비슷하게 설정하는 것이 좋을까요? 아니면 클래스별로 동일한 개수로 구성해주는 것이 좋을까요 ?

- 대회에서 제일 처음 하는게 validation 설정하는게 가장 중요하다고 생각
- 리더보드랑 선형 관계가 있다라고 하면 validation 은 그 다음에 설정 하지 않음
- 그때까지는 이것도해보고 저것도 해보는게 좋음
- 서비스관점에서 생각을 해본다고 하면 다른얘기가 될 수 있음
- test set 이 실제 현장에서 어떻게 될지가 연결이 되어야 프로젝트가 성공적으로 마치기 때문에 데이터를 보고 이해하는데 있어서 통찰력이 필요함

## 고득점과 저득점의 가장 큰 차이가 무엇인지 궁금합니다.

- competition 을 부담없이 진행했으면 좋겠다
- 생각이라는게 중요하지
- 나는 이렇게 문제를 정의했기 때문에 이러한 방법으로 문제를 풀었어가 더 가치있는 일이라고 생각
- 리더보드에서 정의한 스코어와 내가 정의한 문제가 같은게 중요한데
- 내가 생각했던 것은 이런거기 때문에 이런 메소드를 적용했어가 더 좋은 학습방법이라고 생각
- 그래도 답변을 하자면!
- 가장 좋은 방법은 문제에 대해서 잘 해석하는게 중요하다고 생각
- 문제 정의가 되지 않으면 아이디어도 따라오지 않고 메서드도 따라오지 않기 때문에 문제정의가 가장 중요하다
- 보고 있는 문제는 뭔지, 내가 직면한 문제는 뭔지를 잘 구분해서 해결해는게 차이이지 않을까





