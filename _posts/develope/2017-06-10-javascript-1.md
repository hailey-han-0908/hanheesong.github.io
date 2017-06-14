---
layout: amp
title: "jQuery : selectable()"
description: "jqeury selectable() 함수 정리"
tag: [jquery, javascript]
category: develope
sitemap:
  changefreq: daily
---

```javascript
var fadetime = 500, delaytime = 200;
function selectable(){
  $('.f-btns li').on('mouseover', function(){
    var $me = $(this); //$(this) = $('.f-btns li')
    $me.find('.hover').stop(true, true).show('fade', fadetime);
  }).on('mouseout', function(){
    var $me = $(this);
    if ($me.hasClass('choosed')) return; //만약에 $('.f-btns li')가 choosed 되어 있으면 아래 코드 실행안하고 스코프 종료.
    $me.find('.hover').stop(true, true).hide('fade', fadetime);
  }).on('click', function(){
    var $me = $(this);
    $('.f-btns li .hover').not($me.find('.hover')).stop(true, true).hide('fade', fadetime, function(){
      $(this).closest('li').removeClass('choosed');//나빼고 선택된 애들 다 초기화
    });

  });
}
```
