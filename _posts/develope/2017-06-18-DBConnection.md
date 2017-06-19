---
layout: amp
title: "코드이그나이터 DB 커넥션"
description: "코드이그나이터 DB 커넥션"
tag: [코드이그나이터, 데이터베이스]
category: develope
sitemap:
  changefreq: daily
---

libraries / DBConnection.php

```java
Class DBconnection{
  protected static $_config = null;
  public function __construct($db_key){}

//DB config 정보 가져오기
  public static function get_db_config($db_key){
    global $_DB_CONFIG; //libraries/conf.d/config.db.php
    $_config    = DBconnection::$_config;
    /*
      static 키워드

      해당 클래스의 인스턴스화 필요없이 해당 프로퍼티와 메서드에 접근가능 하게 함을 의미. static 키워드로 선언된 프로퍼티는 인스턴스화된 클래스의 객체로 접근 할 수 없음. 정적 프로퍼티는 객체의 -> 연산자를 통한 접근 할 수 없음.
    */
    if($_config === null) {
      $_config  = DBConnection::$_config = $_DB_CONFIG;
    }
    $_config    = new Data($_config);
    $db_key     = strtoupper($db_key); //문자열을 대문자로 만듬
    return $_config->get($db_key);
    return null;
  }
}
```
