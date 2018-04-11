---
layout: post
title: "함수의 메소드와 arguments 배우기"
description: "함수의 메소드와 arguments 배우기"
tag: [javascript]
category: javascript
sitemap:
  changefreq: daily
---

# 함수 호출 방법
1. 함수()
2. call
3. apply

```javascript
var example = function(a,b,c){
  return a + b + c;
}
example(1,2,3);
example.call(null, 1,2,3);
example.apply(null, [1,2,3]);
```

call => 그냥 인자
apply => 인자를 하나로 묶어 배열로

근데 null은 뭐지?!
null 인자의 역할은 바로 __this 바꾸기__

기본적으로 this는 window를 가르키죠.
(엄격모드에선 undefined)
하지만 몇가지 방법으로 this를 바꿀 수 있답니다.


바로, call, apply, bind에서 __첫 번째 인자값__ 에 다른 값으로 넣어주는 것.

그러면 다른 객체의 함수를 자기것인 것 처럼 쓸 수 있어요.

# call, apply의 역할
## 1) this가 가리키는 객체 바꾸기

```javascript
var obj = {
  string: 'zero',
  yell: function(){
    console.log(this.string);
  }
};
var obj2 = {
  string: 'what?'
};
obj.yell(); //=> 'zero'
obj.yell.call(obj2); //=> 'what?'
```

## 2) 함수의 arguments 조작하기

arguments는 함수가 갖고 있는 숨겨진 속성입니다.
함수에 들어온 인자를 배열 형식으로 반환하는데
주의해야 할 점은 배열이 아니라 유사배열이라는 것
이런식으로 못써요
```javascript
fucntion example() {
  console.log(arguments.join());
}
example(1,'string',true); // error!!!!
```

해결 방법은?????
배열의 프로토타입에 있는 join함수를 빌려 쓰는 것!

```javascript
function example2(){
  console.log(Array.prototype.join.call(arguments));
}
example2(1, 'string', true); // '1,string,true'
```

#bind 함수의 역할
