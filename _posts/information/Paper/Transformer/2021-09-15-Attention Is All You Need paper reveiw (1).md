---
title: "Attention Is All You Need paper review (1)"

categories:
  - Transformer
tags:
  - Paper
---
  
- 1편 [Attention Is All You Need Review (1)]({{site.url}}/transformer/Attention-Is-All-You-Need-paper-reveiw-(1)/)
- 2편 [Attention Is All You Need Review (2)]({{site.url}}/transformer/Attention-Is-All-You-Need-paper-reveiw-(2)/)
- 3편 [Attention Is All You Need Review (3)]({{site.url}}/transformer/Attention-Is-All-You-Need-paper-reveiw-(3)/)
- 4편 [Attention Is All You Need Review (4)]({{site.url}}/transformer/Attention-Is-All-You-Need-paper-reveiw-(4)/)

# Attention Is All You Need paper review (1)

부족하겠지만 처음으로 내 스스로 논문을 읽고 정리해보려 함

영어실력의 부족으로 번역에 문제가 좀 있을 수 있으니 오역의 부분이 있다면 댓글을 달아주시면 좋을듯 함

## Abstract

![]({{site.url}}/assets/images/boostcamp/f4d72f81.png)

지배적인 sequence 를 변환하는 모델은 복잡한 Encoder & Decoder 를 포함한 RNN or CNN 으로 기초하고있음

가장 성능이 좋은 모델은 attention mechanism을 통한 encoder and decoder 연결한 모델임

우리는 recurrenct 와 convolution 을 완전히 제거하고 오직 attention mechanism 을 이용한 간단한 구조를 가진 네트워크인 
Transformer 를 제안함

두가지 기계번역에 대한 실험은 이 모델이 더 병령화 가능해지고 학습에 필요한 시간이 상당히 적어지는 동안 품질면에서 우수함을 보여줌

우리의 모델은 WMT 2014 English-to-German translation task 에서 앙상블을 포함해 기존의 최고 결과를 BLEU 스코어를
2만큼 올리면서 28.4 BLEU 스코어를 달성함

WMT 2014 English-to-French 번역 task 에서 우리의 모델은 다른 paper 로 부터 나온 최고 모델들의 학습 비용(resource?)의 작은 양인 
8개의 GPU 를 사용해 3.5일 동안 학습한 후에 새로운 단일 모델로 41.0 BLEU 스코어를 달성했음

## 1. Introduction

![]({{site.url}}/assets/images/boostcamp/5c80a0fc.png)

특별히 LSTM, GRU 인 RNN 은 다음에 나올 단어(문자)를 예측하는 Language Modeling 과 기계번역 같은 sequence modeling 과 
sequence transduction 문제에서 SOTA 접근방법으로서 굳게 자리잡았음

recurrent language models 과 encoder-decoder 구조의 한계를 넘기위해 많은 노력이 계속되고 있음

![]({{site.url}}/assets/images/boostcamp/987b13a1.png)

Recurrent 모델들은 일반적으로 input sequence 와 output sequence 의 토큰 위치에 따라 계산을 분해함

계산시점에 따라 위치를 정렬하면서 Recurrent 모델들은 $t$ 시점의 input 과 이전 시점의 hidden state 인 $h_{t-1}$ 의 함수 값으로서
sequence 의 $h_t$ 를 생성함

이런 본질적인 연속적인 특성은 학습 샘플안에서 병렬화를 배제함 그리고 이 특징은 샘플의 배치를 제한하면서 메모리 제약때문에 더 긴 sequence 길이에서 치명적임

최근 연구는 factorization trick 들과 conditional computation 을 통해서 계산 효율성에서 상당한 발전을 이룸

conditional computation 의 경우 모델 성능도 향상 시킴

그러나 근본적인 연속적인 계산의 제약은 여전히 남아있음

Attention 기법은 input 또는 output sequence 에서 그들의 거리에 관계없이 의존성 모델링을 허락하면서 다양한 task 의 sequence modeling 과 
transduction 모델등에서 강요하는(빠질 수 없는) 완전한 부분이 되고 있음

그러나 attention 기법은 reccurent 네트워크와 연계되서 사용됨

이 연구에서 우리는 input 과 output 사이의 global 의존성을 찾기위해 전적으로 attention 기법에 의존하는 대신에 reccurence 를 피한 모델 구조인
Transformer 를 제안함

Transformer 는 좀 더 유의미한 병렬화를 허락하고, 8개의 P100 GPU 로 12시간 정도만 학습한 후에 번역 퀄리티에서 새로운 SOTA(State Of The Art)를
도달 할 수 있음

## 이 다음 부분은 다음편에서 작성하도록 하겠음




