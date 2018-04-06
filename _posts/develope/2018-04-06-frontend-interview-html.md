---
layout: post
title: "프론트 엔드 인터뷰 HTML 편"
description: "프론트 엔드 인터뷰 HTML에 대한 질문에 대한 답변. (제 생각이니 틀릴 수 있음 주의!)"
tag: [interview, html, frontend]
category: javascript
sitemap:
  changefreq: daily
---

### doctype 이란 무엇입니까?

doctype이란 Document Type Definition을 선언하기 위한 태그로
문서의 렌더링 모드를 설정하거나 유효성 검사에 사용될 기준을 정의하는 것을 말한다.

### 여러 언어로 된 콘텐츠 페이지를 어떻게 제공합니까?
### 다국어 사이트를 디자인하거나 개발할 때 주의해야 할 사항은 무엇입니까?
### data- 속성은 무엇에 좋은가요?
### HTML5를 열린 웹 플랫폼으로 생각하십시오. HTML5의 기본 요소는 무엇입니까?
### 쿠키와 세션저장소 및 로컬저장소의 차이점은 무엇입니까?
### <script>,<script async>,<script defer>의 차이점을 설명하십시오.
### 일반적으로 css <link>는 <head>와 </head> 사이에 넣는게 좋다고하고, script>역시 </body>전에 넣는게 좋다고하는데 그 이유를 설명할 수 있습니까?

웹 브라우저가 HTML 문서를 파싱할 때 `<script>` 태그를 만나면 그 안에 있는 JavaScript의 처리가 끝날 때 까지 다른 HTML의 파싱을 멈추기 때문에 사용자 입장에서 HTML 페이지가 화면에 다 그려지기까지 더 오래 걸립니다. 그래서 우선 CSS, HTML 파싱이 먼저 완료되고 나서 JavaScript가 수행하는 것이 더 빠르게 느껴지기 때문에 HTML 문서의 마지막에(=`</body>` 직전) 두는 것을 권장합니다.

### 점진정 랜더링이 무엇입니까?
### 다른 HTML 템플릿 언어를 사용해 본적 있습니까?
### srcset 이미지 태그에 속성을 사용하는 이유는 무엇입니까? 이 속성의 컨텐츠를 평가할 때 브라우저가 사용하는 프로세스를 설명하세요.
