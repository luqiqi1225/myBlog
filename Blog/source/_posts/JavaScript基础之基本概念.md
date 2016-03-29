title: JavaScript基础之基本概念
date: 2015-11-27 21:08:01
tags:
---
**纯属自己整理，如有错误，欢迎在留言板指出**

<!-- more -->

JavaScript分为三部分：

1、ECMA核心

2、DOM文档对象模型(Document Object Model) API 节点

3、BOM浏览器对象模型(Browser Object Model)

HTML中JS的引用：

	<script type="text/javascript" src = "index.js"></script>
	
derfer属性，只对外部JS引用有效果，立即下载JS，文档加载完成前，不执行。

async属性，只对外部JS引用有效果，异步的加载JS文件，没有顺序可言。