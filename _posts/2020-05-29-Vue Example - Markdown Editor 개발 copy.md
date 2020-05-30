---
layout: post
title: Vue Example - Markdown Editor 개발
tags: [vue tree, vue example markdown editor, vue.js, vue, vuejs]
img: tree1.png
author: realdev9
---

# Vue Example - Markdown Editor 개발

vue.js Example 원본 ->
<https://github.com/vuejs/vue/tree/dev/examples/markdown>

[ 설치 ]

```html
<!-- 개발버전, 도움되는 콘솔 경고를 포함. -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

또는:

<!-- 상용버전, 속도와 용량이 최적화됨. -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

JSFiddle - <https://jsfiddle.net/>

JSFiddle 에 바로 적용해 분석해 보기

[html]

```html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
<!-- the demo root element -->
<div id="editor">
  <textarea :value="input" @input="update"></textarea>
  <div v-html="compiledMarkdown"></div>
</div>
```

[css]

```css
html,
body,
#editor {
  margin: 0;
  height: 100%;
  font-family: 'Helvetica Neue', Arial, sans-serif;
  color: #333;
}

textarea,
#editor div {
  display: inline-block;
  width: 49%;
  height: 100%;
  vertical-align: top;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  padding: 0 20px;
}

textarea {
  border: none;
  border-right: 1px solid #ccc;
  resize: none;
  outline: none;
  background-color: #f6f6f6;
  font-size: 14px;
  font-family: 'Monaco', courier, monospace;
  padding: 20px;
}

code {
  color: #f66;
}
```

[javascript]

```javascript
new Vue({
  el: '#editor',
  data: {
    input: '# hello',
  },
  computed: {
    compiledMarkdown: function () {
      return marked(this.input, { sanitize: true });
    },
  },
  methods: {
    update: _.debounce(function (e) {
      this.input = e.target.value;
    }, 300),
  },
});
```

[Warning]

"marked(): sanitize and sanitizer parameters are deprecated since version 0.7.0, should not be used and will be removed in the future. Read more here: <https://marked.js.org/#/USING_ADVANCED.md#options">

sanitize: true 는 0.7.0 버전이후에 deprecated 되었습니다. ', { sanitize: true }' 를 제거합니다.

marked.js 의 원 정보는 아래와 같습니다.

Hompage - <https://marked.js.org>

Github - <https://github.com/markedjs/marked>

NPM - <https://www.npmjs.com/package/marked>

[ 설치 ]

```html
<script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
```

실제 JSFiddle 에 적용된 소스
<https://jsfiddle.net/realdev/n8ohw2db/9/>

참고 - 아래 링크를 통해 codesandbox 에서도 해당 소스를 확인할 수 있습니다.

이 소스를 vue sfc 환경의 import 형태로 변경해보면, 좀 더 vue 를 활용하는데 도움이 될 수 있습니다.

<https://codesandbox.io/s/wispy-browser-lsnmw?file=/index.html>
