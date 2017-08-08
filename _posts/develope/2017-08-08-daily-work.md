---
layout: amp
title: "Business log 1"
description: "Business log 1"
tag: [Business log]
category: develope
sitemap:
  changefreq: daily
---

 `$('.secondary-header').insertBefore('#Container')`
 `$( ".primary-sub-navigation-ul .bar" ).last().css( "width",0 );`

객체는 참조타입 ( 원시타입과 구별하기 위함 )

이는 객체는 새로운 복사본을 생성하지 않는다.
새로운 복사본을 만들고 싶다면
객체의 프로퍼티, 배열의 원소를 복사해야한다.

1. 복사하고자 하는 배열
2. 복사해 넣을 배열

```javascript
var a = ['a', 'b', 'c'] ;// 복사하고자 하는 배열
var b = []; // 복사해 넣을 배열
for (var i = 0; i < a.length; i++) {
  b[i] = a[i];
}
```
