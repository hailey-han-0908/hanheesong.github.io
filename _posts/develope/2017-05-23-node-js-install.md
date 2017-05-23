---
layout: amp
title: "자주 쓰는 맥 터미널 명령어"
description: "자주 쓰는 맥 터미널 명령어"
tag: [ 터미널명령어 ]
category: develope
sitemap:
  changefreq: daily
---
낮밤이바뀐내일상.......덕분에 중요한 연락도 못받고...참 잘한다.....🤷🏻‍

## 파일찾기(파일명검색)

- `현재 디렉토리`에서 pl 확장자를 가진 모든 파일 찾기
(현재 디렉토리 밑의 하위 디렉토리까지 다 찾음.)
```bash
file -name '*.pl'
```

- `전체하드(루트)` pl 확장자를 가진 모든 파일 찾기
```bash
find / -name '*.pl'
```

- `파일 크기`로 검색
```bash
find . -name 'my*.*' -print -size -2000c
```
🔍2000c에서 -2000은 2000보다 적은 수
🔍`c`는 바이트 단위로 계산하라는 의미임. 킬로바이트 단위는 `k`, `-2000c = -2k`

- 찾아낸 파일 자동 삭제
```bash
ls temp
find . -type f -name '*.txt' -empty -exec rm -f {} \;
```
🔍`-exec`와 `\;` 사이에 기술되는 부분(=rm -f {})이 검색된 파일에 적용될 명령



## 디렉토리명 찾기
- 전체하드(루트)에서 디렉토리 이름이 brew로 시작하는 모든 디렉토리 찾기
```bash
find / -name '*brew*' -type d
```


## 권한설정
```bash
chmod 755 /usr/?/?
