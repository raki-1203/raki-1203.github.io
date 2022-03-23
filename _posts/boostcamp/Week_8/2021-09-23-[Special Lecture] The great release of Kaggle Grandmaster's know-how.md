---
title: "Day_35 [특강] 캐글 그랜드마스터의 노하우 대방출 - 김상훈"

categories:
  - Boostcamp_AI_Tech/Week_8
tags:
  - 특강
---
  
# [특강] 캐글 그랜드마스터의 경진대회 노하우 대방출

## 캐글 소개

- 실력을 인정받을 수 있고 AI 개발자로 성장하기 좋은 캐글 플랫폼을 소개합니다.

### 캐글은?

- 2010년 설립된 세계에서 가장 유명한 인공지능 대회 플랫폼
- 2017년 3월 구글에 인수됨
- 194개국 600만명 이상의 회원 보유
- 캐글을 즐겨하는 사람을 **Kaggler** 라 함

    ![]({{site.url}}/assets/images/boostcamp/afbd5a4d.png)

### 국내 유명 경진대회 플랫폼

![]({{site.url}}/assets/images/boostcamp/c2b341f4.png)

### 캐글을 왜 해야 할까요?

- 세계적으로 실력을 인정 받기 위해서 (취업 목적)
  - 알만한 해외 회사에서 제안이 오기도 함
  - 심지어 아이비리그에 속하는 대학교의 박사과정 제의까지!
- AI 개발자로 배우고 성장 하기 위해서 (개인 성장)
  - 캐글은 특유의 공유문화가 있어서 배우기 좋은 수많은 코드, 토론 자료들이 있음
  - 특히 캐글의 노트북은 버튼 몇 번 조작으로 빅데이터를 읽어서 학습 및 훈련까지 가능!

### 캐글에서 실력을 인정 받으려면?

- 랭킹 시스템 활용
  - 경진대회에서 높은 순위에 들어 포인트를 획득
  - 누적된 포인트로 순위가 매겨짐

- 티어 시스템 활용
  - 경진대회에서 메달을 따게 되면 개수에 따라서 티어가 결정됨
  - 총 4개 종목 중 가장 인기있고 어려운 티어인 **컴피티션 그랜드 마스터** 획득!

  ![]({{site.url}}/assets/images/boostcamp/aa9a1d54.png)

- 상위 랭커가 되려면?
  - 혼자 경진대회에서 높은 등수를 획득
    - 1등 약 64,000 포인트
    - 2등 약 38,000 포인트
    - 3등 약 28,000 포인트
    - ...  

- 그랜드 마스터가 되려면?
  - 5개의 금메달 획득
  - 이 중 1개는 솔로 금메달

## 캐글 시작해 보기

- 경진대회의 전 과정을 캐글을 통해 빠르게 경험해 봅니다.

1) 회원 가입
   
    ![]({{site.url}}/assets/images/boostcamp/ee1df753.png)

2) 참여할 대회 선택

    ![]({{site.url}}/assets/images/boostcamp/caf56043.png)

---
### 참고 - 대회 개최 목적

- Featured
  - 상업적 목적의 예측 대회, 실제 기업에서 우승한 모델을 현업에 적용하기도 함
- Research
  - 연구 목적의 대회, 연구 목적이라 상금이 낮은 편
- Getting Started & Playground
  - 초심자를 위한 학습 목적의 대회. 예: 타이타닉 생존자 예측 대회
  - 랭킹용 포인트나 메달을 얻을 수 없음
- Analytics
  - 데이터 분석 목적의 대회. 데이터 탐색과 이를 시각화한 노트북을 제출하는 대회
- Recruitment
  - 리크루팅 목적의 대회

### 참고 - 대회 제출 방식

- General Competitoin (리소스 제약 없음)
  - submission.csv 파일만 Submit Predictions 메뉴에서 제출
- Code Competition (리소스 제약 있음)
  - 캐글 노트북에서 코드를 실행시켜 submission.csv 파일을 생성해야 함
  - submission.csv 을 생성할 때 리소스 제한(GPU, CPU, RAM, 실행시간)이 있음
  - 캐글러들이 쓸모 있는 모델을 만들도록 강제함
---

2) 참여할 대회 선택 - 진행중 대회

    ![]({{site.url}}/assets/images/boostcamp/04648508.png)

    ![]({{site.url}}/assets/images/boostcamp/b9d386df.png)

    ![]({{site.url}}/assets/images/boostcamp/f95137c8.png)

    ![]({{site.url}}/assets/images/boostcamp/b6588e28.png)

3) 대회 데이터 다운로드

    ![]({{site.url}}/assets/images/boostcamp/8506e301.png)

    ![]({{site.url}}/assets/images/boostcamp/b26ec096.png)

4) 대회를 위한 파이프라인 구축

    ![]({{site.url}}/assets/images/boostcamp/fb064179.png)

5) 캐글로 파이프라인을 빠르게 경험해보기

    ![]({{site.url}}/assets/images/boostcamp/6b9094d0.png)

    ![]({{site.url}}/assets/images/boostcamp/531cc27c.png)

5) 캐글로 파이프라인을 빠르게 경험해보기 - 제출 준비

    ![]({{site.url}}/assets/images/boostcamp/28bb25bf.png)

    ![]({{site.url}}/assets/images/boostcamp/9a584485.png)

- Save Version 을 클릭하고 좀 지나면 0 -> 1 로 바뀌는데 1 을 클릭하면
 
  ![]({{site.url}}/assets/images/boostcamp/1340dc93.png)

5) 캐글로 파이프라인을 빠르게 경험해보기 - 리더보드 제출

- 이 페이지로 오게 됨
- 내 계정으로 완전히 복사하게 됨

    ![]({{site.url}}/assets/images/boostcamp/98e36a87.png)

- Submit 버튼을 클릭하면 리더보드 제출까지 가능

## 캐글 노하우 대방출

- 경진대회에서 우승하기 위해 필요한 것들을 알아 봅니다.

### 우승하기 위해 필요한 것

1) 파이프라인의 (빠른/효율적) 반복
   - GPU 장비
     - 학습속도가 빠를 수록 파이프라인 반복 속도가 빨라짐
     - 캐글에서 상위권에 들기 위해 필수
     - Google Colab 등은 보조로 사용하면 좋음
     - 추천 장비 1 (200만원)
       - CPU : AMD 라이젠 3세대 3700 이상(8코어)
       - RAM : 64GB 이상
       - SSD : 1TB 이상
       - GPU : RTX2080Ti x 2대 (블로워 타입 중고로 구입)
     
         ![]({{site.url}}/assets/images/boostcamp/a23ae47c.png)
     
     - 추천 장비 2 (300~400만원)
       - CPU : AMD 라이젠 3세대 3700 이상(8코어)
       - RAM : 64GB 이상
       - SSD : 1TB 이상
       - GPU : RTX 3090 1대 (or RTX 3080 1대)
     - 추천 장비 3
       - CPU : AMD 라이젠 스레드리퍼
       - RAM : 128GB 이상
       - SSD : 1TB 이상
       - GPU : RTX 3090 2대 (or RTX 3080 2대 or RTX 2080Ti 4대)
     
         ![]({{site.url}}/assets/images/boostcamp/37f7998d.png)
     
   - 시간 투자
     - 수천팀이 참여하여 2 ~ 3 달 동안 많은 시간을 투자
     - 경쟁자를 이기려면 역시 저희도 비슷한 시간의 투자가 필요
     - 1달~2달 동안
     - 평일 하루 평균 4시간 이상 투자
     - 주말 하루 평균 8시간 이상 투자
       
       ![]({{site.url}}/assets/images/boostcamp/1282cc00.png)
   
   - 본인만의 기본 코드
     - 어떤 데이터를 다루는 대회든 기본 코드에서 일부만 수정하면 됨
     - 빠르게 파이프라인을 구축할 수 있고 실수가 적어지게 됨
   - 다른 사람의 코드를 참고하여 본인 것으로 소화한 코드를 만드는 것이 필요
     - 참고: https://github.com/lime-robot/categories-prediction
     - 이 코드를 바탕으로 최근 3개월 동안 3개의 금메달 획득!
       
       ![]({{site.url}}/assets/images/boostcamp/6b9c3246.png)
     
2) 점수 개선 아이디어
   - 캐글 Notebooks
     - 다양한 아이디어나 얻을 수 있음. Best Score, Most Votes 정렬 기능 사용 추천
     - 예: 어떤 딥러닝 아키텍처를 사용하면 좋을지, 이미지 오그멘테이션은 무엇이 좋을지 등
       
       ![]({{site.url}}/assets/images/boostcamp/db705bfe.png)
   
   - Discussion 탭 참고
     - 다양한 아이디어나 얻을 수 있음. Most Votes, Hotness 정렬 기능 사용 추천
     - 비슷하거나 동일한 이전 대회, 참고할 논문, 현재 대회 Overview 등등
       
       ![]({{site.url}}/assets/images/boostcamp/868e4efb.png)
     
   - 다른 경쟁자들의 글을 참고하며, 대회 마지막 제출 때까지 점수 개선 아이디어 고민
     - 추신: 마지막까지 방심하시면 안 됨

3) (올바른 방향인지) 탄탄한 검증 전략
   - 검증 전략이 필요한 이유
     - 최종 순위 하락을 피하기 위해: Public LB 1등 $\rightarrow$ Private LB 70
     - 리더보드 제출 횟수 제한이 있음: 보통 하루에 5회 제공
       
       ![]({{site.url}}/assets/images/boostcamp/d4495022.png)
     
     - Public LB 에 Overfitting 되는 경우가 있어서 필요함
   - 좋은 모델 (일반화; Generalization 성능이 높은 모델)
     - Training set 에서 얻은 점수가 Test set 에서도 비슷하게 나오는 모델
     
       ![]({{site.url}}/assets/images/boostcamp/c28ef75e.png)

   - 검증 전략 (Validation Strategy) 이란?
     - Test set 에서 얻은 점수와 Training set 에서 얻어진 점수 갭 0.03 을 줄이는 평가 방법

   - 검증 전략 구축하기
     - 캐글 데이터 구성
     
       ![]({{site.url}}/assets/images/boostcamp/ef8eb549.png)

     - Training set 나누기 및 평가

       ![]({{site.url}}/assets/images/boostcamp/78ac3050.png)

     - Training set 나누기 및 평가 (이상적)

       ![]({{site.url}}/assets/images/boostcamp/77f5cb58.png)

   - 점수 갭을 줄이기 위한 k-fold 검증 전략 구축하기
     
     ![]({{site.url}}/assets/images/boostcamp/6bf2cfcb.png)

     - 참고 - Stratified k-fold
     
       ![]({{site.url}}/assets/images/boostcamp/035503de.png)

   - 아무리 검증 전략을 잘 세워도 오버 피팅의 위험은 존재
     - local CV 와 Public LB 가 함께 올라가는 방법을 선택

4) 기타 꿀팁
   - 여러 모델의 예측 결과를 섞어서 예측 성능을 향상시킴
     - 싱글 모델 보다 항상 더 좋은 성능을 얻을 수 있음
   
   - 여러 방법이 있지만 아래처럼 정리되는 추세
     - Stratified k-fold 앙상블
     - 다양한 모델 앙상블
       - 정형 데이터 : LightGBM XGBoost, Neural Networks (NNs) 등
       - 이미지 데이터 : resnet, efficientnet, resnext 등
       - 텍스트 데이터 : LSTM, BERT, GPT2, RoBert
     
     ![]({{site.url}}/assets/images/boostcamp/8b3a90d0.png)

   - 대회에서 좋은 성적을 내려면 높은 점수의 싱글 모델이 필요
     - 앙상블해도 싱글 모델의 점수에서 약간 개선이 있을 뿐임
    
   - 근데 싱글 모델 점수를 몇 점까지 / 언제까지 개선해야 할까?
     - 상위 랭커들이 discussion 에 언급한 자신의 싱글모델 점수 참고
       
       ![]({{site.url}}/assets/images/boostcamp/4455a414.png)
     
     - 대회 종료가 1 ~ 2주 정도 남았을 때 싱글 모델 점수로만 50등 내에 들면 좋음 

   - 팀을 맺을 때 주의해야 할 점
     - 2달 동안의 여정은 힘들기 때문에 팀을 맺는 것도 추천
     - 다만, 한번 팀을 맺으면 해체가 불가능
     - 동료 후보가 현재 대회에서 높은 순위에 있는지 확인 필요
       - 생각 외로 게으른 사람들이 많음

   - 코드 관리
     - v1, v2, v3, ... 순서로 개별 폴더를 만들어 코드 관리
     - 버전 별로 전처리 된 데이터, 모델 파일을 저장할 수 있는 장점
     - 여러 버전의 모델을 앙상블 하기 위해 버전 별 폴더 추천
       - github 같은 코드 버전 관리 툴도 사용해 봤으나 큰 파일(전처리 데이터/모델 파일), 잦은 롤백 등의 이유로 최종 
       버전을 보관하는 용도로만 사용

   - 주피터에서 터미널을 열 수 있음

     ![]({{site.url}}/assets/images/boostcamp/8841d54a.png)

   - 이 터미널은 크롬 창을 닫아도 살아있으므로 원격 학습 가능!
  
