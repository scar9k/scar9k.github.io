---

layout: post

title: childNodes , nodeType , nodeValue
date: 2017-07-21
tags:
        - 前端
        - DOM
---
原生DOM中的childNodes,nodeType,nodeValue
---
![](/images/childNodes.jpg)
---
childNodes
---
childNodes属性是包含某一种元素的所有子元素的数组，可以用于获取任意一种元素的所有子元素。

element.childNodes

比如，如果我们要吧某个文档内的所有的子元素全部检索出来，可以使用

```cpp

var body_elems = getElementsByTagName("body")[0]

/**0指的是文档搜索起始点，因为一个文档body元素只有一个所以为0**/

body_elems.childNodes

```

如果测试该数组的length会发现有很多的子元素，因为文档树的节点类型并非元素节点一种。

甚至空格之类的每一样东西都是一个节点。

---
nodeType
---

nodeType可以获取元素的类型

```cpp

body_elems.nodeType

```

得到的结果是1

nodeType有12种可取值

元素节点的值是 1

属性节点的值是 2

文本节点的值是 3

---
nodeValue
---

nodeValue可以用于获取和修改一个节点的值

而在使用nodeValue获取一个对象时，得到的并不是对象的文本。

比如有id=description的段落

```cpp

var description = document.getElementById("description")

alert (description.nodeValue)

```

得到的值是null，因为这指向的对象是一个段落，而不是段落中的文本。

---
firstChild和lastChild
---

我们可以使用childNode

或是firstChild和lastChild

```cpp

description.childnotes[0].nodeValue

description.firstchild.nodeValue

```

可以达到同样的效果



