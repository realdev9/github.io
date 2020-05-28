---
layout: post
title: [Vue Example] Tree 개발
tags: [vue.js, vue, vuejs]
img: logo.png
author: realdev9
---

# [Vue Example] Tree 개발

vue.js Example 원본 ->
<https://github.com/vuejs/vue/tree/dev/examples/tree>

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
<!-- item template -->
<script type="text/x-template" id="item-template">
  <li>
    <div
      :class="{bold: isFolder}"
      @click="toggle"
      @dblclick="changeType">
      {{model.name}}
      <span v-if="isFolder">[{{open ? '-' : '+'}}]</span>
    </div>
    <ul v-show="open" v-if="isFolder">
      <item
        class="item"
        v-for="model in model.children"
        :model="model" >
      </item>
      <li class="add" @click="addChild">+</li>
    </ul>
  </li>
</script>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<!-- the demo root element -->
<ul id="demo">
  <item class="item" :model="treeData"> </item>
</ul>
```

[css]

```css
body {
  font-family: Menlo, Consolas, monospace;
  color: #444;
}
.item {
  cursor: pointer;
}
.bold {
  font-weight: bold;
}
ul {
  padding-left: 1em;
  line-height: 1.5em;
  list-style-type: dot;
}
```

[javascript]

```javascript
var data = {
  name: 'My Tree',
  children: [
    { name: 'hello' },
    { name: 'wat' },
    {
      name: 'child folder',
      children: [
        {
          name: 'child folder',
          children: [{ name: 'hello' }, { name: 'wat' }],
        },
        { name: 'hello' },
        { name: 'wat' },
        {
          name: 'child folder',
          children: [{ name: 'hello' }, { name: 'wat' }],
        },
      ],
    },
  ],
};

// define the item component
Vue.component('item', {
  template: '#item-template',
  props: {
    model: Object,
  },
  data: function () {
    return {
      open: false,
    };
  },
  computed: {
    isFolder: function () {
      return this.model.children && this.model.children.length;
    },
  },
  methods: {
    toggle: function () {
      if (this.isFolder) {
        this.open = !this.open;
      }
    },
    changeType: function () {
      if (!this.isFolder) {
        Vue.set(this.model, 'children', []);
        this.addChild();
        this.open = true;
      }
    },
    addChild: function () {
      this.model.children.push({
        name: 'new stuff',
      });
    },
  },
});

// boot up the demo
var demo = new Vue({
  el: '#demo',
  data: {
    treeData: data,
  },
});
```

실행해보면 정상적으로 Tree 가 잘 동작하지만, console 에 key 가 필요하다는 경고 메세지가 확인됩니다.
vue.js 2.x 부터는 Component 에 v-for 를 사용할때는 key 속성을 이용하는 것이 필수가 되었습니다.
([Vue.js 강의]v-for 와 Component 부분 참고)

data object 의 모든 node 에 id 를 추가하고, item Component 에 v-for 다음에 :key 에 node.id 를 추가한다.

실제 JSFiddle 에 적용된 소스
<https://jsfiddle.net/realdev/zo894ked/6>
