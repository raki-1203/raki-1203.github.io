---
title: "Day_35 [특강] 서비스 향 AI 모델 개발하기 - 이활석"

categories:
  - Boostcamp_AI_Tech/Week_/Day_35
tags:
  - 특강
---
  
# [특강] 서비스 향 AI 모델 개발하기

# 서비스 향 AI 모델 개발하기

## 서비스 향 AI 모델 개발 VS 수업/학교/연구 AI 모델 개발

- 서비스에서 사용되는 AI 모델 개발 일은 현재 수업에서 배우고 있는 AI 모델 개발과 무엇이 다른가?

### 연구 관점에서 AI 개발이란?

- 보통 수업/학교/연구에서는 정해진 데이터셋/평가 방식에서 더 좋은 모델을 찾는 일을 함

    ![]({{site.url}}/assets/images/ba744148.png)

- 테스트 데이터셋과 테스트 방법에서 최고로 좋은 성능을 낼 수 있도록 모델 구조를 새롭게 디자인 하는 일을 모델링이라고 부름
- 그 결과 모델 하나를 확보할 수 있음

### 서비스 관점에서 AI 개발이란?

- 서비스 개발 시에는 학습 데이터셋도 없음

  ![]({{site.url}}/assets/images/6035ff63.png)

- 학습데이터셋이 없는 경우도 많고 테스트 데이터셋이랑 테스트 방법도 없는 경우가 많음

- 서비스 개발 시에는 서비스 요구 사항만이 있음

  ![]({{site.url}}/assets/images/021820d3.png)

- 그래서, 첫 번째로 해야 할 일은 **학습 데이터셋**을 준비하는 것임

  ![]({{site.url}}/assets/images/1e9dca36.png)

- 정확히는 서비스 요구사항으로 부터 학습 데이터셋의 **종류/수량/정답**을 정해야 함

  ![]({{site.url}}/assets/images/21861c70.png)

### 학습 데이터셋 준비 : 종류

- 예시를 들어 보자.

  ![]({{site.url}}/assets/images/bcf324f8.png)

- 질의 응답을 통해서 서비스를 구체화 시켜야 함

  ![]({{site.url}}/assets/images/986d59a9.png)

- 간단한 수식도 있고 딥러닝의 backpropagation 과정에 나오는 복잡한 수식일수도 있으므로 질문
  
  ![]({{site.url}}/assets/images/26668e8f.png)

- 질의 응답으로 학습데이터셋의 대한 종류를 뽑아내야 함

### 학습 데이터셋 준비 : 정답

- 질의응답을 통해 데이터셋의 종류/수량/정답 관련 요구사항을 구체화해야 함

  ![]({{site.url}}/assets/images/cac0f078.png)

  ![]({{site.url}}/assets/images/fd66d812.png)

  ![]({{site.url}}/assets/images/18ff49be.png)

### 학습 데이터셋 준비 : 종류

- 대충 이미지를 찾아보니...

  ![]({{site.url}}/assets/images/b9a05b55.png)

  ![]({{site.url}}/assets/images/6266e41d.png)

- 더 많은 경우를 찾아보니...

  ![]({{site.url}}/assets/images/0e2eaf1e.png)

- 그림자도 신경써야하고 형관펜도 칠한 경우가 있는데 이런 것도 대응을 해야하는지 혹은 수식을 온전히 다 찍으면 좋겠는데
이렇게 밑에 부분에 수식이 짤려있는거라던지 이런 것도 인식을 해야하나?
  
  ![]({{site.url}}/assets/images/4e895ac7.png)

- 열심히 하다가 화이트로 지워서 그 위에 적은 경우도 대응해야하고

  ![]({{site.url}}/assets/images/a7745615.png)

- 종이가 구겨져있거나 휘어져있어도 대응이 되야하는지?

  ![]({{site.url}}/assets/images/d613de5f.png)

- 촬영을 하다보면 회전이 되있을 수도 있음 이런 데이터셋들도 다 대응을 해야하는지?

  ![]({{site.url}}/assets/images/43a4f402.png)

- 보통 기획팀에게 물어보면 모두 다 대응해주세요라는 답변이 오게됨

### 학습 데이터셋 준비 : 종류/수량

- 결국, '종류'에 대해서도 정의를 해야 함
- 어디까지 '종류'로 정의해서 각각 몇 장을 수집 할 것인지 정해야 함

  ![]({{site.url}}/assets/images/2c31b51b.png)

- 꼭 이런 방법으로 모으지 않더라도 됨

  ![]({{site.url}}/assets/images/219d5222.png)

- 이런식으로도 구분이 가능

- "어떤 관점에서 종류/수량을 정할지는 이 강의에서 다루지 않음"

### 학습 데이터셋 준비 : 기술 모듈 설계

- 지금까지의 이야기를 종합하면, 다음과 같은 입출력을 갖는 기술 모듈을 개발해 달라는 요청

  ![]({{site.url}}/assets/images/754bd5b3.png)

- 직접 데이터를 모아보면 미리 생각하지 못한 경우도 많이 발견하게 됨

  ![]({{site.url}}/assets/images/375ca38a.png)

- 이렇게 되면 전체 이미지에서 수식 영역을 검출하는 모듈이 추가 되어야 함

  ![]({{site.url}}/assets/images/b7e70491.png)

- 예시를 보자.

  ![]({{site.url}}/assets/images/cebbd4df.png)

- 이런 흐름을 보면 자연스러움

### 학습 데이터셋 준비 : 정답

- 이번에는 학습데이터의 '정답'에 관한 얘기를 해보자.
- 학습데이터에서 '정답'은 **AI 모델 별**로 입력에 대한 출력 쌍임

  ![]({{site.url}}/assets/images/7739deb2.png)

- **이처럼 AI 모델 하나에 대한 정답은 모델 설계와 맞물려 있음!**

  ![]({{site.url}}/assets/images/076123a3.png)

- 그런데 Image To Latex 가 한 모델로 가능할까? 나름 성능이 검증된 4가지 모델 조합은 어떨까?

  ![]({{site.url}}/assets/images/2539831a.png)

- **이 경우, 각 모델 (총 4개 모델) 별로 입출력 (정답) 정의가 필요함!**

### 학습 데이터셋 준비

- 결국 학습 데이터 준비를 하려면 모델 파이프 라인 설계가 되어 있어야 함

  ![]({{site.url}}/assets/images/55afeb5f.png)

- 학습데이터셋을 준비할 때에는 모델링쪽에서 모델 설계가 들어와야 함

  ![]({{site.url}}/assets/images/dc38edb4.png)

- 그런데, 모델 파이프 라인 설계하려면 어느 정도 데이터가 있어야 함
- 맞나? 틀리나? 를 검증할 수 있어야 함

  ![]({{site.url}}/assets/images/b3bc4137.png)

- 실제로 일을 할 때는 이 과정이 반복적으로 일어남

  ![]({{site.url}}/assets/images/17cd096c.png)

- 자! 본인이 학습 데이터셋 준비 담당자라고 해보고, 어떤 일을 겪게 되는지 살펴보자.

  ![]({{site.url}}/assets/images/d42dcb48.png)

- 서비스 기획자와 많은 커뮤니케이션이 있음

  ![]({{site.url}}/assets/images/ca3297f2.png)

- 모델 설계에 대한 정보를 받아야 함

  ![]({{site.url}}/assets/images/21beca9e.png)

- 요즘은 외주 업체를 많이 씀
- 요즘 데이터셋 제작 업체들은 작업 툴을 만들 수 있는 능력도 가지고 있음

  ![]({{site.url}}/assets/images/7a91f6f3.png)

- 외주업체와 커뮤니케이션을 하면서 제일 중요한게 작업 가이드임
  - 학습데이터셋의 정답을 어떻게 매길것인지에대한 작업 가이드
- 작업 단가 논의, 작업 수량 논의
  - 단가와 수량은 예산도 중요한 포인트임
- 작업자들의 질문에 대한 대응도 필수

- 다시 한 번 정리해보면...

  ![]({{site.url}}/assets/images/6da01ea4.png)

### 테스트 데이터셋 / 테스트 방법 준비

- **테스트 데이터셋은 학습 데이터셋에서 일부 사용한다고 하고,** (사실은 이것도 할 얘기가 많지만..)
- **서비스 요구사항으로부터 테스트 방법을 도출해야 함**

  ![]({{site.url}}/assets/images/e1575d40.png)

  ![]({{site.url}}/assets/images/c150450b.png)

- 어떻게 AI 모델을 평가를 할 것인가? 에 대한 정보를 도출해야 함

- 이것도 이해를 위해서 하나의 예시를 들어 보자!
- 1 vs 1 대전 게임을 위한 AI 모델을 만든다고 생각해 보자.

  ![]({{site.url}}/assets/images/11e0b228.png)

- 이 때 AI 모델의 입출력은 다음과 같음

  ![]({{site.url}}/assets/images/25b7dfdf.png)

  ![]({{site.url}}/assets/images/0aa41906.png)

- 이 AI 를 학습시키기 위해서 프로게이머들의 로그를 받아서 AI를 학습시킴

  ![]({{site.url}}/assets/images/287686ec.png)

- 그 결과 모델의 분류 정확도가 무려 99%!!
- 이 AI 모델을 실제 사용자와 대전을 붙였ㅇ르 경우 결과가 어떻게 되었을까?

- 결과는 완패!!

- 이 AI 모델은 아무런 스킬도 사용하지 않았음
- 왜냐하면, 프로게이머의 로그를 살펴보니..

  ![]({{site.url}}/assets/images/23b76dd2.png)

- 스킬을 사용하는 횟수가 적음
  - 고수일 수록 스킬을 남발하지 않고, 적재적소에서만 사용 $\rightarrow$ 로그 대부분 no_action
  - 그래서 모델이 항상 no_action 을 예측하게 학습이 되었고, 모델 정확도는 99% 실제 승률은 0%

- 이렇게 실 서비스 적용 전에 개발 환경에서의 정량 평가와 **(OFFLINE 테스트)**
- 실 서비스 적용시에 정량 평가는 **(ONLINE 테스트)**
- 이질감이 굉장히 클 수 있음

- 결국, 서비스에서의 품질이 중요하기 때문에 OFFLINE 테스트 결과가 ONLINE 테스트 결과와 유사하게 OFFLINE 테스트를 잘 
설계해야 함

- 테스트 방법에 대해 다음처럼 정리할 수 있음

  ![]({{site.url}}/assets/images/02853494.png)

- 개선 포인트를 파악하는일이 굉장히 중요함!!

## 모델 요구사항 도출

- 추가로, 모델에 관련한 요구사항을 도출해야 함

  ![]({{site.url}}/assets/images/5ad728bb.png)

  ![]({{site.url}}/assets/images/7647690f.png)

- 처리 시간 / 목표 정확도

  - **처리 시간**
    - 처리 시간은 하나의 입력이 처리되어 출력이 나올 때까지의 시간
      - 예) 수식 영역 검출의 경우,
        - OFFLINE TEST : 이미지 입력 후 수식 영역 정보가 출력될 때까지의 시간
        - ONLINE TEST : 이미지 촬영 후 이미지에서 수식 영역 정보가 화면 상에 표현되기까지의 시간
          ![]({{site.url}}/assets/images/67c61ab1.png)

  - **목표 정확도**
    - 해당 기술 모듈의 정량적인 정확도
      - 예) 신용카드 인식의 경우,
        - OFFLINE TEST : 입력된 이미지 내 카드 번호/유효기간에 대한 EDIT DISTANCE
        - ONLINE TEST : 사용자가 AI 모델의 결과값을 수정할 확률

  - **목표 qps**
    - QPS, Queries Per Second (초당 처리 가능한 요청 수)
    - 향상 방법
      - 장비 늘리기
        - N대를 늘리면 QPS 가 N 배 올라감
        - 무조건 올라가진 않지만 손쉽게 올릴 수 있음
      - 처리시간 줄이기
        - AI 모델의 처리 속도가 N 배 올라가면 QPS 도 N 배 올라감
      - 모델 크기 줄이기
        - 한 GPU 에 올라가는 모델 수가 N 배가 되면, QPS 도 N 배 올라감
        - 만약, GPU 메모리가 10GB 이고 , 모델 크기가 8GB 라면, 모델 크기가 5GB 가 되어야
        QPS 가 두 배 올라가지 7GB, 6GB 줄이는 건 QPS 관점에서는 8GB 와 다르지 않음
  
  - **Serving 방식**
    - 기술 모듈이 Mobile 에서 동작하기 원하는지, Local CPU / GPU Server 에서 동작하기 원하는지, 
    Cloud CPU / GPU Server 에서 동작하기 원하는지

  - **장비 사양**
    - 가끔은 Serving 장비조차 없어서 장비 구축까지 같이 요구하는 경우도 있음
    - 이때는 예산 / QPS 에 맞춰서 장비 사양도 정해야 함

- AI 모델 개발에는 수업에서 익히는 것 외에 정말 많은 일들이 존재

  ![]({{site.url}}/assets/images/61d4be92.png)

# 서비스 향 AI 모델 개발 기술팀의 조직 구성

- 서비스에서 사용되는 AI 모델을 개발하기 위한 바람직한 조직 구성

## AI 모델팀

- AI 기술팀에게는 서비스 요구사항이 오고, 이에 맞는 AI 모델을 개발해야 함

  ![]({{site.url}}/assets/images/43bfe23f.png)

- 당연히, AI 모델을 개발하는 인력이 필요함

  ![]({{site.url}}/assets/images/3e12a879.png)

- 다음으로는, 앞서 설명드린 데이터를 준비하고 품질을 관리하는 인력이 필요함

  ![]({{site.url}}/assets/images/aa235d2d.png)

- 추가로, 데이터 / 모델과 관련된 업무의 효율성을 위한 툴을 개발하는 인력도 필요함

  ![]({{site.url}}/assets/images/f286789f.png)

- 마지막으로 이 전체를 총괄하여 모델의 품질을 관리하는 살마이 필요함

  ![]({{site.url}}/assets/images/437b8f07.png)

## AI 모델 서빙팀

- 그런데, 기술팀에 AI 모델 Serving 까지 요구되면 필요한 인력은 늘어남

  ![]({{site.url}}/assets/images/c0bdc127.png)

- 우선 Serving HW 향으로 모델을 최적화하는 인력이 필요함

  ![]({{site.url}}/assets/images/d1f74f87.png)

- 마지막으로 모델을 실제 서빙하기 위한 추가 작업들이 end device 에 맞춰 더 있음

  ![]({{site.url}}/assets/images/51c9bf6d.png)

# 당부의 말씀 몇가지

- AI 쪽으로 커리어를 쌓고자 하시는 분들에게 드리고 싶은 말씀

## 개발자 => AI 관련 전환

- Model Engineering / Tool / Serving 은 개발력이 많이 필요한 일이고,
앞으로 점차 니즈가 많아질테니 너무 AI 모델링 쪽으로 한 번에 넘어 가시지 말아라

  ![]({{site.url}}/assets/images/19453b64.png)

- FrontEnd 개발자분들은 Tool 만드는 일부터 먼저 해보면 좋음
- App 개발자는 TensorFlow Lite 를 받아서 app 으로 구동시키는 작업부터 해보는게 좋음
- BackEnd 개발자분들은 on CPU, on GPU 관련 일부터 해보는게 좋음
- Model Engineering 작업은 교집합이라서 모든 개발자에게 좋음

## 모델러

- 한 분야의 모델링에 대한 전문성도 중요하지만, 점점 해당 업무는 자동화되고 (AutoML, 관련 툴)
관련 인력 수도 늘어나니 주변으로 역량을 확대하라!

  ![]({{site.url}}/assets/images/08b95af1.png)

## All

- 특히나, AI 기술트렌드에 민감해야 함
- AI 기술 발전 속도는 다른 기술에 비해 훨씬 빠르고 변화무쌍함
- 단순히 기술 뿐만 아니라, 이를 둘러썬 많은 것들도 빠르게 변함
- 이것을 당연하게 받아들이고, 어떻게 하면 효율적으로 변화에 적응할 지 고민해야 함
- 예전에 경험하지 못한 늘 새로운 일이 생겨나고, 기존 사례도 없는 경우도 많으니 새로운 길을 개척하는 경우도 적지 않음
