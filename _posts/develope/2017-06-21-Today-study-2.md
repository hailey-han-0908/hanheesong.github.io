---
layout: amp
title: "PHP array"
description: "정리"
tag: [php, array]
category: develope
sitemap:
  changefreq: daily
---


## array_pop : 배열의 마지막 원소 빼기

array_pop($array)
마지막 값을 빼내고 그 값을 반환
```java
$stack = array('han', 'hee', 'song', 'php');
$hanheesong = array_pop($stack);
print_r($stack); //=>[0]->han [1]->hee [2]->song
```

## array_shift : 배열의 첫번째 원소 빼기
