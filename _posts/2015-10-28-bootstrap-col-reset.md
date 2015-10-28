---
layout: post
title: 使用bootstrap的grid进行布局时列自动换行的问题
category: CSS
tags: [css,bootstrap]
---

##问题

使用bootstrap3的grid进行布局，当第一列的高度高于其他列时，自动换行的列不能够从行的最左侧开始排列。

问题代码示例 <http://output.jsbin.com/gedujediwa>

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css" integrity="sha512-dTfge/zgoMYpP7QbHy4gWMEGsbsdZeCXz7irItjcC3sPUFtf0kuFbDz/ixG7ArTxmDjLXDmezHubeNikyKGVyQ==" crossorigin="anonymous">
  <meta charset="utf-8">
  <title>JS Bin</title>
  <style>
    .col {border:1px red solid;}
    .hei100 {height:100px;}
    .hei200 {height:150px;}
  </style>
</head>
<body>
<div class="row">
  <div class="col-md-4 col-sm-3 hei200 col">第一列 <br> 这列比其他列高</div>
  <div class="col-md-4 col-sm-3 hei100 col">第二列</div>
  <div class="col-md-4 col-sm-3 hei100 col">第三列</div>
  <div class="col-md-4 col-sm-3 hei100 col">第四列</div>
  <div class="col-md-4 col-sm-3 hei100 col">第五列</div>
</div>
</body>
</html>
```

## 解决办法

在需要换行的列后面添加一个div并使用clearfix消除float效果，并且clearfix可以和[responsive utilities](http://getbootstrap.com/css/#responsive-utilities)一起使用使其在不同屏幕尺寸生效。 例如我们需要在最小的屏幕（xs）显示两列，而其他的屏幕显示三列，那么可以用下面的代码实现。<http://output.jsbin.com/tefiwu>

```html
<div class="row">
  <div class="col-md-4 col-sm-4 col-xs-6 hei200 col">第一列 <br> 这列比其他列高</div>
  <div class="col-md-4 col-sm-4 col-xs-6 hei100 col">第二列</div>
  <div class="clearfix visible-xs-block"></div>
  <div class="col-md-4 col-sm-4 col-xs-6 hei100 col">第三列</div>
  <div class="clearfix hidden-xs"></div>
  <div class="col-md-4 col-sm-4 col-xs-6 hei100 col">第四列</div>
  <div class="col-md-4 col-sm-4 col-xs-6 hei100 col">第五列</div>
</div>
```

