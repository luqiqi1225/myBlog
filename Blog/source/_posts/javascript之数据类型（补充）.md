title: javascript之数据类型（补充）
date: 2016-03-01 19:22:59
tags:
---

# JavaScript的数据类型

JavaScript中有5种简单数据类型（也称为基本数据类型）：Undefined、Null、Boolean、Number和String。还有1种复杂数据类型--Object，Object本质上是由一组无序的名值组成的。

## typeof操作符

介于Javascript是松散类型的，因此需要有一种手段来检测给定变量的数据类型--typeof就是负责提供者方面信息的操作符。对一个值使用typeof操作符可能返回下列某个字符串：

- undefined ——如果这个值未定义
- boolean ——如果这个值是布尔值
- string ——如果这个值是字符串
- number ——如果这个值是数值
- object ——如果这个值是对象或null
- function ——如果这个值是函数

## Undefined类型
undefined类型只有一个值，即特殊的undefined。在使用var声明变量但未对其加以初始化时，这个变量的值就是undefined，例如：

	var a;
	console.log(a);//结果是 undefined
	
## Null类型
null类型是第二个只有一个值的数据类型，这个特殊的值是null。从逻辑角度来看，null值表示一个空对象指针，而这也正是使用typeof操作符检测null时会返回“object”的原因，例如：

	var b = null;
	console.log(typeof b);//"object"
	
如果定义的变量准备在将来用于保存对象，那么最好将该变量初始化为null而不是其他值。这样，只要检测null值就可以知道相应的变量是否已经保存了一个对象的引用了，例如：

	if(b != null){
		//对b对象执行某些操作
	}
	
实际上，undefined值是派生自null值的，因此ECMA-262规定对它们的相等性测试要返回true。

	alert（undefined == null）;//ture
	
尽管null和undefined有这样的关系，但它们的用途完全不同。无论在什么情况下都没有必要把一个变量的值显式地设置为undefined，可是同样的规则对null却不适用。换言之，只要意在保存对象的变量还没有真正保存对象，就应该明确的让该变量保存null值。这样不仅可以体现null作为空对象指针的惯例，而且也有助于进一步区分null和undefined。

## String类型
String类型用于表示由0或多个16位Unicode字符组成的字符序列，即字符串。字符串可以由单引号或双引号表示。

	var str1 = 'hello';
	var str2 = "hello";
	
任何字符串的长度都可以通过访问其length属性取得

	console.log(str1.length);//输出5
	
	
	*本片博客参考自java_my_life
	
**未完待续...**