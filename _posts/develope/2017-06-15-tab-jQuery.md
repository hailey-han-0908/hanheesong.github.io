---
layout: amp
title: "jQuery : tab"
description: "jQuery tab 탭 텝"
tag: [jquery, javascript, tab]
category: develope
sitemap:
  changefreq: daily
---


```html
<div class="cont-top">

  <div class="tab-header f-btns">
    <ul class="tab-list">
      <li class="tab-item tab1"><a href="javascript:void(0)" onclick="gotab('1')"><img src="tab1_off.png" alt="탭 선택 전"><div class="hover"><img src="tab1_on.png" alt="탭 선택 후"></div></a></li>
      <li class="tab-item tab2"><a href="javascript:void(0)" onclick="gotab('2')"><img src="tab2_off.png" alt="탭 선택 전"><div class="hover"><img src="tab1_on.png" alt="탭 선택 후"></div></a></li>
      <li class="tab-item tab3"><a href="javascript:void(0)" onclick="gotab('3')"><img src="tab3_off.png" alt="탭 선택 전"><div class="hover"><img src="tab1_on.png" alt="탭 선택 후"></div></a></li>
    </ul>
  </div>

</div>


<div class="cont-middle">

  <div id="tabs-container">

    <div id="tab-1" class="tab-cont">
      <img src="tab1.jpg" alt="첫번째 탭">
    </div>

    <div id="tab-2" class="tab-cont">
      <img src="tab2.jpg" alt="두번째 탭">
    </div>

    <div id="tab-3" class="tab-cont">
      <img src="tab3.jpg" alt="세번째 탭">
    </div>

  </div>

</div>
```
`.tab-list li`안에 `a` 태그 `onclick` 속성을 사용해 `gotab()`를 호출하고 매개변수로 idx를 넘김.


```javascript
var $tabctrls       = $('.f-btns li'),
    $tabcontainer   = $('#tabs-container'),
    $tabitems       = $('.tab-cont');

function gotab(idx) {
  idx = Number(idx); // 1
  if ( isNan(idx) || idx<=0 ) idx = 0; //2
  idx++;

  var $go          = $tabcontainer.find('[id^=tab-]' + idx + '"]');

  if (idx !== -1) {
    $tabitems.hide();
    $go.show();
  }
}
```

1 : `Number()`함수는 타입변환 함수로 스트링 -> 숫자로 바꿔줌.

2 : 매개변수로 받은 `idx`가 없거나 `idx`가 0보다 작으면 `idx`를 0으로 초기화시켜줌.
