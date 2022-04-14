---
title: "[Week12] Machine Reading Comprehension"
permalink: /Boostcamp_AI_Tech/Week_12/
layout: category
author_profile: true
sidebar:
    nav: "docs"
---

### [Day50] MRC 8 ~ 10강

- [01. Reducing Training Bias]({{site.url}}/boostcamp_ai_tech/week_12/01.-Reducing-Training-Bias/)
- [02. Closed-book QA with T5]({{site.url}}/boostcamp_ai_tech/week_12/02.-Clased-book-QA-with-T5/)
- [03. QA with Phrase Retrieval]({{site.url}}/boostcamp_ai_tech/week_12/03.-QA-with-Phrase-Retrieval/)
- [오피스아워 Elastic Search - 서중원 멘토]({{site.url}}/boostcamp_ai_tech/week_12/OfficeHour-Elastic-Search/)

### [Day51] 

- [MeetUp 성장을 좋아하는 사람이 성장하고 싶은 사람에게 - 변성윤 마스터]({{site.url}}/boostcamp_ai_tech/week_12/MeetUP-ByunSungYoon/)

### [Week12 피어세션 정리](https://github.com/sangmandu/SangSangPlus/tree/main/Meet-up%20log/Week%204)

---
### 학습회고

이번주는 강의도 강의였지만 대회에서 아이디어를 구현하느라 굉장히 많은 시간을 사용하고있다.

팀원들과의 협업도 github project 와 issue 그리고 pull request 까지 다양한 기능을 사용하면서
진행하고 있다.

이번주에는 baseline 코드에서 공통된 부분을 최대한 줄인 후에 시작하고 싶어서 code refactoring 을 진행한 후
closed book QA 를 구현해보려 진행했다.

물론 제공된 실습코드들을 보면서 구현은 할 수 있었으나 뭔가 제대로된 답변을 생성해내지 못하는 것 같았다.

3일동안 붙잡고 구현하고 evaluation 을 어떻게 해야하나 고민하고 학습된 모델로 결과도 뽑아보고 해봤지만
결과가 형편없었다.

데이터의 부족인가? 아니면 학습방법이 잘 못 되었나? 한국어로 pre-train 된 모델이 다양하지 않은건가?

우리의 fine-tuning dataset 이 부족한건가?  

다양한 고민을 해보면서 결국 중도 포기했다.

같은 조의 다른 분이 다시 시도해보고 싶다고 했는데 잘 되었으면 좋겠고 내가 못했던 부분에서의 인사이트를 좀 얻고
싶다.

작업을 끝내고 다른 팀원들이 Dense retrieval 을 구현하고 있었는데 막히는 부분이 많고 좀 시간이 걸리는 듯 하여
뒤늦게 구현에 동참했다.

빠르게 구현했고 아직 test 단계가 남아있지만 주말의 나에게 맡겨보려한다.

이번 대회에서는 좋은 결과가 있었으면 하는데 다른 분들이 워낙 잘하는 것 같아 보인다 ㅎㅎ

벽이 있는 느낌이랄까 ㅎㅎ

그렇지만 내 위치에서 최선을 다해서 공부하고 알아가보려한다.

부족하지만 논문도 조금씩조금씩 읽고 있고 그 아이디어를 구현도 해보고 굉장히 어렵지만 하나하나 해나가는 기쁨이
있음을 느낀다.

성적보다는 프로젝트관리와 배움의 과정에서 만족하는 건 너무 아쉽다 ㅋㅋㅋㅋㅋㅋ

진짜 상위권으로 올라가고 싶다. 남은 2주 파이팅하자!!
