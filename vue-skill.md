#1 @hook那些事儿

```vue
<script >
  export default {
    mounted () {
      const timer = setInterval(() => {}, 1000);
      this.$once('hook:beforeDestroy', () => clearInterval(timer));
    }
  }
</script>
```

#2 .sync语法糖

> sync 就是为了实现prop进行“双向绑定”仅此而已（父对子，子对父，来回传）

```vue
<template>
  <!--父组件-->
  <div>
    <child :num.sync="num"/>

    <!--等同于-->
    <child :num="num" @update:num="e => num = e"/>
  </div>
</template>

<script>
  import Child from './Child'

  export default {
    components: {
      Child
    },

    data () {
      return {
        num: 1
      }
    }
  }
</script>
```


```vue
<template>
  <!--子组件-->
  <div>
    <div>{{num}}</div>
    <button class="submit-btn" @click="onAdd">添加</button>
  </div>
</template>

<script>
  export default {
    name: 'Child',

    props: ['num'],

    methods: {
      onAdd() {
        this.$emit('update:num', 10)
      }
    }
  }
</script>
```

#3 路由按需加载

> 随着项目功能模块的增加，引入的文件数量剧增。如果不做任何处理，那么首屏加载会相当缓慢，这个时候，路由按需加载就闪亮登场了。

```js
const routes = [
  // webpack < 2.4
  {
    path: '/',
    name: 'home',
    components: resolve => require(['@/views/home'], resolve)
  },
  // webpack > 2.4
  {
    path: '/',
    name: 'home',
    components: () => import('@/views/home')
  }
]
```

#4 卸载watch观察

> 通常定义数据观察，会使用选项的方式 `watch` 中配置：

```js
    export default {
        data() {
            return {
                count: 1      
            }
        },
        watch: {
            count(newVal) {
                console.log('count 新值：' + newVal)
            }
        }
    }
```

> 除此之外，数据观察还有另一种函数式定义的方式：

```js
    export default {
        data() {
            return {
                count: 1      
            }
        },
        created() {
            this.$watch('count', function (newVal) {
                console.log('count 新值：' + newVal)
            })
        }
    }
```

> 它和前者的作用一样，但这种方式使定义数据观察更灵活，而且 `$watch` 会返回一个取消观察函数，用来停止触发回调：

```js
let unwatchFn = this.$watch('count', function(){
    console.log('count 新值：'+newVal)
})
this.count = 2 // log: count 新值：2
unwatchFn()
this.count = 3 // 什么都没有发生...
```

> `$watch` 第三个参数接收一个配置选项

```js
this.$watch('count', function(newVal){
    console.log('count 新值：'+ newVal)
}, {
    immediate: true // 立即执行watch
})
```

#5 巧用template

> 相信 v-if 在开发中是用得最多的指令，那么你一定遇到过这样的场景，多个元素需要切换，而且切换条件都一样，一般都会使用一个元素包裹起来，在这个元素上做切换。

```html
<div v-if="status === 'ok'">
    <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
</div>
```

> 如果像上面的div只是为了切换条件而存在，还导致元素层级嵌套多一层，那么它没有存在的意义。我们都知道在声明页面模板时，所有元素需要放在 `<template>` 元素内，除此之外，它还能在模板内使用， `<template>` 元素作为不可见的包裹元素，只是在运行时做处理，最终的渲染结果并不包含它。

```html
<template>
    <div>
        <template v-if="status==='ok'">
          <h1>Title</h1>
          <p>Paragraph 1</p>
          <p>Paragraph 2</p>
        </template>
    </div>
</template>
```

> 同样的，我们也可以在 `<template>` 上使用 `v-for` 指令，这种当时还能解决 `v-for` 和 `v-if` 同时使用报出的警告问题。   

```html
<template v-for="item in 10">
    <div v-if="item % 2 == 0" :key="item">{{item}}</div>
</template>
```
