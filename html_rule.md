[1 语法](#1-语法)

[2 HTML5 doctype](#2-html5-doctype)

[3 字符编码](#3-字符编码)

[4 页面说明注释](#4-页面说明注释)

[5 Description和Keywords](#5-Description和Keywords)

[6 引入CSS, JS](#7-%E5%BC%95%E5%85%A5css-js)

[7 属性顺序](#8-属性顺序)

[8 boolean属性](#9-boolean属性)

[9 低权重原则]避免滥用子选择器













# 1 语法


- 缩进使用soft tab（4个空格）；
- 嵌套的节点应该缩进；
- 在属性上，使用双引号，不要使用单引号；
- 属性名全小写，用中划线做分隔符；
- 不要在自动闭合标签结尾处使用斜线（HTML5 规范 指出他们是可选的）；
- 不要忽略可选的关闭标签，例：&lt;/li&gt; 和 &lt;/body&gt;。

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page title</title>
    </head>
    <body>
        <img src="images/company_logo.png" alt="Company">
        <h1 class="hello-world">Hello, world!</h1>
    </body>
</html>
```

# 2 HTML5 doctype

在页面开头使用这个简单地doctype来启用标准模式，使其在每个浏览器中尽可能一致的展现；

虽然doctype不区分大小写，但是按照惯例，doctype大写 （关于html属性，大写还是小写）。

```html
<!DOCTYPE html>
<html>
    ...
</html>

```

# 3 字符编码

通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为'UTF-8'。


```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>
    ...
</html>
```

# 4 页面说明注释

在head区域中加上对页面相关人员注释：CP，不能为其他内容。方便在产品环境中的查看。


```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="uft-8">
        <title>多彩宝互联网服务有限公司</title>
        <link href="css/index.css" />
        <!-- 页面设计：name | 页面重构：name | 前端开发：name | 创建：xxxx-xx-xx -->
    </head>
    <body>
        ...
    </body>
</html>
```

# 5 Description和Keywords

注：Description值一般为页面标题或主题，针对该页面主题的说明。Keywords为产品名、专题名、专题相关名词，之间用英文半角逗号隔开。


```html
<meta name="Description" content="" />
<meta name="Keywords" content="" />
```

# 6 引入CSS, JS

根据HTML5规范, 通常在引入CSS和JS时不需要指明 type，因为 text/css 和 text/javascript 分别是他们的默认值。

HTML5 规范链接

- 使用link
- 使用style



```html
<!-- External CSS -->
<link rel="stylesheet" href="code-guide.css">

<!-- In-document CSS -->
<style>
    ...
</style>
```

# 7 属性顺序

属性应该按照特定的顺序出现以保证易读性；(不做硬性要求)


HTML5 规范链接

- class
- id
- name
- data-*（一般由前端使用）
- src, for, type, href, value , max-length, max, min, pattern
- placeholder, title, alt
- aria-*, role
- required, readonly, disabled

class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位。


```html
<a class="..." id="..." data-modal="toggle" href="#">Example link</a>
<input class="form-control" type="text"/>
<img src="..." alt="..."/>
```

# 8 boolean属性

boolean属性指不需要声明取值的属性，XHTML需要每个属性声明取值，但是HTML5并不需要；

更多内容可以参考 WhatWG section on boolean attributes：

boolean属性的存在表示取值为true，不存在则表示取值为false。



```html
<input type="text" disabled />
<input type="checkbox" value="1" checked />
<select>
    <option value="1" selected>1</option>
</select>
```


# 9 避免滥用子选择器

HTML标签的权重是1，class的权重是10，id的权重是100，例如p的权重是1，“div em”的权重是1+1=2，“strong.demo”的权重是10+1=11，“#test.red”的权重是100+10=110.






