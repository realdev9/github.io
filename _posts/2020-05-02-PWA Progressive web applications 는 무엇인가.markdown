---
layout: post
title: PWA (Progressive web applications) 는 무엇인가
tags: vue.js, vue, vuejs
---

# PWA (Progressive Web Application)

이번 시간에는 앞에서 나온 웹개발의 중요한 개념인 PWA 와 SPA 에 대해서 자세히 알아보도록 하겠습니다.

## PWA (Progressive web applications) 는 무엇인가

- 앞에서 살펴본 Vue 는 진보적 프레임워크 progressive framework 라고 했는데요.

바로 이 PWA (Progressive web applications) 를 만들 수 있는 프레임워크 라는 거죠.

- PWA는 웹 소프트웨어의 일종으로, HTML, CSS, 자바스크립트를 포함한 웹 기술들을 사용하여 만듭니다.

- 웹 표준을 준수하는 브라우저를 사용하는 어떠한 플랫폼에서라도 동작하도록 고안되었습니다.

- Vue 호환성 정보 - <https://kr.vuejs.org/v2/guide/installation.html>
  Vue는 ECMAScript 5 기능을 사용하기 때문에 IE8 이하 버전을 지원하지 않습니다. 하지만 모든 ECMAScript 5 호환 브라우저를 지원합니다.

- 오프라인 작업, 푸시 알림, 장치 하드웨어 접근, 데스크톱과 모바일 장치의 네이티브 애플리케이션과 유사한 사용자 경험의 창출을 가능케 하는 것이 포함됩니다. → Native 앱의 기능을 지원

- 웹 애플리케이션이기 때문에 개발자나 사용자가 앱 스토어를 통해 설치할 필요가 없음. → 웹 앱

---

※ 출처

- 위키백과 - <https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%A0%88%EC%8B%9C%EB%B8%8C_%EC%9B%B9_%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98>

※ 참고

- MDN - <https://developer.mozilla.org/ko/docs/Web/Progressive_web_apps/%EC%86%8C%EA%B0%9C>

※ Examples

- 구글 유튜브 - <https://vuetifyjs.com/ko/examples/layouts/google-youtube>
- 구글 Keep - <https://vuetifyjs.com/ko/examples/layouts/google-keep>
- 구글 Contacts - <https://vuetifyjs.com/ko/examples/layouts/google-contacts>

---

## SPA (Single-Page Application)

## SPA (Single-Page Application)는 무엇인가

- 서버로부터 완전한 새로운 페이지를 불러오지 않고 현재의 페이지를 동적으로 다시 작성함으로써 사용자와 소통하는 웹 애플리케이션을 말한다.

- 페이지들 간의 간섭을 막아주고 애플리케이션이 데스크톱 애플리케이션(오프라인 작업)처럼 동작하도록 만들어준다.

- SPA에서 적절한 자원들을 동적으로 불러들여서 필요하면 문서에 추가하는데, 보통 사용자의 동작에 응답하게 되는 방식이다.

- 위치 해시나 HTML5 히스토리 를 사용하여 애플리케이션 안에서 개개의 논리 문서의 인식 및 탐색을 제공할 수 있다(히스토리 모드 - <https://router.vuejs.org/kr/guide/essentials/history-mode.html>). 싱글 페이지 애플리케이션과은 웹 서버와의 동적인 통신(푸시 알림 등)을 수반하기도 한다.

- <https://router.vuejs.org/kr/>

- Vue 라우터는 Vue.js의 공식 라우터입니다. Vue.js를 사용한 싱글 페이지 앱을 쉽게 만들 수 있도록 Vue.js의 코어와 긴밀히 통합되어 있습니다.

※ 참고 - <https://ko.wikipedia.org/wiki/%EC%8B%B1%EA%B8%80_%ED%8E%98%EC%9D%B4%EC%A7%80_%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98>
