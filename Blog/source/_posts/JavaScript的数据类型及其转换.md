title: JavaScript的数据类型的转换及判断
date: 2015-12-05 20:40:28
tags:
---
沉寂好久，今天我来更博啦～博主最近学js学到头昏脑涨...所以也没有顾及到博客，虽然可能也没啥人来看偶滴博客，但是！如果你们来了，请留下你们的脚印，让我知道你们来过..hahaha...自嗨结束，开始进入正题↓


<!-- more -->


### JS的数据类型：简单的数据类型&复杂的数据类型

#### 简单的数据类型：

string 字符串类型

	var str = '123';

Boolean 布尔类型

	var onOff = true;
	var onOff = false;

Number 数字类型

	var num = 1; 

Null 空类型，表示一个空对象,

作用：一般用来保存值或清空（对象）的

undefined 未定义类型

#### 复杂的数据类型：

object 对象类型

	var obj = {
		
	}

Array 数组

	var arr = [];

function 函数

	var fu = function(){
		//do sth;
	}

### Boolean()转换

	boolean：true（1）/false（0）

	str:true(任何非空字符串)/false（空字符串）

	number:true(任何非0数字)/false（0和Nan（非数值））

	object：true（任何对象）/false（null）

	undefined：true（n/a不适用）/false（undefined）

*数值类型：有整数和浮点数，有最大值和最小值，超出范围显示正负无穷，不要用浮点数作对比

*NaN表示一个特殊的数值，不和任何数值对等，包括自己

*isNaN（）;用于判断是否为数值

#### 转换成字符串类型：

	①String()；可以用于任何类型

	②toString();不能用于null和NaN，其他可用

#### 数据类型的判断

简单的数据类型用typeof来检测，复杂的数据类型用instanceof来判断

instanceof主要针对function、object、array、new Number()、new String()、new Boolean()等复杂的数据类型判断，它还能判断它的继承方向。

例：

	var str = '123';//字面量

等同于：

	var str = new String('123');//构建一个字符串对象

	console.log(typeof str);//结果：String类型

	var arr = [1,2,3,4];

	var obj = {
		a:10,
		b:20
	};

	var fn = function(){
		//do sth;
	}();

下面我们来用instanceof检测它们：

console.log(str instanceof String);//false 

这里可以理解为：str是否引用自String//不是

String是简单的数据类型，不可用instanceof来判断，只能用typeof来检测：console.log(typeof str)

	console.log(arr instanceof Object);//true

	console.log(fn3 instanceof function);//true

	console.log(fn3 instanceof Object);//true

	console.log(obj instanceof Object);//true

**如果有错误，欢迎在留言板指出**