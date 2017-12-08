---
layout:     post
title:      "图片居中的两种最简处理"
subtitle:   ""
date:       2017-12-07 16:25
author:     "CS"
header-img: "img/posts/yu.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 前端开发
    - css
    - 图片
    - 居中
---

> 这里不再介绍图片居中的众多方法（绝对定位，table方法，flex布局等），只介绍两种最简单的常用方法。

## 问题

我们先有一个div（已知宽高），div内部有一个img标签，如何让img居中（简单实用）？


```css
body{
    margin:0;
    padding:0;
}
div{
    width:400px;
    height:400px;
    border:1px solid green;
}
img{
    /* 这张图片(zixia.jpg)宽高为200*200 */
    }
```
```html
<body>
    <div>
    	<img src="../img/zixia.jpg" alt="">
    </div>
</body>
```
## 第一种居中方式
注意div和img增加的样式增加的部分

```css
div{
    width:400px;
    height:400px;
    border:1px solid green;
    text-align: center;/* 水平方向居中所需 */
    line-height:400px;/* 垂直方向居中所需 */
    font-size:0;/* 解决inline-block元素垂直方向产生的2px间隙 */
}
img{
    /* 这张图片(zixia.jpg)宽高为200*200 */
    vertical-align: middle;/* 垂直方向居中所需 */
    }
```
## 第二种居中方式
注意div和img增加的样式增加的部分

```css
div{
    width:400px;
    height:400px;
    border:1px solid green;
    text-align: center;/* 水平方向居中所需 */
}
img{
    /* 这张图片(zixia.jpg)宽高为200*200 */
    vertical-align: top;/* 垂直方向居中所需 */
    margin-top:100px;/* 垂直方向居中所需 (div高-img高)*0.5 */ 
    }
```
接下来大家可以试一下效果，其中font-size：0是为了解决inline-block(行内块元素的间隙问题)