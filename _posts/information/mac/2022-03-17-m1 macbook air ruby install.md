---
title: "m1 맥북에어 ruby 재설치"

categories:
  - Information/mac
tags:
  - mac 
---

# m1 맥북에어 ruby 재설치

## 1. iterm2 or terminal 을 rosetta 로 실행하도록 세팅하기

### 순서
1. 응용프로그램에서 iterm2 우클릭 후 복제 선택
    ![](../../../assets/images/information/d538ad50.png)
2. iterm2 복사본 이름 변경 -> 저는 iterm2 rosetta 로 했습니다:)
    ![](../../../assets/images/information/99c4c51f.png)
3. 복사본 우클릭 후 정보가져오기 선택
    ![](../../../assets/images/information/31e62670.png)
4. Rosetta 를 사용하여 열기 선택
    ![](../../../assets/images/information/a3a8196d.png)

## 2. 현재 rbenv 제거하기

### 순서
1. iterm2 rosetta 에서 ```$rm -rf `rbenv root` ``` 실행
2. `brew uninstall rbenv`

## 3. ARM version Homebrew 삭제

```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)"```

## 4. x86_64 version Homebrew 설치

```arch -x86_64 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"```

## 5. `brew install rbenv` 실행

만약 "Error: Cannot install in Homebrew on ARM processor in Intel default prefix (/usr/local)!" 이 뜬다면
`arch -x86_64 brew install rbenv` 실행

## 6. 마지막으로 `arch -x86_64 rbenv install x.x.x`

이때, x.x.x 는 버전 ex) 3.0.3

## 설치 완료!
