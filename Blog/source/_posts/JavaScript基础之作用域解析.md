title: JavaScript基础之作用域与预解析
date: 2015-11-27 21:15:59
tags:
---
##### 最近这些天都在搞博客，没有什么新的知识点，今天终于了解了一些新的JS知识。其实，我对js一直都挺害怕的，害怕自己学不好，很沮丧...甚至感觉自己不是走前端这条路的。。。不过我会好好努力，尽自己最大的能力去学好它☺



<!-- more -->

**纯属自己整理，如有错误，欢迎在留言板指出**

>①浏览器的准备工作

1.把变量，函数表达式的声明提升到当前的作用域顶端

2.把函数赋值

3.还有一些其他事情

>②JS中的预解析机制

//js在执行的时候，会把所有的声明都提升到当前作用域的顶端。

例：

	var a = '123';
	var b = 15;
	var c = function(){};
	
在js中是这么解析的：

	var a,b,c;
	a = '123';
	b = 15;
	c = function(){};

>③作用域

什么是作用域呢？
作用域只有两种：1、全局作用域 2、局部作用域

全局作用域：它的定义很简单，如果一个变量或者函数是全局的，那么在任何地方都可以访问它们。在浏览器中，全局作用域其实就是window对象。咱们之前声明的变量，实际上就是在window对象上创建了一个属性。

	var i = 10;//window.i = 10
	
全局变量怎么声明呢？不使用var关键字。

局部作用域，就是通过函数来创建。

	function fn(){
		var i = 20;
	}
	fn();
	console.log(i);

*在js中都是全局作用域，if、for里没有作用域的概念，只有函数中的才是局部作用域。

*关于局部变量和全局变量：

1、全局变量可以在任何地方访问；

2、函数内部的变量，在外部是不可见的；

3、函数内部可以访问外部函数的变量；

4、局部变量指的是在函数内部的声明。


>④创建函数的三种方式

1、声明函数（函数声明），就是使用function关键字 + 函数名声明的函数。

	function fn(){
		//do sth.
	}
	fn();

2、函数表达式，就是使用function关键字，没有函数名，赋值给一个变量的函数。

	var fn = function(){
		//do sth.
	}();
	//fn();

3、匿名函数，就是使用function关键字但是没有函数名的函数。

	(function(){
		//do sth.
	})();
	
*区别：函数表达式可以使用（）操作符，表示立即执行；声明函数不可以；

*（）（）；第一个（）把匿名函数定义成函数表达式，第二个（）表示立即执行。

##### 关于return返回值：每个function函数都有默认的return返回值，就是undefined。

	function fn(){
		console.log('hello world');
		
		//有默认的返回值，undefined
	}
	console.log(fn());//打印出来看看返回值

