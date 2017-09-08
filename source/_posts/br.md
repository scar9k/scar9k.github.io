---
layout: post
title: 关于br在html5中的写法
date: 2017-07-15
tags:
     - 前端
     - 转载
---
from <a href="https://www.zhihu.com/question/21632236/answer/18824702"target=_blank>知乎</a>
![](/images/brinh5.jpg)
&lt;br&gt;是HTML写法。
&lt;br/&gt;是XHTML1.1的写法，也是XML写法。
&lt;br /&gt;是XHTML为兼容HTML的写法，也是XML写法。
因为HTML5兼容XHTML写法，所以三种都可以使用，没有区别。
如果要省一到二个字节的文件大小，使用第一种。
如果要方便地转成XML而且也要省一个字节的文件大小，使用第二种。
如要要方便地转成XML而且要兼容老的浏览器，使用第三种。因为HTML是SGML的子集，SGML允许标签没有结束标签，而换行符元素正好不需要内嵌元素，也就不需要结束标签。
所以在HTML中，应该写成&lt;br&gt;。
因为XHTML是XML的子集，在XML中，标签必须要有结束标签。
所以在XHTML中只写&lt;br&gt;是不符合语法的，必须写成&lt;br&gt;&lt;/br&gt;或简写成&lt;br/&gt;。
而在XHTML的发展过程中，要做到兼容旧的HTML浏览器。
而旧的HTML浏览器不理解（错误理解）这两种写法，对于第一种写法，某些浏览器估计会理解成两个&lt;br&gt;标签（我没有资料证明这一点），对于第二种写法，某些浏览器会理解成一个叫"br/"的标签。
所以在兼容HTML的XHTML中我们通常把它写成&lt;br /&gt;，这样在HTML解析中会理解成有一个叫"/"的属性的"br"标签，在XML解析中仍然会理解成&lt;br&gt;&lt;/br&gt;的简写，达到了两全其美的效果。