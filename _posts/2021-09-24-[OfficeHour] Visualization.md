---
title: "Day_36 [오피스아워] 시각화"

categories:
  - Boostcamp_AI_Tech/Week_8/Day_36
tags:
  - 오피스아워
---
  
# [오피스아워] 시각화 - 장유진

## 시각화 대시보드 프로젝트 기본 프로세스

### 1. 현업에서의 데이터 시각화

#### 1.1 시각화의 방향

![]({{site.url}}/assets/images/c703fd01.png)

**연구와 활용 측면에서의 시각화의 구체적인 사례**

- 차트의 정보성을 극대화하기 위한 방법론 연구
- 연구 결과를 보고서에 차트로 첨부할 때 활용
- 실험을 하기 전 데이터를 파악하기 위한 탐색 과정
- 수집되고 있는 데이터 품질을 모니터링 대시보드
- 비즈니스에 필요한 핵심 속성을 전반적으로 표현한 대시보드
- 다른 팀과의 커뮤니케이션 및 보고용

#### 1.2 시각화의 원칙

**시각화의 오류 퀴즈 #1**

Q. 다음 그림에서 발생한 시각화의 오류는?

![]({{site.url}}/assets/images/c31b4163.png)

A. 잉크비례의 법칙을 지키지 않음

![]({{site.url}}/assets/images/c9accc2a.png)

Principle of Proportion Ink 잉크 비례의 법칙

**시각화의 오류 퀴즈 #2**

Q. 다음 그림에서 발생한 시각화의 오류는?

![]({{site.url}}/assets/images/975863bb.png)

A. 
1. 나라별 차트의 Y 축 간격이 단위에 비례하지 않음
2. Y 축이 시작할 때 0에서 시작하지 않음
3. 한국의 실업률이 3.7% 위쪽에 작성되어 있는데 미국의 실업률 4.0이 더 낮은 곳에 그려짐

![]({{site.url}}/assets/images/5a905edc.png)

**시각화를 할 때 지켜야 할 원칙**

- 상황과 데이터에 맞게 데이터 왜곡을 하지 않는 것
- 차트를 올바르게 사용하는 것
- 디자인의 조화
- Simple is the Best
- Principle of Proportion Ink 잉크 비례의 법칙
  - $\rightarrow$ 시각화에 정답은 없지만 지켜야 할 룰은 존재한다

#### 1.3 대시보드 예시

**With Python, R, and d3.js**

![]({{site.url}}/assets/images/4384360b.png)

**With Tableau and Power BI**

![]({{site.url}}/assets/images/c10132f5.png)

장점은 편의성 단점은 한계성을 가지고 있음

## 도구만 다를 뿐 시각화의 기본 원칙은 같다

### 2. 시각화 대시보드 프로젝트 기본 프로세스

#### 2.1 대시보드 프로젝트 기본 프로세스

**시각화 대시보드 프로젝트의 과정**

![]({{site.url}}/assets/images/7ae5b2ce.png)

1. DISCOVERY SESSION
- 시각화 대상자?
- 목적?
- 비즈니스 목표?
- 데이터?
- 기존에 사용하던 대시보드가 있는가?
- 대시보드를 표시하는데 사용할 장치 유형?
- 데이터와 그 데이터(플랫폼)에 대한 권한 요청
- ...등등

2. DATA SCHEMA

대시보드에 포함되어야 하는 모든 변수, 조건, 계산된 메트릭 등을 매핑하고 식별하는 스키마를 생성  
필요한 데이터가 없다면 생성 -> 코딩 필요

과정의 필요성: 데이터 관계 확인, 업무의 오류 방지

![]({{site.url}}/assets/images/9480a252.png)

3. WIREFRAME / RESEARCH

기존 템플릿 있다면 검토 추천  
논의 내용과 승인된 데이터 스키마에 따라 와이어프레임 생성  
리서치를 통해 필요한 차트 확인, 각 차트 활용법 계획

과정의 필요성: 비즈니스 상황에 맞게 요구조건을 확인하고 스토리라인 생성, 사용자 편의를 고려한 디자인

![]({{site.url}}/assets/images/003488b5.png)

4. DASHBOARD BUILD

승인된 와이어프레임에 지정된 모든 요소들을 대시보드에 추가

브랜드를 고려한 대시보드 (디자인, 컬러, 로고)

대시보드 초안을 최종사용자에게 승인 받고 최종본 완성

![]({{site.url}}/assets/images/edff6263.png)

5. QA TESTING

대시보드를 만들 때 필요한 QA 는 무엇이 있을까?

- 대시보드에 출력된 데이터가 raw 데이터에서의 출력된 결과와 맞는지
- 없어도 되는 조건을 걸어서 데이터를 필터링 할 수 있어서 정확한 데이터를 출력하는지 확인

![]({{site.url}}/assets/images/df206424.png)

6. DELEVERY & RUN THROUGH

내부적으로 대시보드 실행 최종 확인

회의를 통해 최종사용자에게 대시보드를 공유하고 대시보드를 활용한 통찰력 수집, 대시보드 활용 방법, 데이터 제안 등을 다루는 세션

세션을 통해 피드백과 질문, 그리고 다음 단계를 논의

#### 2.2 대시보드 제작할 때 유의사항

**프로젝트 유의사항**

- 소통은 짧고 굵게
- 제작하는 사람과 사용하는 사람이 다르면 프로젝트 기간이 지연되는 경우가 많음
- 대시보드에 사용자 중심의 용어와 UI 를 사용
- 차트를 보는 사람은 내가 아니라 최종사용자
- BI Tool 을 이용한 대시보드 제작에도 코딩이 필요 -> 코딩 능력이 있으면 유리

**자주 사용하는 도구**

- Color Picker - ColorZilla
- Color Palette Generator
- Google Drawings
- Data Studio Report Gallery
- Power BI Data Stories Gallery
- The Data Visualisation Catalogue
- ... 그리고 구글링!

![]({{site.url}}/assets/images/1ff1afd9.png)

#### 2.3 프로젝트 사례

![]({{site.url}}/assets/images/1ba5fe2f.png)

## 대시보드 프로젝트에서는 언제나 최종 사용자를 생각해야 한다.

대시보드는 내가 보여주고 싶은 것을 그리는 것이 아니라 최종 사용자가 보고 싶은 걸 그려야 한다.

### 3. Business Intelligence Tool

#### 3.1 BI Tool 의 종류 및 특징

**각종 BI Tool**

- Tableau
- Power BI
- Data Studio
- Qlik Sense
- Looker
- Oracle Analytics
- MicroStrategy
- Spotfire
- SAS Visual Analytics
- Yellowfin BI
- FineReport
- Sisense
- MicroStrategy
- Reeport

**Tableau**

데스크탑 기반 (Windows, Linux, Mac 을 지원)

장점: 차트 하나에 표현할 수 있는 **시각화 옵션이 다양**하고 자유로워 시각적 분석 가능한 범위가 넓음  
데이터에 분석에 적합한 UI. 차트들이 시각적으로 **예쁜 편**.  
AI 기반 인사이트 및 통계 엔진이 강력하다고 알려짐.  
각 차트별 필요한 Dimension 과 metric 의 **수가 표시** 됨

단점: 고도로 전문화된 기술과 인프라 투자가 필요.  
차트 및 대시보드 페이지를 모두 **개별적인 페이지로** 생성하여 연결해야함(세부적인 작업이 가능하다는 장점으로 생각될 수 있지만 업무가
복잡해지는 느낌)

**Power BI**

데스크탑 기반(Wiindows만 지원) / 웹 버전도 있으나 UI 가 다소 불편함

장점 : **MS 소프트웨어 데이터** 그대로 이용 가능.  
데이터를 전처리하기 위해 SQL 데이터 엔지니어가 필요하지 않음.  
AI 시각화 및 기능이 있어 비즈니스 분석가와 데이터 과학자가 조직 전체에서 공동으로 작업 가능.  
**R, Python, ArcGIS 등 다양한 분석 플랫폼을 통합** 사용 가능.

단점: 다양한 기능만큼 많은 레이어가 있어 복잠.  
Power BI 의 고급 기능을 최대한 활용하려면 **DAX

**Data Studio**

웹기반 / 무료

장점 : Tableau 및 Qlik 등에 비해 **쉬운 접근성**과 비용의 이유로 많이 선택.  
액세스가 쉬운

**Qlik Sense**

웹기반 / QlikView 의 최신 버전

장점 : **데이터 처리 엔진은 매우 빠르며**

**Looker**

클라우드 기반

장점 : 다른 BI Tool 에 비해

**자바스크립트 라이브러리 D3.js**

#### 3.2 활용 방향 비교

**어떤 상황에 사용하는 것이 좋을까 (개인적인 의견)**

- Tableau -> 가장 대중적인 툴을 익혀보고 싶을 때
- Power BI -> 디자인보다는 정보성이 중요할 때
- Data Studio -> 웹 기반으로 접근성 좋은 시각화가 필요할 때
- Qlik Sense -> 철저한 데이터 보안성이 요구될 때
- Looker -> 기존 BI

**무료 사용 방법 (링크)**

- Tableau
- Power BI
- Data Studio

## 완벽한 BI Tool 은 없다.

어떤 BI Tool 이든 장점과 단점이 있고 완벽한 Tool 은 아직 존재하지 않습니다.

데이터와 상황에 맞게

### 4. 일상과 취업을 위한 시각화

우리에게 어떤 시각화가 필요한가?

#### 4.1 데이터 리터러시

**구글도 강조한 '데이터 리터러시'의 중요성

"데이터 리터러시 역량은 누가 어떤 비즈니스에 종사하든 관계없이, 앞으로 10년간 가장 중요한 비즈니스 능력이 될 것이다."
- 구글의 수성 이코노미스트 할 베릴안 (Hal V)

**데이터 리**

#### 4.2 AI Engineer 에게 요구하는 시각화 능력

**업무에 어느 정도의 시각화 능력이 필요한가**

- 파이썬 라이브러리 Matplotlib, Seaborn 경험
- 시각화의 기본 원칙 숙지
- 시각화에 필요한 기초 통계
- 데이터에 알맞는 시각화를 할 수 있는 능력
- BI Tool 은 필수 요건이 아닌 우대사항

**데이터에 맞는 시각화 능력을 기르기 위한 방법**

- 각 도메인의 통상적인 시각화 사례 공부
  - 각 도메인의 서적들이나, 학위 논문 추천
- 데이터가 갖고있는 질문에 대한 답변을 줄 수 있는 시각화가 무엇일지 고민
- 경험 누적이 가장 큰 도움

## BI Tool 은 우대사항, 프로그래밍 능력이 더 중요

---

# [오피스아워] 시각화 - 이호준

## Visual Analytics 의 필요성

### 1. Introduction to Visual Analytics

#### 1.1 Dive into Visualization Research

**우리는 지금까지 Data Visualization 을 위주로 학습을 진행**

![]({{site.url}}/assets/images/f3023ef2.png)

**Data Visualization**

Communicatate data or information by encoding it as visual **objects**

텍스트로부터 발견할 수 없는 **Trend, Pattern** 등을 발견

![]({{site.url}}/assets/images/a611dfae.png)

**Visualization + Research?**

IEEE VIS
- InfoVIS
- SciVis
- Visual Analytics

![]({{site.url}}/assets/images/3c4408c3.png)
![]({{site.url}}/assets/images/de1c1564.png)

올해부터 하나로 합쳐짐

**Information Visualization (InfoVis)**

**Abstract** Data to Reinforce human cognition

![]({{site.url}}/assets/images/4b25172b.png)

**Scientific Visualization(SciVis)**

- **Spatial** Data
- Concerned on graphically illustrate scientific data

![]({{site.url}}/assets/images/244a3782.png)

태풍의 이동 반경 시각화 등

**Visual Analytics**

The science of analycial reasoning supported by the **interactive** visual interface

데이터마이닝, 기계학습론 등 다양한 기술 사용  
$\rightarrow$ Human-centered Data Exploration 구현!

![]({{site.url}}/assets/images/b62cc116.png)

데이터를 csv 나 table 로 받게 되면 눈이 아픔 한눈에 파악하기 힘듦  
그런것들을 쉽게 하나로 표현

**Interactive Data Visualization 과는 어떤 차이가 있지?**

Interactive Data Viz는 빙산의 일각

이외에 다양한 Process 가 필요  
(Data Transformation, Data Understanding, ...)

**Scope of Visualization Analytics**

![]({{site.url}}/assets/images/33ae72dd.png)

여러분야를 아우르는 굉장히 융합적인 분야

**Visualization in 1990s**

![]({{site.url}}/assets/images/66b62e57.png)

**Visualization in 2000s**

![]({{site.url}}/assets/images/f7416a1e.png)

- Data Mining 이 추가됨
- Interaction 이 늘어남

**Visualization in 2010s**

![]({{site.url}}/assets/images/352d9a88.png)

- 딥러닝이 나오니까 Visualization 을 딥러닝 분야에 활용해보자라는 Agenda 가 나옴
  - 블랙박스 적인 부분을 시각적으로 활용할 수 있지 않을까하는 생각
- 대시보드를 만드는 과정 자체에도 딥러닝을 넣는 것
  - 사용자가 의사결정을 하는 과정에서도 딥러닝을 활용해서 더 좋은 결과를 내는 발전도 있음

Visualization 이 진화하고 있음  
시대의 흐름에 따라서 프로세스가 바뀌고 있음  

### 2. Example of Visual Analytics: VATLD

IEEE VIS VAST 2020 에 소개된 Visual Analytics 를 활용한 예시를 살펴봅니다.

#### 2.0 VATLD?

![]({{site.url}}/assets/images/82553617.png)

대시보드를 활용해서 Traffic Light Detection 문제를 어떻게 이해하고 성능을 Improve 시킬지에 대한 논문

#### 2.2 Structure of VATLD

**Data Processing / Data Representation / Interactive Visualization / VA-assisted Improvements**

---

# Q & A

> 시각화 연습을 꾸준히 하기 위한 멘토님들만의 연습 방법이 따로 있을까요?

- 장유진 멘토
  - 부스트캠프에서 competition 에 참여하면서 많이 연습해보면 좋겠음  
  - 이슈를 맞이하고 그걸 해결하기 위해 시각화를 고려해보는게 중요함
  - 데이터가 가진 문제를 해결하기 위해 어떤 시각화를 해야할까? 하는 고민이 연습이 될 것 같음
  - 각각의 데이터를 다룰때 사용하는 차트들이 다르고 그렇기 때문에 다양한 데이터를 확인해보면 좋겠음
  - 학위논문, NLP 대가의 블로그 포스팅 등
- 이호준 멘토
  - 반년에서 1년동안 삽질했던 것이 강의에 녹아있음
  - 이 강의를 2번 3번 듣는 것이 좋음
  - 꾸준히 하려면 재밌어야 함
  - 관심있어하는 도메인이 있을 것이고 그 관련 데이터를 시각화해보는 고민

> 데이터 사이언스 과점에서 HCI 에 대해서도 공부할 필요성이 있을까요?

- 장유진 멘토
  - 회사의 동기분이 HCI 를 석사전공하고 analytics 와 optimization 분야에서 일하고 있는데 그 관점에서 고민을 많이 
  하시고 재밌어하심
  - 새로운 시각도 갖고 계심
  - 도움이 될 것 같고 우선순위를 정해서 공부하기를 추천


