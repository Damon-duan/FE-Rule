[1 前言](#1-前言)

[2 代码风格](#2-代码风格)

　　[2.1 文件/资源命名](#21-文件/资源命名)

　　[2.2 结构](#22-文件/资源命名)

　　　　[2.2.1 缩进](#221-缩进)

　　　　[2.2.2 空格](#222-空格)

　　　　[2.2.3 换行](#223-换行)

　　　　[2.2.4 语句](#224-语句)

　　[2.3 命名](#23-命名)

　　　　[2.3.1 JS采用CamelCase小驼峰式命名](#231-JS采用CamelCase小驼峰式命名)

　　　　[2.3.2 避免名称冗余](#231-避免名称冗余)

　　[2.4 注释](#24-注释)

　　　　[2.4.1 单行注释](#241-单行注释)

　　　　[2.4.2 多行注释](#242-多行注释)

　　　　[2.4.3 文件注释](#243-文件注释)

　　　　[2.4.4 函数/方法注释](#244-函数/方法注释)

　　　　[2.4.5 常量注释](#245-常量注释)

　　　　[2.4.6 常量注释](#246-细节注释)

[3 语言特性](#3-语言特性)

　　　　[3.1 变量](#31-变量)

　　　　[3.2 条件](#32-条件)

　　　　[3.3 循环](#33-循环)

　　　　[3.４ 类型](#34-类型)

　　　　　　[3.4.1 类型检测](#341-类型检测)

　　　　　　[3.4.2 类型转换](#342-类型转换)

　　　　[3.5 字符串](#35-字符串)

　　　　[3.6 对象](#36-对象)

　　　　　　[3.6.1 创建对象](#361-创建对象)

　　　　　　[3.6.2 对象字面量](#362-对象字面量)

　　　　　　[3.6.3 对象设置默认属性的推荐写法](#363-对象设置默认属性的推荐写法)

　　　　　　[3.6.4 将对象的属性值保存为局部变量](#364-将对象的属性值保存为局部变量)

　　　　　　[3.6.5 原生对象和宿主对象的原型](#365-原生对象和宿主对象的原型)

　　　　[3.7 数组](#37-数组)

[4 其他](#4-其他)


# 1 前言

javascript在大旗被广泛的应用，本文档的目标是使javascript代码风格保持一致，容易被理解和被维护。

# 2 代码风格

## 2.1 文件/资源命名

* 所有的文件名应该都遵循同一命名约定。以可读性而言，减号（-）是用来分隔文件名的不二之选
* 请确定文件命名总是以字母开头而不是数字开头
* 资源的字母名称必须全为小写

__不推荐：__
```
userLogin.js
userLogin.scss
userLogin.html
100-login.js
user-login-min.scss
```
__推荐：__

```
user-login.js
user-login.scss
user-login.html
user-login.min.css
user-login.min.js
```
## 2.2 结构

### 2.2.1 缩进

__【强制】使用 4个空格做为一个缩进层级，不允许使用2个空格。__

__【强制】swith下的case和default必须增加一个缩进层级。__

__不推荐：__

```javascript
switch (value) {
case 0:
    //doing
    break;
case 1:
    //doing
    break;
default:
    //doing
    break;
}
```

__推荐：__

```javascript
switch (value) {
    case 0:
        //doing
        break;
    case 1:
        //doing
        break;
    default:
        //doing
        break;
}
```

### 2.2.2 空格

__【强制】二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格__

__不推荐：__

```javascript
var a =!arr.length;
a ++;
a =b+c;
```

__推荐：__

```javascript
var a = !arr.length;
a++;
a = b + c;
```

__【强制】用作代码块起始的左花括号 { 前必须有一个空格__

__不推荐：__

```javascript
if (value){
    //doing
}

while (value){
    //doing
}

function fnName(){
    //doing
}
```

__推荐：__

```javascript
if (value) {
    //doing
}

while (value) {
    //doing
}

function fnName() {
    //doing
}
```
__【强制】在对象创建时，属性中的 : 之后必须有空格，: 之前不允许有空格__

__不推荐：__

```javascript
var obj = {
    a : 1,
    b:2,
    c :3
};
```

__推荐：__

```javascript
var obj = {
    a: 1,
    b: 2,
    c: 3
};
```

__【强制】函数声明、具名函数表达式、函数调用中，函数名和 ( 之间不允许有空格__

__不推荐：__

```javascript
function fnName () {}

var fnName = function fnName () {};

fnName ();
```

__推荐：__

```javascript
function fnName() {}

var fnName = function fnName() {};

fnName();
```
__【强制】行尾不得有多余的空格__


### 2.2.3 换行

__【强制】每个独立语句结束后必须换行__

__【强制】每行不得超过 120 个字符__

说明：超长的不可分割的代码允许例外，比如复杂的正则表达式。长字符串不在例外之列。

__【强制】运算符处换行时，运算符必须在新行的行首__

__不推荐：__

```javascript
if (validate.username &&
    validate.password &&
    validate.email &&
    validate.code) {
    //doing
}
```

__推荐：__

```javascript
if (validate.username
    && validate.password
    && validate.email
    && validate.code) {
    //doing
}
```

__【强制】在函数声明、函数表达式、函数调用、对象创建、数组创建、for 语句等场景中，不允许在 , 或 ; 前换行__


__不推荐：__

```javascript
var obj = {
    a: 1
    , b: 2
    , c: 6
}

fnName(
    username
    , password
    , email
    , code
)
```

__推荐：__

```javascript
var obj = {
    a: 1,
    b: 2,
    c: 6
}

fnName(
    username,
    password,
    email,
    code
)
```

### 2.2.4 语句

__【强制】不得省略语句结束的分号__

__【强制】在 if / else / for / do / while 语句中，即使只有一行，也不得省略块 {...}__

__不推荐：__

```javascript
if (a) fnName();

if (a)
    fnName();
```

__推荐：__

```javascript
if (a) {
    fnName();
}
```

__【强制】函数定义结束不允许添加分号,如果是函数表达式，分号是不允许省略的__


__不推荐：__

```javascript
function fnName() {

};
//函数表达式
var fnName = function(){

}
```

__推荐：__

```javascript
function fnName() {

}
//函数表达式
var fnName = function(){

};
```

## 2.3 命名

### 2.3.1 JS采用Camel Case小驼峰式命名

__【强制】变量 使用 Camel Case命名法__

__不推荐：__

```javascript
var user_name = ''
```

__推荐：__

```javascript
var userName = ''
```
__【强制】常量 使用 全部字母大写，单词间下划线分隔 的命名方式__

__不推荐：__

```javascript
var config = {
    'server': 'http://192.168.7.115'
}
```

__推荐：__

```javascript
var CONFIG = {
    server: 'http://192.168.7.115'
}
```

__【强制】函数 使用 Camel命名法__

__不推荐：__

```javascript
function user_login() {

}
```

__推荐：__

```javascript
function userLogin() {

}
```

__【强制】函数的 参数 使用 Camel命名法__

__不推荐：__

```javascript
function userLogin(user_name) {

}
```

__推荐：__

```javascript
function userLogin(userName) {

}
```

__【强制】由多个单词组成的缩写词，在命名中，根据当前命名法和出现的位置，所有字母的大小写与首字母的大小写保持一致__

__不推荐：__

```javascript
var http = new HTTPRequest();
```

__推荐：__

```javascript
var httpRequest = new HTTPRequest();
```

### 2.3.2 避免名称冗余

__不推荐：__

```javascript
const Car = {
  carMake: 'Honda',
  carModel: 'Accord',
  carColor: 'Blue'
}
```

__推荐：__

```javascript
const Car = {
  make: 'Honda',
  model: 'Accord',
  color: 'Blue'
}
```


## 2.4 注释

### 2.4.1 单行注释

__【强制】必须独占一行__

__示例：__

```javascript
//登录
function userLogin(userName) {

}
```

### 2.4.2 多行注释

__【建议】他用/**/__

__示例：__

```javascript
/*
 * 注释的内容
 */
function userLogin(userName) {

}
```

### 2.4.3 文件注释

__【建议】文件注释中可以用 @author 标识开发者信息，@Date 文件建立日期，@Last Modified by 最后修改人姓名 @Last Modified time 最后修改时间__

__示例：__

```javascript
/*
 * @Author: 'hejianping'
 * @Date:   2017-12-13 14:24:20
 * @Last Modified by:   'hejianping'
 * @Last Modified time: 2017-12-14 10:44:06
 */

function userLogin(userName, password, code) {

}
```

### 2.4.4 函数/方法注释

__【强制】函数/方法注释必须包含函数说明，有参数和返回值时必须使用注释标识__

__【强制】参数和返回值注释必须包含类型信息，且不允许省略参数的说明__

__示例：__

```javascript
/**
 * [userLogin 函数描述]
 * @param  {[string]} userName [参数1的说明]
 * @param  {[string]} password [参数2的说明]
 * @param  {[string]} code     [参数3的说明]
 * @return {[object]}          [返回值描述]
 */
function userLogin(userName, password, code) {
    return {
        userName: userName,
        password: password,
        code: code,
    }
}
```

__【强制】对 Object 中各项的描述， 必须使用 @param 标识__

__示例：__

```javascript
/**
 * [userLogin 函数描述]
 * @param  {[string]} ele      [参数1的说明]
 * @param  {[object]} config   [config项描述]
 * @param  {[string]} config.userName [cconfig项描述，参数1的说明]
 * @param  {[string]} config.password [cconfig项描述，参数2的说明]
 * @param  {[string]} config.code     [cconfig项描述，参数3的说明]
 */
function userLogin(ele,config) {

}
```

### 2.4.5 常量注释

__【强制】常量必须使用 @const 标记，并包含说明和类型信息__

__示例：__

```javascript
/**
 * @const
 * @type {object}
 */

var CONFIG = {}
```

### 2.4.6 细节注释

对于内部实现、不容易理解的逻辑说明、摘要信息等，我们可能需要编写细节注释

__【建议】细节注释遵循单行注释的格式。说明必须换行时，每行是一个单行注释的起始__

__示例：__

```javascript
function userLogin(username, password, code) {
    //这里对具体内部逻辑进行说明
    //说明矿长需要换行
    for(...){
        //doing
    }
}
```

## 3 语言特性

## 3.1 变量

__【强制】变量、函数在使用前必须先定义__

说明：不通过 var 定义变量将导致变量污染全局环境

__不推荐：__
```javascript
var userName = 'hjp'
```
__推荐：__

```javascript
userName = 'hjp'
```

__【强制】每个 var 只能声明一个变量__

说明：一个 var 声明多个变量，容易导致较长的行长度，并且在修改时容易造成逗号和分号的混淆


__不推荐：__
```javascript
var userName = 'hjp';
var pasword = '12345';
var email = '378540660@qq.com';
```
__推荐：__

```javascript
var userName = 'hjp',
    pasword = '12345',
    email = '378540660@qq.com';
```

__【强制】变量必须 即用即声明，不得在函数或其它形式的代码块起始位置统一声明所有变量__

说明：变量声明与使用的距离越远，出现的跨度越大，代码的阅读与维护成本越高。虽然JavaScript的变量是函数作用域，还是应该根据编程中的意图，缩小变量出现的距离空间


## 3.2 条件

__【强制】在 Equality Expression 中使用类型严格的 ===__

__不推荐：__
```javascript
if (a == 1){
    //doing
}
```
__推荐：__

```javascript
if (a === 1) {
    //doing
}
```

__【建议】尽可能使用简洁的表达式__


__不推荐：__
```javascript
//字符串为空
if (name === '') {
    //doing
}

//字符串非空
if (name !== '') {

}

//数组非空
if (arr.length > 0) {

}

//布尔不成立
if (notTrue === false) {

}
```
__推荐：__

```javascript
//字符串为空
if (!name) {
    //doing
}

//字符串非空
if (name) {

}

//数组非空
if (arr.length) {

}

//布尔不成立
if (!notTrue) {

}
```
__【建议】对于相同变量或表达式的多值条件，用 switch 代替 if__


__不推荐：__
```javascript
var type = typeof types;
if (type === 'object') {
    //doing
}
else if (type === 'number' || type === 'boolean' || type === 'string') {
    //doing
}
```
__推荐：__

```javascript
switch (typeof types) {
    case 'object':
        //doing
        break;
    case 'number':
    case 'string':
    case 'boolean':
        //doing
        break;
}
```

## 3.3 循环

__【建议】不要在循环体中包含函数表达式，事先将函数提取到循环体外__

说明：循环体中的函数表达式，运行过程中会生成循环次数个函数对象

__不推荐：__
```javascript
for (var i = 0, len = elements.length; i < len; i++) {
    var element = elements[i];

    element.on('click', function() {
        //doing
    });
}
```
__推荐：__

```javascript
function clicker() {
    //doings
}

for (var i = 0, len = elements.length; i < len; i++) {
    var element = elements[i];

    element.on('click', clicker);
}
```

__【建议】对循环内多次使用的不变值，在循环外用变量缓存__

__不推荐：__
```javascript
for (var i = 0, len = elements.length; i < len; i++) {
    var element = elements[i];

    element.width($('.ele').width());
}
```
__推荐：__

```javascript
var width = $('.ele').width();

for (var i = 0, len = elements.length; i < len; i++) {
    var element =elements[i];

    element.width(width);
}
```

__【建议】对有序集合进行遍历时，缓存 length__

说明：虽然现代浏览器都对数组长度进行了缓存，但对于一些宿主对象和老旧浏览器的数组对象，在每次 length 访问时会动态计算元素个数，此时缓存 length 能有效提高程序性能

__不推荐：__
```javascript
for (var i = 0; i < elements.length; i++) {
    //doing
}
```
__推荐：__

```javascript
for (var i = 0, len = elements.length; i < len; i++) {
    //doing
}
```

## 3.4 类型

### 3.4.1 类型检测

__【建议】类型检测优先使用 typeof。对象类型检测使用 instanceof。null 或 undefined 的检测使用 == null__

__未例：__

```javascript
// string
typeof types === 'string'

// number
typeof types === 'number'

// boolean
typeof types === 'boolean'

// Function
typeof types === 'function'

// Object
typeof types === 'object'

// RegExp
types instanceof RegExp

// Array
types instanceof Array

// null
types === null

// null or undefined
types == null

// undefined
typeof types === 'undefined'
```

### 3.4.2 类型转换

__【建议】转换成 string 时，使用 + ''__


__不推荐：__

```javascript

new String(num);
num.toString();
String(num);
```

__推荐：__

```javascript

num + '';
```

__【建议】转换成 number 时，通常使用 +__


__不推荐：__

```javascript
Number(str);
```

__推荐：__

```javascript
+str;

```

__【建议】string 转换成 number，要转换的字符串结尾包含非数字并期望忽略时，使用 parseInt__


__示例：__

```javascript
var width = '200px';
parseInt(width, 10);
```

__【建议】转换成 boolean 时，使用 !!__


__示例：__

```javascript
var num = 3.14;
!!num;
```

## 3.5 字符串

__【强制】字符串开头和结束使用单引号 '__

说明：

1、输入单引号不需要按住 shift，方便输入。

2、实际使用中，字符串经常用来拼接 HTML。为方便 HTML 中包含双引号而不需要转义写法。


__示例：__

```javascript
var str = '我是字符串';
var html = '<div class="text">拼接HTML可以省去双引号转义</div>';
```

__【建议】使用 数组 或 + 拼接字符串__

说明：

1、使用+拼接字符串，如果拼接的全部是StringLiteral，压缩工具可以对其进行自动合并的优化。所以，静态字符串建议使用 + 拼接。

2、在现代浏览器下，使用 + 拼接字符串，性能较数组的方式要高。

3、如需要兼顾老旧浏览器，应尽量使用数组拼接字符串。

__【建议】复杂的数据到视图字符串的转换过程，选用一种模板引擎__

## 3.6 对象

### 3.6.1 创建对象

__【强制】使用对象字面量 {} 创建新 Object__

__不推荐：__

```javascript
var obj = new Object();
```

__推荐：__

```javascript
var obj = {};
```
__【建议】对象创建时，如果一个对象的所有 属性 均可以不添加引号，建议所有 属性 不添加引号__

__推荐：__

```javascript
var info = {
    name: 'someone',
    age: 28
};
```

### 3.6.2 对象字面量

__创建对象和数组推荐使用字面量，因为这不仅是性能最优也有助于节省代码量__

__不推荐：__

```javascript
var info = {};
info.name = 'tom';
info.age = 15;
info.sex = '男'
```

__推荐：__

```javascript
var info = {
    name: 'tom',
    age: 15,
    sex: '男'
};
```

### 3.6.3 对象设置默认属性的推荐写法

__不推荐：__

```javascript
const menuConfig = {
  title: null,
  body: "Bar",
  buttonText: null,
  cancellable: true
};

function createMenu(config) {
  config.title = config.title || "Foo";
  config.body = config.body || "Bar";
  config.buttonText = config.buttonText || "Baz";
  config.cancellable =
    config.cancellable !== undefined ? config.cancellable : true;
}

createMenu(menuConfig);
```

__推荐：__

```javascript
const menuConfig = {
  title: "Order",
  // User did not include 'body' key
  buttonText: "Send",
  cancellable: true
};

function createMenu(config) {
  config = Object.assign(
    {
      title: "Foo",
      body: "Bar",
      buttonText: "Baz",
      cancellable: true
    },
    config
  );

  // config now equals: {title: "Order", body: "Bar", buttonText: "Send", cancellable: true}
  // ...
}

createMenu(menuConfig);
```

### 3.6.4 将对象的属性值保存为局部变量

__对象成员嵌套越深，读取速度也就越慢。所以好的经验法则是：如果在函数中需要多次读取一个对象属性，最佳做法是将该属性值保存在局部变量中，避免多次查找带来的性能开销__

__不推荐：__

```javascript
let person = {
    info: {
        sex:'男'
    }
}
function  getMaleSex () {
    if (person.info.sex === '男') {
        console.log(person.info.sex)
    }
} 
```

__推荐：__

```javascript
let person = {
    info: {
        sex:'男'
    }
}
function  getMaleSex () {
    let sex = person.info.sex;
    if (sex === '男') {
        console.log(sex)
    }
}
```

### 3.6.5 原生对象和宿主对象的原型

__【强制】不允许修改和扩展任何原生对象和宿主对象的原型__

__禁止：__

```javascript
// 以下行为绝对禁止
String.prototype.trim = function () {
};
```

__【强制】属性访问时，尽量使用 .号__


## 3.7 数组

__【强制】使用数组字面量 [] 创建新数组，除非想要创建的是指定长度的数组__


__不推荐：__

```javascript
var arr = new Array();
```

__推荐：__

```javascript
var arr = [];
```

__【强制】遍历数组不使用 for in__


__【建议】尽量使用数组的 sort 方法__


__【建议】清空数组使用 arr = []__


# 4 其他

尽量避免使用 `==` `!=`, 推荐使用严格比较 `===` `!==` .
* `eval` 非特殊业务， 禁止使用
* `with` 非特殊业务， 禁止使用
