# 가짜연구소 블로그

[블로그 바로가기](https://pseudolab.github.io/)

## 블로그 포스트 작성 방법
- _posts/ 폴더 안에 .md 파일로 작성하시면 됩니다.
- 아래 포맷에 맞춰 .md 파일 최상단에 7줄을 작성해주세요.
```
---
layout: post
title:  "제목 작성"
author: 작성자
categories: [ tag1, tag2 ]
image: assets/images/그림.jpg
---
```
- `layout: post`는 바꾸지 않으셔도 됩니다.
- categories는 `,`로 구분하셔야 합니다.
- 대문 사진으로 사용할 이미지를 assets/image/ 폴더 안에 jpg 파일로 넣고, `image`에 설정하시면 됩니다.

### 자주쓰는 마크다운 문법
- `[가짜연구소](https://pseudo-lab.com/)`  =  [가짜연구소](https://pseudo-lab.com/)
- `**굵게**`  =  **굵게**
- `~~취소선~~`  =  ~~취소선~~
- `<u>밑줄</u>`  = <u>밑줄</u>
- `![](assets/images/Pseudo_Lab_logo.png){: width="300" height="300"}`

### 작성자 추가 방법
- `_config.yml` 파일 `authors:` 아래에 아래 포맷에 맞춰 작성하시면 됩니다.
- `assets/images/builder-profile/`에 이미지 파일을 업로드하고, `avatar`에 해당 경로를 추가해주세요.
```
 김찬란:
    name: 김찬란
    display_name: 김찬란
    avatar: 'assets/images/builder-profile/김찬란.png'
    email: seriousran@gmail.com
    linkedIn: https://www.linkedin.com/in/chanran-kim/
    github: https://github.com/seriousran
    tag: [NCSOFT 연구원, HP 글로벌 앰버서더, 디저트 중독]
    description: "/ 1-4기 / 함께 개발자"
```
