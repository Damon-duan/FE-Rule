# 前端编码规范

版本  |  说明  |  时间  |  参与编辑人员
------|--------|--------|--------
v1.0  |初版    |2020-7-7 |

* [浏览器是如何工作的](https://juejin.im/post/5e47cb68f265da57584d9a54?utm_source=gold_browser_extension)
* [HTML 编码规范](./html-rule.md)
* [Javascript 编码规范](./javascript-rule.md)
* [CSS 编码规范](./css-rule.md)
* [Vue 项目开发规范](./vue-rule.md)
* [Javascript 开发技巧](./js-skill.md)
* [编辑器配置教程](./editor-config.md)


Frontend前端目录结构如下:
```
./ 前端项目根目录
│  .babelrc                    babel编译参数
│  .editorconfig               定义代码格式
│  .eslintignore               eslint语法检查ignore配置文件
│  .eslintrc.js                eslint语法校验配置文件
│  .postcssrc.js               转换css的工具
│  index.html                  主页
│  package.json                项目基本信息（项目开发所需模块、项目名称、版本）
│  pom.xml                     maven托管前端配置文件
│  README.md                   项目说明文档
│
├─build
│      build.js                生产环境构建代码
│      check-versions.js       检查node、npm等版本
│      dev-client.js           热重载相关配置
│      dev-server.js           构建本地服务器
│      utils.js                构建工具相关
│      vue-loader.conf.js      css加载器配置
│      webpack.base.conf.js    webpack基础配置
│      webpack.dev.conf.js     webpack开发环境配置
│      webpack.prod.conf.js    webpack生产环境配置
│
├─config
│      dev.env.js              开发环境变量
│      index.js                项目一些配置变量
│      prod.env.js             生产环境变量
│
├─src
│  │  App.vue                  项目的根组件
│  │  main.js                  组件的入口文件
│  │
│  ├─assets                    静态资源
│  │  ├─font                   字体图标存放位置
│  │  │      iconfont.css      字体图标样式
│  │  │      iconfont.eot      字体图标文件
│  │  │      iconfont.svg      字体图标文件
│  │  │      iconfont.ttf      字体图标文件
│  │  │      iconfont.woff     字体图标文件
│  │  │
│  │  ├─images                 系统图标或图片存放位置
│  │  │      loading.gif       loading图片
│  │  │      no-data.png       空数据暂未图
│  │  │
│  │  └─scss                   sass样式文件存放位置
│  │          extends.scss     继承类
│  │          global.scss      全局样式
│  │          mixins.scss      宏
│  │          normalize.scss   初始化样式文件
│  │          variable.scss    全局变量文件
│  │
│  ├─common
│  │      ajax.js              axios类封装
│  │      eventBus.js          事件通信封装
│  │      index.js
│  │      loadJs.js            第三方库加载
│  │      RSA.json             加密公钥
│  │      storage.js           本地存储|回话临时存储封装
│  │      utils.js             工具类
│  │
│  ├─components                公用组件存放位置
│  │  ├─dialog                 弹窗组件
│  │  │      index.js
│  │  │      index.vue
│  │  │
│  │  ├─loading                loading加载组件
│  │  │      index.js
│  │  │      index.vue
│  │  │
│  │  └─toast                  轻提示组件
│  │          index.js
│  │          index.vue
│  │
│  ├─router                     路由配置
│  │      index.js
│  │
│  └─views                      项目页面编写
│         index.vue
│  
│
└─static                        静态资源存放位置
```
