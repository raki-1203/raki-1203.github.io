---
title: "Mecab 과 Khaiii 를 설치해서 한국어 전처리 실습 환경 만들기 on linux"

categories:
  - Setting
tags:
  - Mecab
  - Khaiii
---
  
# Mecab 과 Khaiii 를 설치해서 한국어 전처리 실습 환경 만들기 on linux

```
sudo apt install g++
sudo apt update
sudo apt install default-jre
sudo apt install default-jdk
pip install konlpy
```

## Install khaiii
```
cd ~
git clone https://github.com/kakao/khaiii.git
cd khaiii
mkdir build
cd build
pip install cmake
sudo apt-get install cmake
cmake ..
make resource
sudo make install
make package_python
cd package_python
pip install .
cd ~
apt-get install locales
locale-gen en_US.UTF-8
pip install tweepy==3.7.0
```

## Install mecab
```
wget https://bitbucket.org/eunjeon/mecab-ko/downloads/mecab-0.996-ko-0.9.2.tar.gz
tar xvfz mecab-0.996-ko-0.9.2.tar.gz
cd mecab-0.996-ko-0.9.2
./configure
make
make check
sudo make install
sudo ldconfig
cd ~
wget https://bitbucket.org/eunjeon/mecab-ko-dic/downloads/mecab-ko-dic-2.1.1-20180720.tar.gz
tar xvfz mecab-ko-dic-2.1.1-20180720.tar.gz
cd mecab-ko-dic-2.1.1-20180720
./configure
make
sudo make install
cd ~
mecab -d /usr/local/lib/mecab/dic/mecab-ko-dic
apt install curl
apt install git
bash <(curl -s https://raw.githubusercontent.com/konlpy/konlpy/master/scripts/mecab.sh)
pip install mecab-python
```

## 사용법

```python
from konlpy.tag import Mecab
from khaiii import KhaiiiApi

mecab = Mecab()
khaiii = KhaiiiApi()

text = "klue re 대회 우리 모두 하루하루 배워가며 성장해나가요!"

print(mecab.pos(text))

for tk in khaiii.analyze(text):
    token_with_pos = str(tk).split("\t")[1]
    for tk_w_pos in token_with_pos.split(" + "):
        token, pos = tk_w_pos.split("/")
        print(f"('{token}', '{pos}')")
```


