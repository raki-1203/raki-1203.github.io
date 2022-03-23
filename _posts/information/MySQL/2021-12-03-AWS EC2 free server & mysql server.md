---
title: "AWS EC2 서버에 MySQL 설치하기"

categories:
  - Install
tags:
  - AWS
  - EC2
  - MySQL
---
 
# AWS EC2 서버에 MySQL 설치하기

먼저 해야할 것은 서버 세팅입니다.
 
1. 지역 설정
2. OPT 설정
3. EC2 생성
4. mysql 설치 및 설정

## 1. 지역 설정

AWS 에 가입은 했다는 가정하에 진행할게요!

![]({{site.url}}/assets/images/boostcamp/9fc3b9d3.png)

지역을 서울로 바꿔줍니다.

서버컴퓨터도 하드웨어 장치가 어디에 위치해있을건데 그걸 인터넷으로 원격으로 서버를 생성하고 삭제하고 하는 거에요

그 장치의 위치를 선택하는거에요

우리는 한국에있죠?

서울에 있는 서버로 접속해야 명령이 빠르게 입력이됨

만약에 먼 곳 미국 동부에 서버 설정해서 접속하면 좀 느릴 수 있어요

그래서 서울에다가 인스턴스를 만들도록 할게요

참고로 미국이 서울(아시아권)보다 서버 비용이 싸요 절반이에요!!

우리가 사용할 EC2 서버 클라이언트는 트래픽에 따라서 사용 시간에 따라서 비용이 부과됩니다.

처음 가입했다면 1년동안 한달에 750시간 무료에요!!

거의 과금이 되지 않을거에요 ㅎㅎ 아마도? ㅎㅎ

## 2. OPT 설정

### 1. 보안 자격 증명 으로 이동

![]({{site.url}}/assets/images/boostcamp/fa769962.png)

빨간 박스로 되어있는 부분은 아이디가 적혀있는 부분인데요

저길 클릭하고 `보안 자격 증명` 을 클릭해서 들어갑니다.

### 2. 멀티 팩터 인증(MFA)

![]({{site.url}}/assets/images/boostcamp/ead37aa6.png)

`멀티 팩터 인증(MFA)` 를 클릭해서 위와 같은 화면이 나오면 `MFA 활성화` 버튼을 클릭!

![]({{site.url}}/assets/images/boostcamp/52fca9b1.png)

이 화면이 나오면 `계속` 을 눌러줍니다.

![]({{site.url}}/assets/images/boostcamp/93009e64.png)

`비밀 키 표시` 를 눌러주세요

![]({{site.url}}/assets/images/boostcamp/9ce33f48.png)

빨간박스 부분에 비밀 키가 생성되었어요

이걸 복사해서 Twilio Authy 라는 프로그램을 사용해서 MFA 코드를 생성해줄거에요!

없으신분은 https://authy.com/download/ 여기에 들어가서 다운받으시고 설치하면 됩니다.

![]({{site.url}}/assets/images/boostcamp/d98e07e1.png)

다운받으신 후 실행하시면 이런 화면이 뜰거에요!

저는 두개정도 추가를 해둬서 좀 가려놨는데 이제부터 새로 AWS 아이디와 Twilio Authy 를 연결할게요

![]({{site.url}}/assets/images/boostcamp/17f72da5.png)

`+` 버튼을 클릭할게요!

![]({{site.url}}/assets/images/boostcamp/7db21a8e.png)

위에서 `비밀 키 표시` 를 클릭해서 나왔던 코드를 복사해서 붙여넣어줍니다.

`Add Account` 버튼을 클릭할게요!

![]({{site.url}}/assets/images/boostcamp/cc50b9cb.png)

이제 Account Name 과 색을 지정하고 Save 하면 끝났습니다!

![]({{site.url}}/assets/images/boostcamp/b37c49e8.png)

다시 여기로 돌아와서 3. 아래에 2개의 연속된 MFA 코드 입력 란이 보이죠?

여기에 Twilio Authy 에서 나오는 코드를 한번 붙여넣고 두번째 코드가 나오길 기다렸다가 연속된 두 코드를 붙여 넣어주면 됩니다.

마지막으로 `MFA 할당` 버튼을 클릭해주세요!

그러면 OPT 설정은 완료되었습니다!

이제부터는 AWS 에 로그인할때 MFA 인증코드를 입력해야 들어갈 수 있을거에요

이러면 누군가 해킹해서 사용하지 못하겠죠?

이걸 방지하기 위함입니다.

꼭 설정하지 않으셔도 되요 ㅎㅎ

## 3. EC2 생성

다음은 EC2 인스턴스 생성해보도록 할게요!

AWS 에서 EC2 페이지로 들어옵니다.

검색창에 EC2 를 검색해도되고 서비스탭에서 EC2 를 찾아서 들어와도 됩니다.

![]({{site.url}}/assets/images/boostcamp/7bfa6e05.png)

저는 이렇게 검색해서 EC2 를 클릭해서 들어갈게요!

![]({{site.url}}/assets/images/boostcamp/286f5176.png)

왼쪽에 인스턴스를 클릭해서 들어오면 처음 가입하신 분들은 아무것도 없을거에요

저는 하나 미리 생성해서 저렇게 실행중인 인스턴스가 있습니다.

오른쪽 상단에 `인스턴스 시작` 을 클릭해서 생성을 해봅시다.

![]({{site.url}}/assets/images/boostcamp/6f1162cf.png)

스크롤을 좀 내리면 `Ubuntu Server 18.04 LTS (HVM), SSD Volume Type` 이 보일거에요!

프리 티어 사용 가능 적혀있는지 확인하시고 선택을 눌러줍니다.

![]({{site.url}}/assets/images/boostcamp/864c80ee.png)

t2.micro 라고 되어있는게 프리 티어 사용 가능 이라고 적혀있으니 저걸 선택하고 `검토 및 시작` 을 클릭합니다.

![]({{site.url}}/assets/images/boostcamp/23d69ce7.png)

여기서 시작하기를 눌러주세요!

![]({{site.url}}/assets/images/boostcamp/9cff5ca4.png)

그러면 이런 화면이 뜨는데요!

새 키 페어 생성을 클릭합니다.

![]({{site.url}}/assets/images/boostcamp/800260d8.png)

키 페어 이름을 입력해주세요

그 다음 `키 페어 다운로드` 를 클릭해서 pem 파일을 다운로드 받습니다.

이 다운로드된 파일은 ssh 서버 연결시 사용되니까 잘 보관해주세요~

저는 ~/.ssh 폴더에 옮겨놓고 사용하고 있습니다. ㅎ

그리고 파일 권한을 변경해주세요!

`chmod 400 ~/.ssh/{키 페어 저장이름}.pem`

`인스턴스 보기` 를 클릭하면 EC2 인스턴스 탭을 눌렀을 때 나오는 화면으로 이동하는데요

인스턴스 상태가 실행 중 으로 바뀌면 인스턴스가 생성이 되고 실행까지 완료되었습니다!

![]({{site.url}}/assets/images/boostcamp/376086c4.png)

여기서 생성한 인스턴스를 클릭하면 밑에 인스턴스의 정보가 나오는데요

퍼블릭 IPv4 주소가 생성된 서버로 접속할 수 있는 ip 주소가 됩니다.

서버에 접속하는 방법은 terminal 에서 아래 명령어를 입력해주시면 됩니다.

`ssh -i ~/.ssh/{키 페어 저장이름}.pem ubuntu@{퍼블릭 주소}`

## 4. mysql 설치 및 설정

### 서버에 접속하신 후 terminal 에서 명령어를 입력합니다.

`sudo apt install mysql-server`

### 이제 입력을 잘해야해요!!! 잘못하면 지웠다가 다시 깔아야해요!

`sudo mysql_secure_installation`

첫번째 선택지는 setup VALIDATE PASSWORD plugin 을 설정할지 말지인데요

비밀번호를 복잡하게 설정하도록 하는 plugin 인데요 

회사에서는 설치해서 사용하시되 여기서는 쉽게 넘어가기 위해서 `n` 을 입력할게요!

그러면 비밀번호를 입력하라고 나와요!

여기서 원하는 비밀번호를 입력하세요

저는 예시로 `raki` 라고 입력했다고 할게요

그러면 두번째 선택지가 나오는데요 anonymous users 를 지울거냐고 하네요?

익명유저를 지우도록 하겠습니다. `y`

세번째 선택지가 나왔습니다 이거 굉장히 중요해요!!

root login remotely? 외부 접속을 허용할지 않을지 물어본거에요 이건 무조건 `n` 을 입력해주셔야해요!

외부접속을 할거니까요!

Remove test database? 이거 지울게요! `y`

Reload privilege tables now? 설정들을 바꿨는데 이 설정들을 적용할지 물어보는거에요! `y` 적용할거에요!

그러면 All Done! 이 뜨고 설정이 완료되었습니다

### mysql 설치하고 설정을 적용했는데 최초에 서버에 들어갈때는 `최초 패스워드를 설정`해야해요!

아까 비밀번호 설정한것과 별개로 mysql database 설정 파일안에 비밀번호를 추가로 설정해야해요!

```
$ sudo mysql
mysql> SELECT user, authentication_string, plugin, host FROM mysql.user;
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'raki';
mysql> FLUSH PRIVILEGES;
mysql> SELECT user, authentication_string, plugin, host FROM mysql.user;
mysql> exit
```

이 명령어를 차례대로 입력하시면 

처음 명령어를 통해 나온 결과물엔 root 의 authentication_string 이 비어있어요 여기에 비밀번호가 들어가야해요!

두번째 명령어를 입력하면 비밀번호가 저장됩니다. 마지막에 'raki' 는 비밀번호를 입력한거에요

세번째 명령어를 실행하면 변경된 설정이 적용이됩니다!

네번째 명령어는 첫번째 명령어와 똑같은데 이제 root 의 authentication_string 에 비밀번호가 들어간걸 확인할 수 있을거에요!

마지막으로 exit 눌러서 나와주세요!

이렇게 하면 최초 패스워드 설정이 완료되었습니다!

### 이제 mysql 서버에 접속하기 위해서는 아래 명령어를 수행하면 됩니다.

`$ mysql -u root -p`

이 명령어를 실행하면 비밀번호를 입력하라고 나오는데요 아까 설정한 'raki' 를 입력하시면 서버에 접속이됩니다

여기서 `-u` 는 user 라고 생각하면 되고 `-p` 는 password 라고 생각하면 됩니다

### 외부 접속 허용을 위한 설정을 진행할게요

`$ sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

`bind-address` 를 찾아서 127.0.0.1 $\rightarrow$ 0.0.0.0 으로 변경해주세요! 

127.0.0.1 은 localhost 를 의미하고 자기 서버에서만 접속이 가능한거에요! 이걸 0.0.0.0 으로 바꾸면 모든 ip 에서 접속이 가능합니다.

이때 vim 단축키 팁은 w 를 누르면 단어단위로 오른쪽으로 커서가 이동합니다. D 를 누르면 뒤에있는 문자가 다 삭제되요!

i 를 누르면 INSERT 모드로 바뀌고 수정할 수 있게됩니다.

마지막으로 :wq 하고 저장해서 나올게요!

이제 mysql 에 접속해서 외부접속이 허용되도록 mysql 설정할게요!

```
$ mysql -u root -p
mysql> grant all privileges on *.* to 'root'@'%' identified by 'raki';
mysql> exit
```

설정이 바꿔줬고 끝났으니 설정이 적용되도록 restart 하겠습니다.

`$ sudo systemctl restart mysql.service`

아무것도 안나오는게 정상이구요!

`$ sudo systemctl status mysql.service`

이 명령어를 입력해서 `active (running)` 이걸 확인하면 정상 작동한거에요!

### 마지막으로 mysql 포트가 3306 이 기본인데 서버에서 3306 포트를 활성화시켜 주도록 할게요!

![]({{site.url}}/assets/images/boostcamp/5a3027ef.png)

AWS 페이지에서 아래에 보면 `보안` 탭을 클릭합니다.

![]({{site.url}}/assets/images/boostcamp/a0b327b3.png)

보안 그룹 파란색 글씨로 되어있는부분 클릭합니다

![]({{site.url}}/assets/images/boostcamp/fba0efb1.png)

여기서 오른쪽 아래부분에 `인바운드 규칙 편집` 을 클릭해주세요

![]({{site.url}}/assets/images/boostcamp/7b1f49bb.png)

`규칙 추가` 를 클릭하고 `포트 범위` 에 3306 을 입력해주고 소스 돋보기 옆에 `0.0.0.0/0` 을 입력하고 `규칙 저장` 을 클릭하면 완료입니다.

드디어 설정 끝!

이제 외부에서도 mysql 에 접속이 가능해졌어요!

mac 사용자분들은 Sequel Pro 를 사용하시면 될 듯하고 windows 분들은 Heidi SQL 사용하면 쉽게 접속 가능할 것 같습니다!!

이상으로 오늘의 포스팅을 마치겠습니다.



