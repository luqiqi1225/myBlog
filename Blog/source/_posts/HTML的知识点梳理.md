title: HTML的知识点梳理
date: 2015-11-26 09:30:30
tags:
---
**纯属自己整理，如有错误，欢迎在留言板指出**
>## 编辑器

目前为止我只接触了一个Sublime Text这个编辑器,没有安装任何插件，都是手动敲代码，以后还会接触一些其他的编辑器，我很期待哟～

<!-- more -->

>## 终端命令

cd 进入 （例：cd Desktop/ 进入桌面）

cd .. 返回上一级

ls 查看当前的文件（当前文件的内容）

pwd 查看当前路径 

mkdir 创建文件夹 （例：mkdir web 创建一个叫web的文件夹）

touch 创建文件（例：touch index.html 创建一个叫index的html文件）

*注：文件夹不要用中文，文件名称不要用中文

>## MAC系统下Sublime Text一些常用的快捷键

command + +放大字体

command + -缩小字体

command + L选取整行

command + KK删除光标处后面的内容，对上一行和下一行内容无影响

command + j 合并行

command + / 注释

command +S保存

command +N 新建文档

command +Z 回退

command +shift+P 命令板

CTRL+`console命令行（调试器）

command +↑返回上级菜单

alt + command +i打开开发者工具

tab缩进

command+Q关闭应用

command+shift+3全屏截图

command+shift+4区域截图

command + 空格 切换输入法

command +，打开工具偏好设置

*注：在MAC系统下 ”整理“就是刷新，”强制退出“就是任务管理器，page(word)、number（Excel）、Keynote(PPT)

>## HTML（超文本标记语言）

**标签是让文本有自己的语意，方便浏览器、搜索引擎爬虫识别**

!doctype不是一个标签，它是告诉浏览器用什么版本解析（是头文档声明）

html文档标准：

1.所有的标签属性命名都要用小写，属性值用双引号；

2.html文档包括两部分：head和body；

3.head必须要有title，和编码格式；

4.所有可见内容都要放在body里面

*下面是一个完整的html的基本格式：

    <!DOCTYPE html>
    <html lang="en">
    <head>
	      <meta charset="utf-8"/><!-- 代码编码格式，用中文的意思，不然会出现乱码 -->
	      <title>标题</title>	
	      <link rel="stylesheet" type="text/css" href="css样式表的路径">
    </head>
	<body>
		<div>我是一个div，是个块级标签，表示一块区域</div>
	</body>
    </html>

####*body有默认的margin:8px，如何去掉？
body{margin:0;}
### ①div标签

	<div></div>
块级标签（block），表示区域

不设置具体宽度时，默认宽度为100%，充满整屏；不设置具体高度时，默认高度为0；字体可以撑开高度；有父级的话，继承父级宽高；margin、padding有效，宽高有效，有默认宽度、border，背景有效。
### ②P标签

	<p></p>
块级标签（block），表示段落

不设置宽高时，继承父级宽高；margin、padding有效，宽高有效，有默认宽度、border，背景有效。

### ③span标签

	<span></span>
行级标签（inline），作用：放一些无语意的文本内容

宽高无效，默认没有宽高，纵向margin、纵向padding无效，横向的有效，可以设置背景、边框

### ④a标签

	<a></a>
行级标签（inline),用作链接（锚点）

	<a href = "#">我是锚点</a>

a标签有四种状态：

	1、a:link{};
	表示当前的锚点没有被访问过的样式，就是初始样式。
	2、a:visited{};
	表示访问过后的样式。	
	3、a:hover{};
	表示鼠标悬浮在上面的样式。
	4、a:active{};
	鼠标点击没有松开的样式。
	
a标签有默认的属性：下划线;
如何去掉这些默认的属性？
text-decoration:none/underline;

### ⑤img标签

	<img src = "" alt = "" title = "" width =    height= />
	
行级标签，单标签；特殊的：可以设置宽高，在HTML中设置；有src路径属性，alt内容代替属性，title提示属性。

图片边框样式：
img{boder:none};

### ⑥link标签

	<link rel="stylesheet" type="text/css" href="css样式表的路径">
单标签，有两个属性：rel 表示类型，stylesheet表示为样式表类型；type表示关联的文件类型是css，href是路径。

### ⑦h1～h6标签

	<h1></h1> 一级标题
	<h2></h2> 二级标题
	<h3></h3> 三级标题
	<h4></h4> 四级标题
	<h5></h5> 五级标题
	<h6></h6> 六级标题
块级标签，不设置宽高时，继承父级宽高；margin、padding有效，宽高有效，有默认宽度、border，背景有效。

有默认的margin，如何去掉默认属性？

	h1,h2,h3,h4,h5,h6{margin:0;}
### ⑧列表标签

	有序列表,ol和li必须成套使用,ol为列表,li为列表项
	<ol>
		<li>列表1</li>
		<li>列表2</li>
		<li>列表3</li>
	</ol>
	无序列表,属性同ol
	<ul>
		<li>列表1</li>
		<li>列表2</li>
		<li>列表3</li>
	</ul>
	字典列表或者自定义列表
	<dl>
		<dt>美女：</dt>
		<dd>颜值很高的女性</dd>
		<dt>豆芽：</dt>
		<dd>好吃的豆芽</dd>
		<dt>前端开发工程师：</dt>
		<dd>一种致力于人类发展的伟大职业</dd>
	</dl>
	
### ⑨表格标签

	<table>
		<caption></caption> <!-- caption定义表格标题，非必须标签 -->
		<tbody>
			<tr>
				<th></th> <!-- 默认上下左右都居中 -->
				<td></td>
			</tr>
		</tbody>
	</table>
	
border-collapse：collapse;合并表格边框 separate;默认值
border-spacing:0px 0px;设置相邻单元格的边框间的距离；（第一个值表示左右，第二个值表示上下，可以为1个值，表示上下左右）

colspan 1 向右合并1格

rowspan 1 向下合并1格
vertical-align:top/middle/bottom;文本垂直方向 上/居中/下

text-align:left/center/right;文本方向 左/中/右

### ⑩一些其他标签

	<br/>换行 单标签，既不是块级，也不是行级
	<hr/>分隔线 单标签
	<i></i>强调
	<em></em>强调，突出内容，代替i标签
	<b></b>强调，突出内容（加粗）
	<strong></strong>强调，突出内容，代替b标签
	<sub></sub>下标字
	<sup></sup>上标字
	<del></del>定义删除字
	<code></code>
	<small></small>小字体
	<big></big>大字体
	<var></var>
	<object></object>   
	
text-indent 首行缩进：

text-indent:1em;(缩进一个字)2em;（缩进两个字）

font-size:1em;(字体大小也可以用em，也可以取小数1.88em)

font-size:1rem;
 
*em：根据它的父级或者自身来；

*rem：根据HTML来；

*百分比：根据继承他的父级来的；

以上综述：rem根据html、根目录节点来的，em、百分比、像素都是根据他的父级。

	sub{
		font-size:inherit;(默认继承父级)
		vertical-align:inherit;（默认）继承父级
	}

####一些默认字体样式：
	font-style:italic;字体倾斜； 

	font-style：normal;自然的、正常的字体
	   
	font-weight:bold;字体加粗

	font-weight:bolder;字体加粗（少用）

	font-weight:normal;字体恢复正常

	font-weight:lighter;          
	
	text-decoration:underline/line-through/overline/none;下划线/中划线/上划线/没线

font:font-weight、font-size/line-height、font-family;

	&nbsp; 空格
	&copy;  ©
	&lt;    <
	&gt;    >
	
### 未完待续，随时补充....☺