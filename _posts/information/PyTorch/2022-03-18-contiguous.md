---
title: "PyTorch .contiguous() 가 뭘까?"

categories:
  - PyTorch
tags:
  - PyTorch
---
  
# PyTorch .contiguous() 가 뭘까?

pytorch 를 사용하다보면 코드속에 .contiguous() 가 가끔 보이는데 없어도 지장이 없을거 같은데 
무슨 의미일지 궁금한 경우가 있어서 알아보려한다.

이는 연속적인 메모리 텐서를 반환하는 메서드로 만약 어떤 연산을 사용할 때 이를 사용하지 않으면
에러가 발생하는 경우가 생긴다.

예로 아래와 같이 a 라는 텐서를 만들고 텐서의 형태(shape)와 보폭(stride)을 살펴보면 다음과 같다.

```python
a = torch.randn(2, 4, 6)
a.size()
> torch.Size([2, 4, 6])
a.stride()
> (24, 6, 1)
```

여기서 보폭은 해당하는 차원의 원소에 접근할 때 건너 뛰어야 할 원소들의 수(보폭)를 의미한다.

위의 예로 0차원 에서 건너 다음 원소를 가져올때는 24개의 원소를 뛰어 넘어야 한다는 의미이다.

하지만 메모리에 연속적으로 값이 들어있지 않은 경우에는 말이 좀 달라진다.

예로 아래와 같이 a 텐서의 차원 0과 1을 바꾸어 보았다. 그리고 텐서의 형태가 바뀐 a 와 같은 
형태의 b 를 만들어서 비교해보면 다음과 같다.

```python
a = a.transpose(0, 1)
a.size()
> torch.Size([4, 2, 6])
a.stride()
> (6, 24, 1)
a.is_contiguous()
> False
b = torch.randn(4, 2, 6)
b.stride()
> (12, 6, 1)
b.is_contiguous()
> True
```

여기서 눈여겨 볼점은 a 와 b 가 (4, 2, 6) 로 같은 shape 을 가지지만 실제 원소에 접근하기 위한 
보폭을 살펴보면 값이 다르다는 점(a: [6, 24, 1], b: [12, 6, 1])을 확인할 수 있다.

이런 이유는 텐서 a 의 형태가 변화될 때 실제로 해당 원소에 접근할때는 (메모리에서는 원소들의) 
위치가 변화되지 않았고 접근 인덱스만 변화되었기 때문이다.

이는 pytorch 에서 일부 텐서 연산을 수행함에 있어서 성능향상을 위한 것으로 생각된다. (만약 텐서의
형태가 바뀔때마다 메모리에 있는 원소들도 재할당을 해줘야 하는데 이러한 연산이 잦으면 오히려 성능을
떨어뜨리는 원인이 될 수 있다.)

그래서 형태가 바뀐 a 의 보폭을 해석해보면 차원 0에서 다음 원소에 접근할 때 12개가 아닌 6개의 원소만
건너면 b 왁 같은 텐서처럼 사용을 할 수가 있다는 의미로, 실제 메모리에서는 a 와 b 가 다른 순서로
배열이 되어있으나 메모리 재할당을 할 필요 없이 접근 인덱스만 바꾸면 b 처럼 사용을 할 수가 있다는
의미가 된다.

그리고 .contiguous() 메서드는 다음과 같이 이러한 a 와 같은 비연속적인 텐서를 연속적으로 만들어주는
역할을 한다.

```python
a = a.contiguous()
a.stride()
> (12, 6, 1)
```

이제 텐서 b 랑 같아졌다.

이래의 예는 contiguous 하지 않은 텐서를 펴서 사용할 때 접할 수 있는 에러이다.

```python
a = a.transpose(0, 1)
a = a.view(-1)
> RuntimeError: view size is not compatible with input tensor`s size and stride 
(at least one dimension spans across two contiguous subspaces). Use .reshape(...) instead.
```

이를 해결하려면 텐서를 연속적으로 만들어주면 된다.

```python
a = a.contiguous()
a = a.view(-1)
a.size()
> torch.Size([48])
```

또는 .contiguous() 없이 아래와 같이 사용이 가능하다.

```python
a = torch.randn(4, 2, 6)
a = a.transpose(0, 1)
a = a.reshape(-1)  # view() 대신 reshape() 사용
a.size()
> torch.Size([48])
```

> Reference

https://titania7777.tistory.com/3




