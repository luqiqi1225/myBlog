title: CSS的知识点梳理
date: 2015-11-27 21:03:50
tags:
---
**自己整理，如有错误，欢迎在留言板指出**

# CSS的引入方式


	1、<style>标签引入方式（内部样式引入）；

	2、标签内部引入方式（行间样式）优先级最高；

	3、link外部样式引入。

**有冲突的样式，标签内部的引入方式高于style标签的引入方式。**

<!-- more -->

**①div样式**

>width:标签元素的宽度

>height:标签元素的高度

>background-color:背景颜色

>background-image:背景图片

>background-repeat:是否平铺

>background-position:位置


**②边框样式（border）**

>border-style:solid/dotted/dashed/double 实线/点状线/虚线//

>边框样式，没有默认值

>border-color:默认颜色值是字体颜色，默认的字体颜色是黑色

>border-width:默认值是3px的宽度，数值不能为负数

>border:10px red groove 3D凹槽边框，有兼容性问题，火狐支持的很好

>border:10px red ridge 3D垄状边框，有兼容性问题，火狐支持的很好

>border:inside outside

**③内边距（padding）**

>"TRBL"法则：top、right、bottom、left

>padding不可以用于background，因为背景有自己的position，可以用于文字、标签。

# 选择器及优先级

**①标签选择器：**直接作用于选择的标签元素，是一个集合

	div{
		//do sth
	}

**②ID选择器：**直接作用于叫该名称的标签元素，名称是唯一的，标签也是唯一的，只对该名称标签有效

	#box{
		//do sth
	}

**③父子选择器：**又叫层级选择器

层级选择器用空格隔开，有顺序，生效最里面的子集。
例：

	body .box #duan{
		//do sth
	}

**④类选择器：**

	.class{
		//do sth
	}

**⑤群组选择器：**用’，‘隔开，无顺序可言

div,.box,#box1{
	//do sth
}

**⑥通配选择器**

	*{
		//do sth
	}

# 浮动布局

float : left / right / none; 向左浮/向右浮/默认值（不浮）

## 清除浮动的几种方法：

- 给浮动元素的父级添加内容高度；

- 给浮动元素的父级添加overflow：hidden；必备条件是有宽度或者高度，需要设置宽或高，但是有高度的话，就不需要设置overflow：hidden了；

- 在浮动元素的下方，同级关系的标签元素设置clear：left/right/both；需要添加额外标签来清楚浮动。

# position位置(三种类型)

- relative 相对定位：对标签没有属性改变，设置left/right/top/bottom方向可以偏移位置；有z-index的级别样式，默认后面标签元素覆盖前面元素。

- absolute 绝对定位：对标签元素有属性改变(变成inline-block属性)；脱离文档流；float无效；有清楚浮动的效果；内容撑开宽度、高度；有z-index层级样式；margin：0 auto 无效；默认后面标签元素覆盖前面元素；以父级标签设置relative或者absolute属性后为方向起点；没有父级设置，以body左上角为方向起点.

- fixed 固定定位：类似于绝对定位，有改变元素属性；方向固定后，是以浏览器窗口定位；不会因为html文档滚动而改变位置，可以用百分比（width:100%,height:100%）

**这三种类型，大部分以布局为主**