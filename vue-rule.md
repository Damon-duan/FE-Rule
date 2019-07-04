[1 文件命名规范](#1-文件命名规范)

[2 组件数据](#2-组件数据)

[3 单文件组件文件名称](#3-单文件组件文件名称)

[4 紧密耦合的组件名](#4-紧密耦合的组件名)

[5 自闭合组件](#5-自闭合组件)

[6 Prop名大小写](#6-Prop名大小写)

[7 Props换行](#7-Props换行)

[8 Props顺序](#8-Props顺序)

[9 指令缩写](#8-指令缩写)

[10 组件选项的顺序](#10-组件选项的顺序)

[11 组件选项中的空行](#11-组件选项中的空行)

[12 单文件组件顶级标签的顺序](#12-单文件组件顶级标签的顺序)

[13 为v-for设置键值](#13-为v-for设置键值)


# 1 文件命名规范

**1、所有文件和文件夹，统一使用：小写字母开头，英文中划线分隔的方式命名。必须遵守**！

**2、组件名应该以高级别的 (通常是一般化描述的) 单词开头，以描述性的修饰词结尾**。[参考这里](https://cn.vuejs.org/v2/style-guide/#%E7%BB%84%E4%BB%B6%E5%90%8D%E4%B8%AD%E7%9A%84%E5%8D%95%E8%AF%8D%E9%A1%BA%E5%BA%8F-%E5%BC%BA%E7%83%88%E6%8E%A8%E8%8D%90)

> 目录设计是按照功能划分成一个文件夹，以便于满足日后功能扩展的需要。同时也保证目录的简洁，可读性。



# 2 组件数据

__不推荐：__

```javascript
export default {
  data: {
    foo: 'bar'
  }
}
```

__推荐：__

```javascript
export default {
  data () {
    return {
      foo: 'bar'
    }
  }
}
```



# 3 单文件组件文件名称

单文件组件的文件名应该要么始终是单词大写开头 (PascalCase)，要么始终是横线连接 (kebab-case)。

__不推荐：__

```
mycomponent.vue
myComponent.vue
```

__推荐：__

```
my-component.vue
MyComponent.vue
```


# 4 紧密耦合的组件名


和父组件紧密耦合的子组件应该以父组件名作为前缀命名。

__不推荐：__

```
components/
|- TodoList.vue
|- TodoItem.vue
└─ TodoButton.vue

```

__推荐：__

```
components/
|- TodoList.vue
|- TodoListItem.vue
└─ TodoListItemButton.vue
```


# 5 自闭合组件


在单文件组件中没有内容的组件应该是自闭合的。

__不推荐：__

```html
<my-component></my-component>
```

__推荐：__

```html
<my-component />
```


# 6 Prop 名大小写

在声明 prop 的时候，其命名应该始终使用 camelCase，而在模板中应该始终使用 kebab-case。

__不推荐：__

```js
export default {
  props: {
    'greeting-text': String
  }
};
```

__推荐：__

```js
export default {
  props: {
    greetingText: String
  }
}
```

__不推荐：__

```html
<welcome-message greetingText="hi" />
```
__推荐：__

```html
<welcome-message greeting-text="hi" />
```

# 7 Props 换行

多个 Props 的元素应该分多行撰写，每个 Props 一行，闭合标签单起一行。

__不推荐：__

```html
<my-component foo="a" bar="b" baz="c" />
```

__推荐：__

```html
<my-component
  foo="a"
  bar="b"
  baz="c"
/>
```

# 8 Props 顺序

标签的 Props 应该有统一的顺序，依次为指令、属性和事件。

__推荐：__

```html
<my-component
  v-if="if"
  v-show="show"
  v-model="value"
  ref="ref"
  :key="key"
  :text="text"
  @input="onInput"
  @change="onChange"
/>
```



# 9 指令缩写

指令缩写，用 `:` 表示 `v-bind:` ，用 `@` 表示 `v-on:`

__不推荐：__

```html
<input
  v-bind:value="value"
  v-on:input="onInput"
>
```

__推荐：__

```html
<!-- bad -->
<input
  :value="value"
  @input="onInput"
>
```


# 10 组件选项的顺序

组件选项应该有统一的顺序。

__推荐：__

```js
export default {
  name: '',

  mixins: [],

  components: {},

  props: {},

  data() {},

  computed: {},

  watch: {},

  created() {},

  mounted() {},

  destroyed() {},

  methods: {}
};
```


# 11 组件选项中的空行

组件选项较多时，建议在属性之间添加空行。

__推荐：__

```js
export default {
  computed: {
    formattedValue() {
      // ...
    },

    styles() {
      // ...
    }
  },

  methods: {
    onInput() {
      // ...
    },

    onChange() {
      // ...
    }
  }
};
```


# 12 单文件组件顶级标签的顺序

单文件组件应该总是让顶级标签的顺序保持一致，且标签之间留有空行。

__推荐：__

```html
<template>
...
</template>

<script>
/* ... */
</script>

<style>
/* ... */
</style>
```

# 13 为v-for设置键值

v-for 中总是有设置 key 值。在组件上总是必须用 key 配合 v-for，以便维护内部组件及其子树的状态

__不推荐：__

```html
<ul>
  <li v-for="todo in todos">
​    {{ todo.text }}
  </li>
</ul>
```

__推荐：__

```html
<ul>
  <li
​    v-for="todo in todos"
​    :key="todo.id">
​    {{ todo.text }}
  </li>
</ul>
```
