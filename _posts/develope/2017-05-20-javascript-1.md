---
layout: amp
title: "자바스크립트 this (1)"
description: "자바스크립트 this 용법 알기"
tag: [javascript]
category: develope
sitemap:
  changefreq: daily
---

- this? this!
- 함수 실행:
  - 함수 실행에서의 this
  - 엄격 모드 함수 실행에서의 this
  - 내부 함수에서 this를 사용할 때 실수하는 부분
- 메소드 실행
  - 메소드 실행에서의 this
  - 객체로부터 메소드를 분리할 때
- 생성자 실행
  - 생성자 실행에서의 this
  - new를 깜빡할 때
- 간접 실행
  - 간접 실행에서의 this
- 바인딩 함수
  - 바인딩 함수에서의 this
- 화살표 함수
  - 화살표 함수에서의 this
  - 화살표 함수로 메소드를 정의할 때 실수

# 1. this? this!
`javascript`에서 4가지 함수 실행 타입이 있다.

- 함수 실행 : alert('Hello World')
- 메소드 실행 : console.log('Hello World')
- 생성자 실행 : new RegExp('\d')
- 간접 실행 : alert.call(undefined, 'Hello World')

각 타입은 서로 다른 문맥을 갖는다.
`this`키워드를 이해할 수 있는 방법은 함수 실행이 문맥에 어떤 영향을 미치는지에 대해 확실히 이해하는 것이다. 시작하기 전에 아래의 용어들과 친숙해지자.

<pre>
- 실행이란, 함수 내부에 있는 코드를 수행하는 것 = 함수호출
- 실행 시점에서의 문맥은 함수 내부에서의 값
- 함수의 스코프는 변수, 객체, 내부 함수들의 집합
</pre>


# 2. 함수 실행
함수 표현식은 { 인자1, 인자2, ... }로 수행된다.
ex. parseInt('18')
이 표현식은 myObject.myFunction과 같이 메소드를 실행하기 위해 사용하는 속성 접근자가 될 수 없다. 예를 들어 [1,5].join(',')은 함수 실행이 아니라 메소드 호출이다.

```javascript
function hello(name){
  return 'Hello' + name + '!';
}
var msg = hello('World'); //함수실행
console.log(msg); // => 'Hello World!'
```
`hello('World')`가 함수를 실행하는 부분이다. `hello`표현식 뒤에 따라오는 `World`인자와 함께 함수 객체로 계산된 것이다.

⚠️ 즉시실행함수(IIFE)
```javascript
var message = (function(name){
    return 'Hello' + name + '!';
  })('World');
  console.log(message) //=> 'Hello World'!{% endraw %}
```

즉시실행함수 역시 함수 실행의 종류 중 하나다.
```javascript
(function(name){
    return 'Hello' + name + '!';
  }) /*=> 함수 객체로 바뀔 표현식 */ ('World'); //=> 함수에 전달될 인자
```

# 2.1 함수 실행에서의 this
함수 실행에서 `this`는 **전역객체**다.
**전역객체**는 실행 환경에 따라 결정 되며 웹 브라우저에서 `window` 객체가 전역객체가 된다.
```javascript
function sum(a,b){
console.log(this === window); // => true
this.myNumber = 20; // 전역객체에 'myNumber' 속성 추가
return a + b;
}
sum(15, 16); // => 31
window.myNumber; // => 20
```

sum(15, 16) 함수가 실행됨과 동시에 자바스크립트는 자동으로 `this`를 전역객체로 갖는다. 웹 브라우저 환경에서 `this`는 `window`이다. `this`가 함수 스코프~전역실행문맥~ 바깥에서 사용 되었을 경우 전역객체를 참조하게 된다.

# 2.2 엄격모드 함수 실행에서의 this
엄격모드 함수 실행의 `this`는 **undefined**다.
엄격모드는 `코드 안정성` 그리고 `더 나은 오류검증 제공`을 위해 ECMA Script 5.1버전에서 처음 소개되었다. 엄격모드로 작성하는 방법은 **함수 내부 최상단**에 `use strick`라는 예약어를 적으면 된다.

```javascript
function multiply(a, b){
  'use strict';

  console.log(this === undefined); // => true
  return a * b;
}
multiply(2, 5); // => 10
```
엄격모드는 현재 스코프뿐만 아니라 내부에 정의된 모든 스코프에서도 적용된다.

{% highlight javascript linenos %}
{% raw %}
function execute(){
  'use strict';

  function concat(str1, str2){
    console.log(this === undefined); // => true
    return str1 + str2;
  }
  concat('Hello', 'World'); // => Hello World!
}
execute();
{% endraw %}
{% endhighlight %}
