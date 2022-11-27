---
layout: post
title: "Google_Analytics"
info: "Google_Analytics_Set"
tech: "MarkDown"
type: Kookmin
comments: true
---

## 9. 구글 애널리틱스 설정하기

- ### 초기 설정

  [Google Analytics]("https://analytics.google.com/analytics/web/?hl=ko#/p343826126/reports/intelligenthome") 계정을 먼저생성한다.
  측정 시작 버튼 &rarr; 계정 이름 생성 &rarr; 속성 설정 &rarr; 비즈니스 정보 입력

- ### 애널리틱스 데이터 스트림 설정

  웹으로 설정 https, 내 github 주소, 스트림 이름을 입력하고 스트림 만들기 선택
  측정 아이디 복사 &rarr; \_config.yml에 tracking id 추가

- ### 오류

  위와 같이 적용하였을 때, 제대로 연결이 되지 않았다.
  그 이유를 검색해 본 결과, 테마에 따라 `Google 애널리틱스`와 `유니버셜 애널리틱스`로 나뉜다는 것을 알았다.  
  가장 큰 차이점은 설치스크립트가 다른 점이다. 또한 구글 검색 시 대부분 이전 버전 기준으로 설명하고 있어서 관련 자료를 찾기 힘들다.
  또한 둘은 측정 ID 형식이 다른데,

  - `G-XXXXXXXX` 형식 &rarr; `Google Analytics 4`를 사용한다는 뜻이고,
  - `UA-XXXXXXX` 형식 &rarr; `유니버셜 애널리틱스`를 사용한다는 걸 뜻한다.

  ##### 블로그에 적용하는 방법

  나의 경우, UA 형식을 사용하기 때문에, 유니버셜 애널리틱스의 경우를 차용했다.

  ###### ga4를 디폴트로 지원하지 않는 테마에 ga4를 붙여주었다.

  `_includes` 폴더로 이동하여 `head.html`에 스크립트를 삽입해 준다.

  - 스크립트는 `관리 > 데이터 스트림 > 계정 생성할때 생성했던 스크림 > 태그 안내 보기 > 직접 설치` 에서 수동으로 아래의 코드를 붙여넣기 해주면 된다.

  ```html
  <!-- Google tag (gtag.js) -->
  <script
    async
    src="https://www.googletagmanager.com/gtag/js?id=G-LVW35GS148"
  ></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag() {
      dataLayer.push(arguments);
    }
    gtag("js", new Date());

    gtag("config", "G-LVW35GS148");
  </script>
  ```

  그 후 깃허브에 수정한 소스코드를 올리고,  
   개발자 도구를 킨 후 `gtag`를 입력해보고  
   정상적으로 설치된 것을 확인한다.
