---
title: "Day_82 [마스터클래스] 클라이언트 사이드 ML - 김정훈 마스터"

categories:
  - Boostcamp_AI_Tech/Week_18
tags:
  - 마스터클래스
---

# [마스터클래스] 클라이언트 사이드 ML - 김정훈 마스터

## Client-side ML

### 부제: 내 비싼 서버 말고.. 고객님 기기(노트북, 스마트폰)에서 inference 돌리기

## 1. Overview

### 1.2 경량화 업무

**결국 돈 돈 돈!(cloud)**

- 유사한 성능의 모델을
  - 한번에 더 많이(Channel)
  - 더 빠르게(Speed)
  - 돌릴 수 있다면?
  - 근데 심지어 더 저렴하게?(Fee), 더 싼 device 로?

![]({{site.url}}/assets/images/boostcamp/9678d437.png)

유사한 성능인데 80% 60%의 비용을 줄일수 있다면 왜 안하겠어?

customize 하고 자동화하기 쉽지 않음

### 1.2 Server-side ML

**Server-side ML: 지금까지 해왔던 것들**

- 별도의 server 환경에서 $\rightarrow$ Infra 비용
- 고객의 정보를 젇날받아
- 추론하고
- 추론 결과를 전송 $\rightarrow$ privacy 이슈, 네트워크 연결, 지연문제

## 2. Client-side ML

### 2.1 Introduction

**Client-side ML?**

- Client 쪽에서 ML 모델의 학습, 추론을 수행
- Client 쪽?
  - Browser: 크롬, 사파리, 파이어폭스, 웨일
  - Mobile: 아이폰, 안드로이드 폰
  - IoT: 라즈베리파이 등의 임베디드 디바이스

**빌드업: client 들의 기기가 좋아지고 있어요!**

- 좋아지는 컴퓨터(+노트북), 스마트폰 spec
- 발전되는 기술들: WebGL, Web Assembly, WebGPU

![]({{site.url}}/assets/images/boostcamp/56a58979.png)

**WebGL, WebAssembly, WebGPU?**

- Browser(chrome, safari, ...)에서 3D 그래픽 처리 가속화를 위해 만들어진 라이브러리
- WebAssembly(WASM): CPU backend, SIMD, multi-threading 등으로 가속화
- WebGL: GPU backend, 다양한 플랫폼에서 활용 가

![]({{site.url}}/assets/images/boostcamp/1c06e748.png)

**Client-side ML 의 장점**

![]({{site.url}}/assets/images/boostcamp/95ed7763.png)

프라이버시 보장, 낮은 지연, 접근성 좋음, 서빙 cost 적음

- Privacy: 서버에 데이터를 전송할 필요 없이, local 에서 학습, 추론이 가능
  - 데이터를 보내기 민감한 케이스에 대해서 활용 가능
  - 개인정보보호법, EU 의 GDPR(General Data Protection Regulation) 등에 대해서 비교적 자유로움
- Speed: API 로부터 응답을 기다리지 않아, realtime inference 가능
- Reach and scale: web page 에서 클릭만으로 누구든 접근 가능(환경 셋업 등의 작업이 필요치 않음)
- Cost: 서버 구축(임대) 비용이 들지 않음

**Client-side ML 의 단점(개발자 입장)**

- Client 내에 모델이 다운로드, 메모리에 올라가 추론이 이루어지므로, 모델이 노출됨
  - 모델 구조, 데이터 프로세싱 과정을 client 가 알아낼 수 이씅ㅁ
- Monitoring 불가
  - 유저가 보는 데이터에 접근할 수 없으므로($\rightarrow$ Feedback cycle 구성이 어려움)

### 2.2 대표 라이브러리 소개

**Tensorflow.js(https:/www.tensorflow.org/js)**

- 가장 활발한 개발이 진행 중
- 친절한 튜토리얼 & 다양한 데모
- 기존 Tensorflow 모델을 js 로 변환이 가능
  - E.g) HuggingFace TF 모델을 TFJS 로 변환
- 여러 종류의 pretrained 모델 제공
  - https://www.tensorflow.org/js/models
  - https://tfhub.dev/
- (⭐️) 기존 TF 함수들 사용이 가능해서, 
  - 전처리 과정(e.g. Tokenizer), 후처리 과정(e.g. NMS)이 용이
- (tfjs 와는 별개로) Mobile(App), IoT 를 위한 TFLite 또한 고려 가능(https://www.tensorflow.org/lite)

tensorflow 쪽이 모바일이나 웹쪽에 힘을 많이 쓰고 있는 느낌

**ONNXruntime(https://onnxruntime.ai, https://github.com/microsoft/onnxruntime/tree/master/js/web)**

- (⭐️) PyTorch $\rightarrow$ ONNX 후 사용 가능
- TFjs 대비 더 높은 성능(https://github.com/microsoft/onnxjs#benchmarks)
- Vision 관련 데모(https://microsoft.github.io/onnxjs-demo/#/)
- (😭) 전처리 과정(e.g. Tokenizer), 후처리 과정(e.g. NMS)에 대해서 js, ts 구현체가 필요

## 3. Demo

### 3.1

https://playground.tensorflow.org/

### 3.2 

https://hoonyyhoon.github.io/clientside-ml-demo/ 

https://github.com/Hoonyyhoon/clientside-ml-demo/

### 3.3

https://www.tensorflow.org/js/demos

## 4. 정리

**Server-side, Client-side: 상황에 맞게**

- Server-side: Computing power 측면에서 강점
- Client-side: Privacy, cost 측면에서 강점
- (⭐️) 서비스의 Pipeline 전체가 Server-side 일 필요는 없음

**Server-side, Client-side: 예시**

![]({{site.url}}/assets/images/boostcamp/e4a855ee.png)








 