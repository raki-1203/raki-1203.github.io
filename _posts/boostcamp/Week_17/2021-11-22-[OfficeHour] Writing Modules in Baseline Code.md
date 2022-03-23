---
title: "Day_75 [오피스아워] Baseline 코드에 모듈 작성하기 - 신종선 멘토"

categories:
  - Boostcamp_AI_Tech/Week_17/Day_75
tags:
  - 오피스아워
---
  
# [오피스아워] Baseline 코드에 모듈 작성하기 - 신종선 멘토

마키나락스 ML Engineer

## Baseline 코드 이해

### Model Parser 흐름 이해하기

![]({{site.url}}/assets/images/boostcamp/6560b7bc.png)

**Model Parser 에서 최종 model 까지**

1. Model.yaml
2. ModelParser._parse_model()
   1. ModuleGenerator
   2. CustomModuleGenerator
   3. CustomModule
3. return Model

![]({{site.url}}/assets/images/boostcamp/ba3bf1b2.png)

![]({{site.url}}/assets/images/boostcamp/854d81de.png)

**ModelParser**

- _parse_model : 내부적으로 model_config 를 parsing 해서 nn.Sequential 모듈 리턴
- yaml 에서 입력받은 repeat, module, args 를 ModuleGenerator 에 입력

![]({{site.url}}/assets/images/boostcamp/5df6a07c.png)

![]({{site.url}}/assets/images/boostcamp/31e3f4d0.png)

**ModuleGenerator**

- `__call__` : 입력 받은 module 이람의 generator 를 호출

src.modules.init.py 에 존재하는 모듈 중 입력받은 module generator 에 해당하는 모듈을 가져옴

이렇게 3가지를 직접 작성하면 됨
1. Model.yaml
2. CustomModuleGenerator
3. CustomModule

## Custom Module 작성하기

1. Fire Module
   - Torchvision 의 model 사용
   - **forward** : 1x1 expand layer 와 3x3 expand layer 의 out channel concat 하여 출력

   ![]({{site.url}}/assets/images/boostcamp/fa269d22.png)

   ![]({{site.url}}/assets/images/boostcamp/40efd517.png)

2. GeneratorAbstract

   - Custom Module Generator 를 만들 때 상속받아야 하는 추상화 클래스
   - abstractmethod : out_channel, `__call__`
   - Custom module generator 의 class 이름은 Custom Module 이름 + Generator 로 작성

   ![]({{site.url}}/assets/images/boostcamp/db76f3f6.png)

   ![]({{site.url}}/assets/images/boostcamp/b7defb80.png)

3. FireGenerator
   - **out_channel** : expand1x1 channel 과 expand3x3 channel 의 합으로 out_channel 결정
   
   ![]({{site.url}}/assets/images/boostcamp/403f4578.png)

   ![]({{site.url}}/assets/images/boostcamp/43fc512d.png)

4. Fire Module Generator

   - `__call__` : Generator 가 불리울 때, base_module 을 호출하여 argument 를 전달하고 repeats 에 맞는 module 생성
   - **base_module** : src.modules.init.py 에 존재하는 모듈 중 Fire 에 해당하는 모듈을 가져오므로 init.py 에도 추가

   ![]({{site.url}}/assets/images/boostcamp/5d7927af.png)

   ![]({{site.url}}/assets/images/boostcamp/df7d6010.png)

### 결과

squeezenet.yaml

![]({{site.url}}/assets/images/boostcamp/2c6eec7f.png)

---

Q&A

> 주로 yaml 파일을 이용해서 모듈을 만드나요?

module 을 새로 만든다면 코드를 새로 작성해줘야 함

> 앞장 ppt에서 MaxPool의 인자를 하나씩 설명해주실 수 있으신가요?

source.modules.maxpool.py 를 확인하면 정확할 것 같음

