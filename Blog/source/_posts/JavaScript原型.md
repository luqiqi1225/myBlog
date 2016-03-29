title: JavaScript原型与this
date: 2015-12-07 19:10:28
tags:
---
今天又是新的一周的开始，感觉时间过得好快又好慢...对于未知的将来，既期待又担忧...希望自己可以好好的把该掌握的知识点掌握了，不期望自己能够多厉害，只要能尽自己最大的力学好就ok，怀挺～～～～～

<!-- more -->

### 1、原型

①prototype 原型，当前函数的原型；

所有的函数都有prototype属性，该属性是一个对象，

作用：是给当前函数增加属性的

假如这个函数没有任何属性的话，prototype对象，默认有个construction属性，该属性指向当前函数本身

	function fn(){
		console.log(fn.prototype);
	}
	fn();
	
	可以打印出一个fn{}对象，里面包含了一个默认属性construction：function fn(){}，指向当前函数本身,里面包含prototype对象（当前函数的原型）；和一个__proto__:Object；以及一些其他的属性

construction：function fn(){}，指向当前函数本身，我们来验证一下：
	
	function fn(){
	console.log(fn.prototype.constructor);
	}
	fn();
	
	可以打印出一个结果：function fn();


②__proto__ 也叫原型，指向创建当前函数对象的函数prototype；

所有的对象都有__proto__属性。


下面来看一个例子：

	function fn(){
		fn.prototype.name = 'xiaoqiqi';
		fn.prototype.age = 18;
		fn.prototype.star = function(){
			// return '10';
			console.log('123');
		}
	}
	var fn2 = new fn();//从fn方法里面new出一个实例；生成对象fn2，所有的对象都有__proto__属性；所有的函数都有prototype属性;这里的fn2继承父级fn里的所有内容；
	// fn2.__proto__.sex = '男';//通过__proto__给fn2里增加一个sex属性，父级里也增加了，这个sex属性在__proto__里；破坏了原生链，原生的__proto__里面的内容也增加了；一般不推荐
	fn2.age = 20;//给new出来的新的对象fn2里的age属性改变内容（用fn2.age=20改变的话 只是改变的fn2里的age，fn里的并不会受到影响）
	console.log(fn2.age);//查看属性age的内容；(这时如果用父级fn.age来查看是undefined)
	console.log(fn.prototype);//查看父级里的所有属性内容（要通过prototype;在这里我的理解是 把prototype当成函数fn下的一个装属性的容器，它是一个对象，里面有__proto__属性，它也是一个对象，是指向创建当前函数【这时这个函数变成了一个对象】prototype）
	console.log(typeof fn2);//object
	console.log(fn2.__proto__ === fn.prototype);//true
	
	
### 2、this

①函数声明、匿名函数、函数表达式在全局中调用，this指向window

	(function(){
		console.log(this);//在全局作用域下面调用this，this指向global，也就是window
	})();
	
②new关键词构造的对象，this指向构造的新对象

	var fn1 = function(){
	this.x = 10;
	this.y = 10;

	console.log(this);//fn1{x:10,y:10}(这里的this指的fn1，这时fn1不是函数，变成了一个对象)
	}
	var fn2 = new fn1();//fn2是由fn1 new出来的一个对象
	console.log(fn1);//在全局中打印fn1，fn1还是函数本身
	
③this当前的函数为对象属性的时候，this指向该对象

	var obj = {
	x:10,
	y:20,
	fn1:function(){
		this.x = 20;
		console.log(this);//Object{x:20,y:20}(这时候this指的是obj这个对象)
		}
	}
	obj.fn1();
	console.log(obj.x);//20
	
再来看一个例子：
	
	var fn1 = function(){
	console.log(this);
	this.x = 10;
	this.y = 20;
	}
	fn1();
	console.log(window.x);
	
	//这里的this指的是window，因为fn1()在全局中运行，所有这里的this指的是window
	
	
**this肯定是指向的一个对象**
**一般在函数内部使用this**
**基础数据的属性不会报错，是undefined**

**如果有错误，欢迎在留言板指出哟**