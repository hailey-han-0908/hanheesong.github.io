---
layout: post
title: Sitemap.xml - changefreq 및 우선순위 xml이 중요한 이유
description: Sitemap.XML – Why Changefreq & Priority XML Are Important
tag: [develope, sitemap]
category: develope
sitemap:
  changefreq: daily
---

웹 사이트에 XML Sitemap이 있다면 `changefreq`와 `priority`는 검색 엔진에 데이터를 제공하기 위한 두 가지 중요한 사이트 맵 태그입니다. 검색 엔진 `스파이더`(`로봇`또는 `크롤러`)가 사이트의 개별 페이지를 방문하는 시기와 빈도에 영향을 미치므로 여러가지 의미가 있습니다.

# Changefreq
Google에 따르면 `changefreq xml`태그는 다음과 같은 7가지 빈도수 중 하나로 설정 될 수 있습니다.

- **never**
- **yearly**
- **monthly**
- **weekly**
- **daily**
- **hourly**
- **always**

이것은 검색 엔진에 각 페이지가 얼마나 자주 업데이트 되는지 알려줍니다.
업데이트는 Flash 콘텐츠나 수정 된 이미지가 아닌 페이지의 HTML 코드 또는 텍스트에 대한 실제 변경 사항을 말합니다.

## Changefreq 가이드 라인
- **never**: 오래된 뉴스 기사, 보도 자료
- **yearly**: 연락처, 회사 소개, 로그인, 등록페이지
- **monthly**: 자주 묻는 질문, 지침, 때때로 업데이트되는 기사
- **weekly**: 제품 정보 페이지, 웹 사이트 디렉토리
- **daily**: 블로그 포스트, 벼룩 시장, 소규모 게시판
- **hourly**: 주요 뉴스 사이트, 날씨 정보, 포럼
- **always**: 주식 시장 자료, 사회 북마킹 카테고리

# Priority XML
`priority xml`사이트 맵 태그는 유용하지만 중요하지는 않습니다.
0부터 1까지의 숫자로 설정되어 있고, 숫자가 지정되지 않으면 페이지 우선 순위는 0.5입니다. 우선 순위가 높은 페이지는 검색 결과에서 동일한 사이트의 다른 페이지보다 자주 색인을 생성하거나 위에 표시 될 수 있습니다.

- 0.8-1.0: 홈페이지, 하위 도메인, 제품 정보, 주요 기능
- 0.4-0.7: 기사 및 블로그 포스트, 카테고리 페이지, FAQ
- 0.0-0.3: 오래된 뉴스, 관련성이 없는 정보
