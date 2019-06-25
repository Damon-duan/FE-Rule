  

[1 缩进](#1-缩进)  

[2 分号](#2-分号)  

[3 空格](#3-空格)  

[4 换行](#4-换行)  

[5 注释](#5-注释)  

[6 命名](#6-命名)  

[7 声明顺序](#7-声明顺序)  

[8 颜色](#8-颜色)  

[9 媒体查询](#9-媒体查询)  


# 1 缩进

使用soft tab（4个空格）。  

```css
.element{
    position: absolute;
    top: 10px;
    left: 10px;
    width: 50px;
    height: 50px;
    border-radius: 10px;
}
```

# 2 分号

每个属性声明末尾都要加分号。  

```css
.element{
    width: 20px;
    height: 20px;
    background-color: red;
}

```

# 3 空格

以下几种情况不需要空格：  

- 属性名后
- 多个规则的分隔符','前
- !important '!'后
- 属性值中'('后和')'前
- 行末不要有多余的空格

以下几种情况需要空格：  

- 属性值前
- 选择器'>', '+', '~'前后
- !important '!'前
- @else 前后
- 注释'/*'后和'*/'前

```css
/* not good */
.element{
    color :red! important;
    background-color: rgba(0,0,0,.5);
}

/* good */
.element{
    color: red !important;
    background-color: rgba(0, 0, 0, .5);
}

/* not good */
.element>.dialog{
    ...
}

/* good */
.element > .dialog{
    ...
}

/* not good */
@if{
    ...
}@else{
    ...
}

/* good */
@if{
    ...
} @else {
    ...
}

```

# 4 换行

以下几种情况不需要换行：  

- '{'前
以下几种情况需要换行：  

- '{'后和'}'前
- 每个属性独占一行
- 多个规则的分隔符','后

```css
/* not good */
.element
{color: red; background-color: black;}

/* good */
.element{
    color: red;
    background-color: black;
}

/* not good */
.element, .dialog{
    ...
}

/* good */
.element,
.dialog{
    ...
}
```

# 5 注释

注释统一用'/* */'（scss中也不要用'//'），具体参照右边的写法；  

缩进与下一行代码保持一致；  

可位于一个代码行的末尾，与代码间隔一个空格。  

```css
/* Modal header */
.modal-header{
    ...
}

/*
 * Modal header
 */
.modal-header{
    ...
}

.modal-header{
    /* 50px */
    width: 50px;

    color: red; /* color red */
}
```

# 6 命名

- 类名使用小写字母，以中划线分隔
- id采用中线式命名
- scss中的变量、函数、混合、placeholder采用中线式命名
- 插件外层盒子以daq开头

```css
/* class */
.element-content{
    ...
}

/* id */
#my-dialog{
    ...
}

/* 变量 */
$color-black: #000;>

/* 插件盒子 */
.daq-dialog{
    ...
}
```

# 7 声明顺序

相关的属性声明应当归为一组，并按照下面的顺序排列：  

- Positioning
- 2. Box model
- 3. Typographic
- 4. Visual
由于定位（positioning）可以从正常的文档流中移除元素，并且还能覆盖盒模型（box model）相关的样式，因此排在首位。盒模型排在第二位，因为它决定了组件的尺寸和位置。  

其他属性只是影响组件的内部（inside）或者是不影响前两组属性，因此排在后面。  


```css
.element{
    /* Positioning */
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 100;

    /* Box-model */
    display: block;
    float: right;
    width: 100px;
    height: 100px;

    /* Typography */
    font: normal 13px "Helvetica Neue", sans-serif;
    line-height: 1.5;
    color: #333;
    text-align: center;

    /* Visual */
    background-color: #f5f5f5;
    border: 1px solid #e5e5e5;
    border-radius: 3px;

    /* Misc */
    opacity: 1;
}
```

# 8 颜色

颜色16进制用小写字母；  

颜色16进制尽量用简写。  

```css 
/* not good */
.element{
    color: #ABCDEF;
    background-color: #001122;
}

/* good */
.element{
    color: #abcdef;
    background-color: #012;
}
```


# 9 媒体查询

尽量将媒体查询的规则靠近与他们相关的规则，不要将他们一起放到一个独立的样式文件中，或者丢在文档的最底部，这样做只会让大家以后更容易忘记他们。  


```css 
.element{
    ...
}

.element-avatar{
    ...
}

@media (min-width: 480px){
    .element{
        ...
    }

    .element-avatar{
        ...
    }
}
```

