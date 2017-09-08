---
layout: post
title: window.onload相关
date: 2017-07-21
tags:
         - 前端
         - DOM
---
网页的有些函数必须在用户使用前提前加载才能正确地执行。
如果要让函数在页面加载时执行，我们可以使用onload函数。
```cpp
window.onload = functionname
```
如有多个函数需要在页面加载时，如果把他们依次
```cpp
window.onload = function1
window.onload = function2
```
实际执行时会只执行最后的那条指令。
![](/images/windowonload.jpg)

解决方法1
```cpp
window.onload =funtion(){
function1();
function2();
...
}
```

解决方法2
使用addLoadEvent()
```cpp
addLoadEvent(function1);
addLoadEvent(function2);
```