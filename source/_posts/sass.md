---
title: CSS预处理器概念
date: 2017-08-21
tags:
     - DOM
     - css预处理
     - Sass
---
CSS预处理器
---
对css预处理器早有耳闻，但是一直没有接触过。于是今天了解了解。

---
Sass和Less
---
首先了解下CSS预处理器都有什么特点
-混合（Mixins）:class中的class;
-参数混合（Parametric）：可以像函数一样传递的class
-嵌套规则（Nested Rules）：class中嵌套class，提高代码复用性
-运算（Operations）：css中的运算
-颜色功能（Color function）：可以编辑你的颜色
-命名空间（Namespaces）：样式分组，从而方便被调用
-作用域（Scope）：可以局部修改样式
-JavaScript表达式（Javascript evaluation）:在css样式中使用JavaScript表达式赋值。

---
Less和Sass在实现方式上的不同
---
Less是基于JavaScript运行的
Sass需要在ruby上运行

<a href="https://www.sass.hk/" ><img src="https://i.loli.net/2017/09/08/59b1a7f63a76c.png"></a>
相比之下Sass有什么特点
---
1.Sass有变量和作用域
```$variable```like php
```#{$variable}```like ruby
变量有全局和局部之分，并且有优先级。
2.Sass有函数的概念
```@function```和```@return```以及函数参数（还有不定参数）可以像JS一样封装逻辑函数。
```@mixin```类似function但是没有想function的逻辑，更多的是提高代码的复用性，和模块化。
```ruby```提供了非常全面的内置原生api
3.进程控制
条件：``@if`` ``@else``
循环遍历：``@each`` ``@while`` ``@for``
继承：``@extend``
引用：``@import``
4.数据结构：
``$list``类型=数组
``$map``类型=对象
也有``string`` ``number`` ``function``
5.为了和LESS竞争而完全兼容css

编译器
---
koala（考拉）是一个国产免费前端预处理语言图形编译工具
<img src="https://i.loli.net/2017/09/08/59b1a7f7e4d78.png">
<a href=https://www.sass.hk/skill/koala-app.html>下载地址</a>
