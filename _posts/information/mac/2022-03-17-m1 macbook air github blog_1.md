---
title: "m1 맥북에어 github blog 관리"

categories:
  - GitHubBlog
tags:
  - mac
  - GitHubBlog
  - Ruby
  - Jekyll
---

# m1 맥북에어 github blog 관리

# 블로그 포스팅 방법

_posts 폴더에 yyyy-mm-dd-파일이름.md 형식으로 파일을 만들어 준다.
ex) 2021-05-29-github.md 그후

```
---
title: "제목"
excerpt: "부제"

categorise:
  - 카테고리명
tags:
  - 태그명
---
여기엔 Markdown문법으로 적으면 된다.
```

이런식으로 적고 git push로 GitHub에 올려주면, 포스팅이 된다.

하지만, 보통 push를 하면 1~3분 정도 걸리니 그전에 확인하는게 좋다. 그래서 설치한것이 전에 포스팅한 Ruby와 Jekyll이다.

## 내 맥북에서 블로그 미리보는 방법

iterm2 에서 github blog 폴더로 이동해 `$ bundle exec jekyll serve` 명령어 실행하면

http://localhost:4000/를 통해서, 내 블로그를 깃허브에 올리기전에 미리 보면서 수정할 수 있다.
