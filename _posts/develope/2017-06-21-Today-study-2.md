---
layout: amp
title: "PHP array"
description: "정리"
tag: [php, array]
category: develope
sitemap:
  changefreq: daily
---
# array 목차
* array_pop
* array_push
* array_shift
* array_unshift

## array_pop : 배열의 마지막 원소 빼기
array_pop($array)

```java
$stack = array('han', 'hee', 'song', 'php');
$hanheesong = array_pop($stack);
print_r($stack); //=>[0] => han [1] => hee [2] => song
```

## array_push : 배열의 마지막에 하나 이상의 원소를 첨가
array_push($array1, $var1, ....)

```java
$stack1 = array('han', 'hee', 'song', 'php');
array_push($stack1, "php");
print_r($stack1); //=>[0] => han [1] => hee [2] => song [3] => php [4] => php
```

## array_shift : 배열의 첫번째 원소 빼기
array_shift($array)

```java
$stack2 = array('php', 'han', 'hee', 'song');
$hanheesong2 = array_shift($stack2);
print_r($stack2); //=>[0] => han [1] => hee [2] => song
```

## array_unshift : 배열의 맨 앞에 하나 이상의 원소를 첨가
array_unshift($array, $var1, ...)

```java
$stack3 = array('han', 'hee', 'song');
array_unshift($stack3, 'php');
print_r($stack3); //=>[0] => php [1] => han [2] => hee [3] => song
```
