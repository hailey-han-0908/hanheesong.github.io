---
layout: post
title: MySQL Database 생성, 삭제, 열람, 선택
description: "MySQL"
tags: [mysql]
category: db
sitemap:
  changefreq: daily
---

## Database
데이터가 실질적으로 적재되는 테이블들을 분류하는 상위 개념

## SQL
### 생성

```sql
CREATE DATABASE `데이터베이스명` CHARACTER SET utf8 COLLATE utf8_general_ci;
```
`CHARACTER SET utf8 COLLATE utf8_general_ci`로 [인코딩](http://d2.naver.com/helloworld/19187)을 해줘야 한글이 명시됨!
### 삭제

```sql
DROP DATABASE `데이터베이스명`;
```

### 열람

```sql
SHOW DATABASE;
```

### 선택

```sql
USE `데이터베이스명`;
```
