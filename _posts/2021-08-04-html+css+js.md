---
layout: post
title: HTML+CSS+JS
description: HTML+CSS+JS
category: 前端
photos:
link: http://www.google.com/
tags:
---
# 1 javaee java企业级开发

## 前端技术：
 

# 2 html概念

> **html的学习重点：html中有哪些标签  标签有哪些属性  属性有什么效果**

> html: hyper text markup language:超文本标记语言
>
> ​           超文本：比普通文本更强大：可以控制文本更多的效果 并且可以操作图片+视频+音乐等
>
> ​           标记：标签：<标签名   属性名=属性值  属性名=属性值  >数据</标签名>
>
> ​           原理：通过标签来封装数据  通过属性来控制数据的显示效果(样式)

> 案例1:创建一个文本文件 名字更改为myFirst.html 使用文本文档编辑  使用浏览器运行

~~~html
我叫<font  color="red"  size="7">苗天宝</font>
今年33岁
性别男
~~~

> html注意事项

~~~
1：html的源文件后缀名必须是.html或者是.htm
2：使用浏览器内置有html的解析程序 但 浏览器兼容性差 
3：html中所有的标签  及其标签中的属性是预定义的
4：标签类语言统一注释: <!-- 注释的内容 -->
5：html是描述性语言  没有编程能力
6：html语法：<标签名  属性名=属性值>数据</标签名>
           标签由起始标签 和 结束标签组成  起始标签中可以添加属性  
           属性格式：属性名=属性值  属性值可以写在单引号/双引号/不加引号  建议加双引号
7：html正规的文件应该由html标签作为根标签 根标签下有head和body子标签           
~~~

~~~html
<html>
   <head>
       <!--存放用于描述整个html文件属性的子标签-->
	   <title>我的第一个页面</title>
   </head>
   <body>
       <!--当前html要显示的所有数据-->
	   我叫<font  color="red"  size="7">苗天宝</font>
		<!--啊哈哈哈哈-->
		今年33岁
		性别男
   </body>
</html>
~~~

> 8:  html不区分大小写: html是非严谨性语言

> 9: 标签之间可以合理嵌套：外层的是父标签 里面的是子标签

~~~html
合理嵌套：<i><b>你好吗?</b></i>
~~~

> 10： 内部闭合标签：没有要封装的数据 效果比较单一  格式：<标签名 />
>
> ​         如  换行标签:br  水平线标签:hr

# 3 常用的标签

## 3.1 文本行标签:没有换行功能的文本标签

> font标签

~~~html
<!--font标签：属性size控制大小：值相对值(-2到+4) 绝对值(1到7)
             属性color控制颜色：英文单词、#6个16进制(三原色成分)-->
正常数据
<font color="red">font标签:color属性值：英文单词</font><br/>
<font color="#aa33ff">font标签:color属性值：#6个16进制 表示三原色红绿蓝作占的成分</font><br/>
<font size="1">font标签:size控制文字大小：值1到7  1</font><br/>
<font size="3">font标签:size控制文字大小：值1到7  3</font><br/>
<font size="7">font标签:size控制文字大小：值1到7  7</font><br/>
<font size="8">font标签:size控制文字大小：值1到7  8</font><br/>
<font size="-2">font标签:size控制文字大小：相对值-2到+4  -2</font><br/>
<font size="+1">font标签:size控制文字大小：相对值-2到+4  +1</font><br/>
<font size="+4">font标签:size控制文字大小：相对值-2到+4  +4</font><br/>
~~~

> 其他文本行标签

~~~html
<!--其他文本行标签-->
<b>b标签</b><br/>
<i>i标签</i><br/>
<u>u标签</u><br/>
<s>s标签</s><br/>
正常字体<sup>sup标签</sup>正常字体   2<sup>5</sup><br/>
正常字体<sub>sub标签</sub>正常字体   log<sub>5</sub>3<br/>
~~~



## 3.2 文本块标签：有换行功能的文本标签

~~~html
<!--文本块标签：有换行功能的文本标签-->
<!--hr:水平线标签
        属性：size:粗细            值:px
        width：长度          值:px 或者 %
        align: 水平对齐方式  值:left right center(默认)
        color: 颜色          值:英文单词 或者 #6个16进制
-->
		<hr size="10px" width="800px" align="left" color="red"/>
		<hr size="10px" width="50%"  align="center" color="#ff0000"/>
		<!--br:换行符-->
		<br/>
<!--p:段落标签：自带效果：换行功能+前后后空行
      属性:align:文本的水平对齐方式：值:left(默认) right center
-->
		正常文字
		<p align="center">p标签</p>
		正常文字
		<p align="right">p标签</p>
<!--hn:标题标签：n取值1到6:
    自带效果：1到6字体逐渐变小  加粗  换行  前后有空行
    属性:align:文本的水平对齐方式：值:left(默认) right center
-->
		正常文字
		<h1 align="center">h1标签</h1>
		<h2>h2标签</h2>
		<h3>h3标签</h3>
		<h4>h4标签</h4>
		<h5>h5标签</h5>
		<h6>h6标签</h6>
<!--pre标签：数据格式化标签：保留数据的原有格式-->
		class Student{
		   public static void main(String[] s){
		       System.out.println(111);
		   }
		}
		<pre>
		class Student{
		   public static void main(String[] s){
		       System.out.println(111);
		   }
		}
		</pre>
<!--center标签：居中标签-->
		222<center>eheh</center>111
~~~

## 3.3 超链接标签

~~~html
<!--超链接标签：a
    href:  如果a标签没有href属性 就没有链接效果
        绝对路径需要加协议：file:///  http:///
        相对路径(相对于当前资源所在目录):不需要协议 后退一步：../
    target: 打开资源的方式：
  		  值:_self（默认）	 在当前窗口打开新资源
   			 _block         在新窗口打开新资源	
			框架名
    name:设置锚点		  
-->
<a href="">a标签1</a><br/>
<a href="">a标签2</a><br/>
<a name="kt">开头锚点</a><br/>
<a href="">a标签</a><br/>
<a href="#">a标签</a><br/>
<a href="javascript:void(0);">a标签</a><br/>
<a href="file:///C:\Users\Administrator\Desktop\java34课堂记录\01_html\imgs\1.jpg">1.jpg</a><br/>
<a href="C:\Users\Administrator\Desktop\java34课堂记录\01_html\imgs\1.jpg">1.jpg</a><br/>
<a href="imgs\1.jpg">1.jpg</a><br/>
<a href="../2.jpg">2.jpg</a><br/>
<a href="../2.jpg" target="_self">2.jpg target="_self"</a><br/>
<a href="../2.jpg" target="_block">2.jpg target="_block"</a><br/>
<img src="imgs\1.jpg"/><br/>
<img src="imgs\2.jpg"/><br/>
<img src="imgs\3.jpg"/><br/>
<img src="imgs\4.jpg"/><br/>
<a href="#kt">回到name="kt"的锚点处</a><br/>
~~~

## 3.4 图片标签

~~~html
<!--图片标签：img
属性：   src  指定图片的路径(绝对路径+相对路径)
        width 设置图片的宽度：值:px 或者 %
        height 设置图片的高度:值:px 或者 %
        align  设置图片左右文本的对齐方式：值：bottom(默认) center top left right
        alt    图片说明文字: 当图片加载过程中/加载失败显示的文字
-->
<img src="imgs\4.jpg" width="1300px" height="300px"/><br/>
<br/>
正常文字
<img src="file:///C:\Users\Administrator\Desktop\java34课堂记录\01_html\imgs\41.jpg"
     width="50%" height="20%" align="right" alt="呵呵呵 看不到吧"/>
正常文字
~~~

## 3.5 列表标签

~~~html
       <h1>列表标签：让数据以列表的格式展示</h1>
	   <h2>有序列表:ol</h2>
	   <!--
	      ol    自带效果：块标签  前后有空行   列表项前有数字编号
	                属性 type:a  A  i  I  1(默认)
		  li        属性  value:整数   指定当前项从几开始			
	   -->
	   <ol type="a">
	       <li>列表项11</li>
		   <li value="6">列表项12</li>
		   <li type="1">列表项13</li>
		   <li>列表项14</li>
	   </ol>
	   正常文字
	   <h2>无序列表:ul</h2>
	   <!--
	      ul    自带效果：块标签  前后有空行   列表项有列表样式
	                属性 type: square  disc(默认)  circle
		  li        属性 type: square  disc  circle			
	   -->
	   <ul  type="square">
	      <li>无序列表11</li>
	      <li>无序列表12</li>
		  <li>无序列表13</li>
		  <li>无序列表14</li>
	   </ul>
	    <ul  type="circle">
	      <li>无序列表11</li>
	      <li>无序列表12</li>
		  <li>无序列表13</li>
		  <li>无序列表14</li>
	   </ul>
	    <ul  type="disc">
	      <li>无序列表11</li>
	      <li  type="square">无序列表12</li>
		  <li>无序列表13</li>
		  <li>无序列表14</li>
	   </ul>
~~~

## 3.6 表格标签

~~~html
      <h1>表格标签:让数据以表格的格式展示</h1>
	   <!--
	   table:表格标签的父标签
	      属性：width:宽度  值：px/%
		        height:高度  值：px/%
				border:边框粗细  值:px
				borderColor:边框颜色  值:英文单词/#6个16进制
				background:背景图片  值:图片路径
				bgColor:背景颜色  值:英文单词/#6个16进制
				align:表格水平对齐方式  值：left right center
				cellpadding:数据与边框之间的距离 内边距
				cellspacing:相邻边框之间的距离  外边距
	   caption:表格标题
		        align:标题水平对齐方式  值：left right center top bottom
	   tr:行标签
		        height:高度  值：px/%
				borderColor:边框颜色  值:英文单词/#6个16进制
				background:背景图片  值:图片路径
				bgColor:背景颜色  值:英文单词/#6个16进制
				align:本行数据的水平对齐方式  值：left right center
				valign:本行数据的垂直对齐方式  值：top middle bottom
	   td/th:单元格/列标题(加粗 居中)
	            width:宽度  值：px/%
		        height:高度  值：px/%
				borderColor:边框颜色  值:英文单词/#6个16进制
				background:背景图片  值:图片路径
				bgColor:背景颜色  值:英文单词/#6个16进制
				align:表格水平对齐方式  值：left right center
				colspan: 合并列  值：整数
				rowspan:合并行   值: 整数
	   -->
	   正常数据
	   <table width="1200px" height="300px" border="5px" 
	          borderColor="red" align="center"  
			  bgcolor="#aaaaaa" cellspacing="10px" cellpadding="20px" >
	       <caption align="bottom">学生成绩表</caption>
		   <tr height="100px"  borderColor="blue" align="left"  valign="top"  
		       bgcolor="#aaaaaa" >
		       <th>学号</th>
			   <th>姓名</th>
			   <th>性别</th>
			   <th>分数</th>
		   </tr>
		   <tr>
		       <td  width="300px" height="100px" bgcolor="#33aa33" background="imgs/1.jpg"
			        borderColor="#0000ff" align="right" 
			   >s001</td>
			   <td rowspan="2" colspan="3">张三</td>
		   </tr>
		   <tr>
		       <td>s002</td>
		   </tr>
		   <tr>
		       <td rowspan="2">s003</td>
			   <td>王五</td>
			   <td>女</td>
			   <td>80</td>
		   </tr>
		   <tr>
			   <td colspan="3">赵六</td>
		   </tr>
	   </table>
	   正常数据
~~~

## 3.7 表单标签

~~~html
<form action="day01_3.html" method="get">
		      姓名:<input type="text"   value="tom"/><br/>
			  密码:<input type="password"  name="pwd" value="123456"/><br/>
			  性别:男<input type="radio"  name="sex" value="nan" checked="checked"/>|
			       女<input type="radio"  name="sex" value="nv"/>
			  <br/>
			  省份:<select name="province" size="4" multiple="multiple">
			           <option value="hn">河南</option>
					   <option value="hb" selected="selected">河北</option>
					   <option value="tj">天津</option>
					   <option value="bj">北京</option>
					   <option value="yn">云南</option>
					   <option value="gd">广东</option>
			       </select><br/>
			  爱好:篮球<input type="checkbox" value="lq" name="enjoy"/>	|
 			      足球<input type="checkbox" value="zq" name="enjoy" checked="checked"/>	|
				  排球<input type="checkbox" value="pq" name="enjoy" checked="checked"/>	|
				  铅球<input type="checkbox" value="qq" name="enjoy"/><br/>
               隐藏的信息:<input type="hidden" value="1001" name="id"/>	<br/>
			  照片:<input type="file" name="photo"/><br/>
			  一个按钮:<input type="button" value="点我干啥"/><br/>
			  自我介绍:<textarea name="show" rows="4" cols="20"></textarea><br/>
			  <input type="reset" value="重置"/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
			  <input type="submit" value="提交"/><br/>
		</form>
~~~

## 3.8 框架标签

~~~
框架：   把多个页面展示在同一个窗口中 拼凑成一个页面
		      提高页面代码的复用性
		标签：frameset+frame	
		frameset标签：用于设置页面布局
		              不能有body标签
				属性：cols 对窗口左右拆分为列  值：百分比/整数
                      rows 对窗口上下拆分为行  值：百分比/整数
                      border: 边框粗细  值:px
                 					  
		frame标签：一个frame对应一个页面 一个页面对应一个窗体
		        属性： src：当前窗体要显示的页面的路径
				       noresize="noresize"：窗体大小不能更改
					   name：给窗体起个名字
~~~

main.html

~~~html
<html>
   <head>
       <!--存放用于描述整个html文件属性的子标签-->
	   <title>我的第五个页面</title>
   </head>
   <frameset  cols="30%,*" border="0px"><!--第一列占30% 第二列占剩下的全部-->
          <frame src="left.html" noresize="noresize"/>
		  <frameset rows="1,2" border="0px">
		       <frame  src="top.html" noresize="noresize"/>
			   <frame  src="bottom.html" noresize="noresize"  name="bottomframe"/>
		  </frameset>
   </frameset>
</html>
~~~

top.html

~~~html
<h1 align="center"><font color="red">我的淘宝<font></h1>
~~~

left.html

~~~html
<ul>
   <li><a  href="imgs/1.jpg" target="bottomframe">1.jpg</a></li>
   <li><a  href="imgs/2.jpg" target="bottomframe">2.jpg</a></li>
   <li><a  href="imgs/3.jpg" target="bottomframe">3.jpg</a></li>
   <li><a  href="imgs/4.jpg" target="bottomframe">4.jpg</a></li>
   <li><a  href="imgs/5.jpg" target="bottomframe">5.jpg</a></li>
</ul>
~~~

bottom.html

~~~html
我是展示数据的页面
~~~

> 效果

![image-20210308100058323](../../../AppData/Roaming/Typora/typora-user-images/image-20210308100058323.png)



## 3.9 字符实体

~~~ html
      <h1>字符实体：在html中通过字符实体来表示特殊字符</h1>
	   int a=1,b=3,c=4;<br/>
	   错误写法:特殊字符会被解析：a<b>c   c<a>b  "  a  '<br/>
	   正确写法:用字符实体来表示特殊字符:
           a&lt;b&gt;c&nbsp;&nbsp;&nbsp;&nbsp;c&lt;a&gt;b  "  a  '<br/>
	   <!--
	      字符实体格式：&xxx;
		  > 大于号     &gt;
		  < 小于号     &lt;
		    空格       &nbsp;
	   -->
~~~

# 1 css概念

~~~
css:cascading style sheets
	级联样式表
		 原理：把属性从标签中分离，html提供标签封装数据 css提供属性控制数据的样式
         优点：
               1  属性从标签中分离  便于样式的复用
               2  css提供更丰富的样式、样式更精准、兼容性强
               3  css可以实现页面元素的随意布局 
		 语法：属性名:属性值	
~~~

# 2 css与html结合的方式

~~~
css与html整合的方式：
 		1 行内样式：标签的style属性(id class style)对应的是css代码
            eg: <font style="color:#aaaaaa;font-size:40px;font-weight:bold;">font行内样式表</font>
          缺点：不能实现样式的复用
        2 内部样式表：通过head标签的style子标签
		    eg:<style type="text/css">
				 /*css的注释*/
				 /*内部样式表*/
				 #font_1{ /*选择器：当前样式要作用到那些/那个标签上*/
					   color:red;
					   font-size:40px;
					   font-family:隶书;
				 }
	           </style>
			缺点：不能在多个页面之间复用
        3 外部样式表：
		    3.1 通过head的link子标签
			   eg:<link href="css_1.css" rel="stylesheet" type="text/css"/>
			   href:指定要引入文件的路径
			   rel:指定要引入文件的作用
			   type:指定要引入文件的类型
			3.2 通过head的style子标签中@import
               eg: @import url("css_2.css");		
~~~

# 3 css选择器

~~~
css选择器：选择样式要作用到那些标签上
		  通配符选择器：匹配所有元素
		       格式： *{}
		  标签选择器：匹配指定的所有标签
		       格式：标签名{}
		  类选择器：匹配指定class值的所有标签
		       格式：.class值{}
		  id选择器：匹配指定id值的标签--(同一个html文件中id值不能重复)
		       格式：#id值{}
		  组合选择器：多个选择器使用一个样式
		       格式：选择器1,选择器2,选择器3...{}
		  派生选择器：选中指定父标签下的子标签
		       格式： 父选择器 子标签{}
		  伪类选择器：
		       :link   ---设置a标签未被访问前的样式
			   :hover  ---设置元素鼠标悬停时的样式   
			   :visited ---设置a标签已被访问过的样式
			   :active  ---设置对象(a和button)被激活瞬间的样式
			   :focus   ---设置对象(text\password\textarea)获取输入焦点时的样式
			   :first-letter ---设置第一个字符的样式
~~~

# 4 css常用的属性

~~~
/*大小*/
width:200px;
height:180px;
/*边框*/
border:1px solid blue;
border-width:3px;
border-top:5px double red;
border-bottom-color:#aaaaaa;
/*字体*/
font:italic small-caps bold 30px 楷体;
font-family:宋体;/*字体样式*/
font-size:30px;/*字体大小*/
font-weight:bold;/*字体加粗*/
color:red;/*字体颜色*/
text-decoration :  line-through ;/*划线*/
letter-spacing : 20px;/*字符间距*/
text-indent : 50px;/*首行缩进*/
word-break : break-all;/*边界内自动换行*/
text-align:center; 
/*背景*/
/*background : background-color || background-image || background-repeat || 
               background-attachment || background-position */
background-color:#cccccc;/*背景颜色*/
background-image:url("imgs/1.jpg");/*背景图片*/
background-image:url("bg.png");
background-repeat:no-repeat;/*平铺方式*/
background-repeat:repeat-y;
/*外边距:当前元素边框与相邻元素边框之间的距离*/
margin:20px;/*上下左右*/
margin:20px 40px;/*上下  左右*/
margin:20px 40px 60px 80px;/*上右下左*/
/*内边距:数据与边框之间的距离*/
padding:20px 40px 60px 80px;
/*表格相关属性*/
border-collapse :collapse ;/*合并相邻单元格之间的边框*/
~~~

# 5 css选择器优先级

~~~
css:级联样式表
    多个样式共同作用到一个元素上：属性不冲突 效果叠加
属性相同时：样式取决于选择器的优先级
         id > 类 > 标签 > 通配符
~~~

# 6 css浮动

~~~
实现布局方式一：浮动+外边距
		相关属性：float、clear
				当当前元素设置float属性 下一个元素必须设置float/clear属性
		float: left/right
		float:left  有两个效果：当前元素排在尽可能的左边
				    下一个元素要排在当前元素的右边
		clear: left/right/both;
		clear:both;消除上一个元素的float属性对当前元素的影响
~~~

> 练习代码

~~~html
<div  id="div_5" style="width:800px;height:500px;">
		       <img id="img_1" src="imgs/1.jpg"  style="float:left;" />
		       春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
			   春眠不觉晓，处处闻啼鸟。夜来风雨声，花落知多少！
</div>
~~~

> 练习效果

![image-20210309120731008](https://i.loli.net/2021/03/09/qS8nNhWKtvo5wcY.png)

 # 7 css定位

~~~
 实现布局方式二：定位
     position:absolute (绝对定位)/ relative (相对定位)
     left/right:
     top/bottom:

多个div的默认排序方式：每个div占一行 从上到下排序
---文档流

position:relative;相对定位
特点： 1 相当于元素在文档流中本来的位
      2 文档流中保留了当前元素的位置
position:absolute;绝对定位
特点： 1 文档流中不保留当前元素的位置
      2	如果父标签设置了position：那就相当于父标签
如果所有的父标签都没有设置position：相当于body	
~~~

> 练习代码

~~~html
 <div style="position:absolute; margin:200px;">
		     <img src="imgs/6.jpg"/>
			 <div  id="div_text" 
			     style="color:blue;font-size:60px;font-weight:bold;
				 letter-spacing:50px;width:480px;text-align:center;
				 position:absolute;top:300px; left:300px;
				 border:0px;">日出东方</div>
</div>
~~~

> 练习效果

![image-20210309121013394](https://i.loli.net/2021/03/09/CLFoIdaZxyEtpXW.png)

# 1 js概念

~~~
js:javascript；Jscript
		     基于对象和事件驱动的客户端脚本语言
	解释： 基于对象：js中所有的内容都是对象 其代码依赖浏览器的内置对象
          事件驱动：页面中可以执行的所有操作--事件
				 当某一事件发生时  和其关联的js程序就会执行
		  客户端：js写在html中 浏览器内置有解析html的程序和执行js代码的引擎
		  脚本语言：具有编程能力的实现页面动态效果的解释性语言
				 
     前端三剑客：html+css+js
              html提供标签封装数据
              css提供属性控制样式
               js 把标签封装为对象 实现页面数据和样式的动态效果
			
     js特点：
            安全性：不允许直接访问本地硬盘
            动态性：实现页面动态效果
            跨平台： 所有的浏览器内置有解析js代码的引擎  与操作系统无关
~~~

# 2 js与java的区别

~~~
java和js的区别
        都是编程类语言
不同之处：
        1 公司不同： java是sun公司的产品 被oracle收购
       	 js是netspace公司的产品
        2 js是基于对象 ：js中所有的内容都是对象  
       	 java是面向对象：设计细想  通过调用对象来解决问题
        3 js是弱类型语言：  变量的空间大小可以更改
       	 java是强类型语言：变量的空间大小不能更改  只能赋值相同类型的数据
        4 js是解释性语言：js代码通过编码表解释成字节  直接运行
         java是编译型语言：java源文件要被编译器编译成.class字节码文件 然后才能运行
~~~

# 3 js与html结合方式

~~~
js与html结合方式---script标签(任意位置)	
    方式1：内部js代码
    eg: <script type="text/javascript">
       		 alert("hello js!");//弹出框 
        </script>
    方式2：外部js文件
    eg: <script type="text/javascript"  src="js_1.js">
   			 //设置了src的srcipt标签中不能再写js代码
    		alert("11");
    	</script>
~~~

# 4 编程类语言的语法组成

~~~
所有编程类语言共同的内容：
        关键字：赋予特殊含义的单词/字符
        标示符：所有的名字  和同类区分 方便调用
        数据类型：对数据进行分类
        常量和变量：
        注释：对代码进行解释说明
        运算符：用于执行运算的符号
        流程控制：通过关键字对代码的执行流程进行控制
        数组：装多个数据的容器
        方法：对一个指定功能代码块的封装
        对象：功能和数据的封装
~~~

# 5 js的变量和数据类型

~~~ javaScript
/*变量：js是弱类型语言  定义变量时不用指定数据类型
		定义变量通过关键字 var  变量;
*/
		var a;//定义变量 variable
        a=1;a=true;a="1";
/*数据类型：判断数据的类型 通过方法typeof()
		  number类型：所有的数字
          string类型：字符串/字符  在js中双引号和单引号都表示字符串
		  boolean类型：true、false
		  object类型：所有的对象
		  undefined：唯一值undefined：：变量没有赋值	 
*/
		a=1;
//方法：typeof(n):判断参数数据的数据类型
		alert(a+"::::"+typeof(a));
//方法：document.write(s):把参数数据显示在页面
		document.write(a+"::::"+typeof(a)+"<br/>");
~~~

# 6 运算符

## 6.1 算术运算符

~~~ javascript
//算术运算符： + - *／　% ++ --
a=1;b=2;//0.5
document.write(a+"/"+b+"="+(a/b)+"<br/>");//0.5
a="1";b=2;
document.write(a+"+"+b+"="+(a+b)+"<br/>");//"12"
document.write(a+"-"+b+"="+(a-b)+"<br/>");//-1
document.write(a+"*"+b+"="+(a*b)+"<br/>");//2
~~~

~~~ javascript
//方法：parseInt(o) 把参数转换为整数
document.write(a+"+"+b+"="+(parseInt(a)+b)+"<br/>");
a="3.1";
//方法：parseFloat(o) 把参数转换为浮点
document.write(a+"+"+b+"="+(parseFloat(a)+b)+"<br/>");//5.1
~~~

> NaN

~~~ javascript
//常量：NaN:::not a number:当要进行数字运算时 结果不能得到一个数字
document.write((parseInt(a)+b)+"<br/>");//NaN
//注意：NaN比较不能用==  而是用方法isNaN(O);
document.write((parseInt("abc")==NaN)+"<br/>");//false
var bb=isNaN(parseInt("abc"));document.write(bb+"<br/>");//true
bb=isNaN(parseInt("1"));document.write(bb+"<br/>");//false
~~~

> 几个特殊的数据‘

~~~
//NaN：数据要转换为数字 但转换失败
//undefined：变量定义了 但没有赋值
//null:一个引用的地址栏存放的不是对象的地址 而是null 表示此引用没有指向任何对象
//""：字符串对象  字符序列是空的
//' '：字符串对象 有一个字符
~~~

## 6.2 比较运算符

~~~ javascript
//比较运算符： > >= < <= != ==
//注意：在js中所有的数据都可以作为boolean：
//      "",0,null,NaN,undefined作为boolean时是false
//      其他数据都是true
a=1;a=-1;a=" ";a=0;a="";a=NaN;a=null;a=undefined;
if(a){
    document.write(a+"  成立了<br/>");
}else{
    document.write(a+"  不成立了<br/>");
}
~~~

## 6.3 其他运算符

~~~ javascript
//赋值运算符：= += -= *= /= %=
//逻辑运算符：&& || ^  !
document.write((true ^ false)+"<br/>");
//位运算符:& | ^  >>> <<<  操作的是数据的二进制

//三元运算符：
document.write((1>2?3:4)+"<br/>");
~~~

# 7 流程控制

**和java基本一样**

> switch表达式的值类型可以是boolean和字符串

~~~ javascript
a=true;//switch表达式的值类型可以是boolean和字符串
switch(a){
    case true:
        //alert("true"); break;
    case false:
        //alert("false"); break;		   
}
~~~

> //循环结构：for while dowhile
> //while:先判断后执行
> //dowhile:先执行后判断  至少执行一次

~~~ javascript
//求质数
var n=19;
var b=true;//定义一个变量作为标签 记录n是否被除尽过
//使用循环 让一个变量m从2跑到n-1 循环判断是否可以除尽n
for(var m=2;m<=n/2;m++){
    if(n%m==0){ b=false;}
}
//循环完后 通过判断标签的值是否被更改 来判断n是否被除尽过 进而判断n是否为质数
if(b){
    document.write(n+"是质数<br/>");
}else{
    document.write(n+"不是质数<br/>");
}
~~~

~~~ javascript
//打印99乘法表
document.write("<table>");
for(var i=1;i<=9;i++){
    document.write("<tr>");
    for(var j=1;j<=i;j++){
        document.write("<td>"+i+"*"+j+"="+i*j+"</td>");
    }
    document.write("</tr>");
}
document.write("</table>");
~~~

# 8 方法

~~~
 方法--函数：具有指定功能的代码块
     意义：实现代码的复用性
     java方法格式：修饰符 返回值类型 方法名(参数列表){
                      实现方法具体功能的代码块
                      return 返回值;
                  }	 
     js方法格式： function 方法名(参数列表){
                     实现方法具体功能的代码块
                     return 返回值;
                 }
     js方法注意事项：
         1 js方法的参数列表不需要var  就是在定义变量
         2 var sum01=add01;//给方法add01又起个名字sum01
         3 一个页面的所有script标签是相通的
         4 方法外定义的变量--全局变量 作用域为整个页面
     		方法中(参数列表+方法体)定义的变量--局部变量 作用域为当前方法
         5 js方法调用时的实参个数和形参个数可以不一致
        	js方法体中默认有数组arguments 接受所有的实参
~~~

# 9 数组

~~~
数组：装多个数据的容器 
		  创建js数组：
		      方式1：通过[]
			         eg：var arr1=[1,2,3,4];
			  方式2：通过Array
			         eg: arr1=new Array();//创建一个空的数组
						 arr1=new Array(3);//创建一个数组 指定元素个数
						 arr1=new Array(3,1,2,4,5,7);//创建一个数组 指定元素的具体值
		  js和java数组的区别
              1 ：	js中数组的元素类型可以不同
              2 ：	js中数组的长度是可变  
              3 ：  js中数组不存在下标越界异常	
              4 :	js中数组中元素的默认值统一为undefined
        Arrays中的方法：
              //1 Array concat([item...]);把参数元素添加到当前数组后面 返回一个新的数组
		      //2 String join(char);通过参数字符拼接所有的元素 形成一个字符串
			  //3 pop();移除当前数组的最后一个元素 并返回此元素
			  //  shift();移除当前数组的第一个元素 并返回此元素
			  //4 int push([item...]); 把参数追加到当前数组后面 并返回新的元素个数
			  //5 Array reverse(); 元素反转 返回当前数组
			  //6 Array sort(); 元素排序  返回当前数组	
~~~

# 10 Date

~~~
Date对象:日期
		       和java中的java.util.Date完全相同
			构造方法：
			      date=new Date();//无参数 获取的是当前时间
		          date=new Date(1000);//参数是毫秒值   相当于历元：1970:1:1 0:0:0
		          date=new Date(2021,3-1,10,14,15,12);//参数是年月日时分秒：月0-11
		    普通方法：
			      1 int getXxx();void setXxx(int); 获取和设置时间参数
				  2 long getTime(); void setTime(long); Date与毫秒值之间的转换
				  3 String toLocaleString();获取本地系统对应的日期格式
~~~

~~~ javascript
//定义一个方法获取参数date对应的字符串  字符串格式如：1970-1-1 x 0:0:0
function getString(date){
		        var year=date.getFullYear();
				var month=date.getMonth()+1;//0到11
				var day=date.getDate();
				var week=date.getDay();
				var hour=date.getHours();
				var minute=date.getMinutes();
				var second=date.getSeconds();
				var weeks=["星期日","星期一","星期二","星期三","星期四","星期五","星期六"];
				var str=year+"-"+month+"-"+day+" "+weeks[week]+" "+
				        hour+":"+minute+":"+second;
				document.write(str+"<br/>");		
}
~~~

# 11 String

~~~
			String对象:字符串：
			创建字符串对象：
			   1 通过构造方法：var str=new String("1234");
			   2 通过双引号：var str="1234";
			普通方法：
               与java中String相同的方法：
			   1  char charAt(index);根据下标获取字符
			   2  String concat([string2[, string3....]]);把参数字符串拼接到当前字符串后 返回一个新的字符串
               3  int indexOf(subString[, startIndex]); 查找子串
			      int lastIndexOf(subString[, startIndex]); 倒着 查找子串
			   4  String replace(old, new) ; 把第一个old替换为new 返回一个新的字符串
			   5  String[] split(s);使用s切割当前字符串 获取一个字符串数组
			   6  String substr(start [, length ])；截取从start开始总共length个字符
			      String substring(start, end)；截取从start开始到end-1处的字符
			   7  String toLowerCase( ) ;所有字母转换为小写
                  String toUpperCase( )	;所有字母转换为大写		   
			特有方法：
               1 String bold();等价于<b>str</b>
 			   2 String fontcolor(colorVal);等价于<font color="val">str</font>
			   3 String fontsize(intSize);等价于<font size="val">str</font>
			   4 String italics( )
~~~

## 12 Math

~~~
Math:数学相关的属性和方法
			     是固有对象 无需创建对象
		    属性：PI/E
            方法：
                 1 绝对值： double abs(double)
                 2 近似值： double floor(double);小于等于参数的最大整数
                            double ceil(double);大于等于参数的最小整数
                            double round(double);四舍五入
				 3 幂运算： double sqrt(double);求参数的开方
                            double pow(a,b);求a的b次方
                 4 随机：   double random(); 随机一个[0,1)
~~~

# 13 Global

~~~
  一些方法不属于任意对象：统一的放在Global中
			 1 isNaN(N); 判断参数数据是不是NaN
			 2 parseInt(n);由参数数据获取一个整数
			 3 parseFloat(n);由参数数据获取一个浮点数据
			 4 eval(str);使用js引擎对str进行解析
~~~

# 14 正则(java)

~~~ java
         * 正则：正则表达式：正则规则
		 *     为字符串定义正确规则
		 * 使用正则两种方式：
		 *    1 通过Pattern类
		 *      //创建一个pattern对象
				Pattern pattern=Pattern.compile("1[356789][0-9]{9}");
				//获取匹配器对象 并关联要判断的字符串
				Matcher matcher=pattern.matcher(s);
				//调用匹配器对象的方法获取匹配结果
				return matcher.matches();  
			  2 通过字符串的方法
			    String pattern="1[356789][0-9]{9}";//[]表示范围  {}表示次数  []中的-表示到
		        return s.matches(pattern);   
		 * 通过一些特殊字符来指定规则：
		 *     x  表示任意字符 x
		 *     \\  表示\
		 *     
		 * 取值范围[]
		 *     [abc]  表示 a、b、c
		 *     [^abc] 表示 除了abc以外的所有字符
		 *     [a-d]  表示编码表中a到d的所有字符
		 *     [a-z[A-Z]] 表示[a-z]和 [A-Z]的并集
		 *     [a-z&&[a-f]] 表示[a-z]与[a-f]的交集
		 * 特殊字符
		 *     \d   表示所有的数字字符 [0-9]
		 *     \D   表示所有的非数字字符 [^0-9]
		 *     \s   表示所有的空白字符  ：[ \t\n\x0B\f\r]
		 *     \S   表示所有的非空白字符
		 *     \w   表示所有的单词字符
		 *     \W   表示所有的非单词字符
		 *     
		 *     ^    表示字符串的开头
		 *     $    表示字符串的结尾
		 * 次数{}
		 *     a?   表示a出现<=1次
		 *     a*   表示a出现>=0次
		 *     a+   表示a出现>=1次
		 *     a{n} 表示a出现==n次
		 *     a{n,} 表示a出现>=n次
		 *     a{n,m} 表示a出现>=n次 并且 <=m次
		 *         
		 * 组()
		 *    
		 * 字符串中可以使用正则的方法：
		 * 1   boolean matches(String regex) ：判断当前字符串是不是与参数正则匹配
		 * 2   String[] split(String regex) ： 使用一个正则规则来切割字符串
		 * 3   String replaceAll(String regex, String new)；用new替换当前字符串中所有匹配regex的子串
~~~

> 正则练习题

~~~ java
public static void testReplaceAll() {
    String s;
    s="12ab12uy34hjpo98hh7";
    //删除所有的非数字字符：把所有的非数字字符替换为空字符串
    s=s.replaceAll("[^0-9]+", "");
    System.out.println(s);

    //判断是否为叠词
    s="11111";
    String regex="(.)\\1+";//
    System.out.println(s.matches(regex));

    //"11123333"
    s="1111299999";//前后都是叠词 中间不是
    regex="(.)\\1+.(.)\\2+";
    System.out.println(s.matches(regex));

    //删除所有的叠词
    //111222333abc6661----abc1
    s="111222333abc6661";//使用空字符串替换叠词
    System.out.println(s.replaceAll("(.)\\1+", ""));

    //去除所有的叠词
    //111222333abc6661----123abc61
    s="111222333abc6661";
    System.out.println(s.replaceAll("(.)\\1+", "$1"));

    s="111222abcccdddd123333";
    //111222abcccdddd123333---21abdc123333
    System.out.println(s.replaceAll("(.)\\1+(.)\\2+", "$2$1"));

    s="我...我...叫.....苗....苗.....天..........宝.....宝.....宝";
    //删除所有的点
    s=s.replaceAll("\\.+", "");
    System.out.println(s);
    //去除所有的叠词
    s=s.replaceAll("(.)\\1+", "$1");
    System.out.println(s);
}
public static void testSplit() {
    String s;
    String[] arr;
    s="12ab12uy34hjpo98hh7";
    //使用数字切割
    arr=s.split("[0-9]+");
    System.out.println(Arrays.toString(arr));
    //使用.切割
    s="1.2.3.4.5.6..7.8.9";
    arr=s.split("\\.+");
    System.out.println(Arrays.toString(arr));
}

public static void testMatches() {
    String s;
    s="123.1";
    //判断一个字符串是不是数字：//"123"  //"123.1"
    String regex="[0-9]+\\.?[0-9]*";//
    System.out.println(s+":::"+s.matches(regex));
    s="1231.";
    System.out.println(s+":::"+s.matches(regex));
    //System.out.println(Integer.parseInt(s));
    System.out.println(Float.parseFloat(s));

    //判断是不是邮箱：miaotianbao@163.com
    regex="[0-9a-zA-Z_]+@[0-9a-zA-Z]+(\\.[a-z]+)+";
    s="miaotianbao@163.com";
    System.out.println(s+":::"+s.matches(regex));
    s="1@1.com";
    System.out.println(s+":::"+s.matches(regex));

    //判断一个用户名是否符合规则：由数字字母下划线组成  但只能以字母开头 必须包含_  长度6-9
    regex="[a-zA-Z][a-zA-Z0-9_]{5,8}";

    //判断是不是名字：2-4汉字：：：:[\u4e00-\u9fa5]//19968--40869
    System.out.println((char)19968);
    System.out.println((char)40869);
    regex="[一-龥]{2,4}";
    regex="[\u4e00-\u9fa5]{2,4}";
    s="韩寒";
    regex="\\w+";
    s="123abcABSD_";
    System.out.println(s+":::"+s.matches(regex));
    s="我...我...叫.....苗....苗.....天..........宝.....宝.....宝";
}
//写一个方法判断一个字符串是不是电话号码
public static boolean isPhone2(String s) {
    //判断s是否符合电话号的规则
    String pattern="1[356789][0-9]{9}";//[]表示范围  {}表示次数  []中的-表示到
    return s.matches(pattern);
}
public static boolean isPhone3(String s) {
    //创建一个pattern对象
    Pattern pattern=Pattern.compile("1[356789][0-9]{9}");
    //获取匹配器对象 并关联要判断的字符串
    Matcher matcher=pattern.matcher(s);
    //调用匹配器对象的方法获取匹配结果
    return matcher.matches();
}
//写一个方法判断一个字符串是不是电话号码
public static boolean isPhone1(String s) {
    //长度
    if(s.length()!=11) {return false;}
    //是不是纯数字
    try {
        long lon=Long.parseLong(s);
    }catch(NumberFormatException e) {
        return false;
    }
    //是不是判断：1 3 4 5 6 7 8 9 
    char char1=s.charAt(0);
    if(char1!='1') {
        return false;
    }
    char char2=s.charAt(1);
    return char2!='0'&&char2!='1'&&char2!='2'&&char2!='4';

}
~~~

> js中使用正则

~~~ javascript
/*
	js中的正则与java的正则基本相同
	不同之处：
		 1  创建方式不同
		 2  字符串是否匹配正则  通过正则的test方法
*/
var regex;
regex=new RegExp("[0-9]+");
regex=/^[0-9]+$/;
var b=regex.test("a1234");
document.write(b+"<br/>");
~~~

# 15内置对象

#### DHTML

~~~ javascript
 /*
			DHTML:动态的html   dynamic html
			      由三门语言和一门技术组成：
				  html:提供标签封装数据
				  css：提供属性控制样式
				  dom：把标签封装为对象
				  js：操作对象提供编程 实现页面动态效果
				  
			dom:document object model:文档对象模型
			    用于解析标签类语言文件  
				原理：把整个文档中所有的元素包括文档本身封装为对象 这些有关系的对象组成dom树
			
            内置对象：浏览器内置解析html的程序已经把html中所有元素封装为对象
                       不需要我们创建  直接使用
			*/
            			
			
~~~

#### window

~~~ javaScript
/*window:窗口对象：：：window对象名可以省略
            方法：对象具有的功能
                1：提示框
                     window.alert([sMessage])；只有一个确定按钮
					 bConfirmed = window.confirm( [sMessage])：有确定和取消按钮
					 vTextData = window.prompt( [sMessage] [, sDefaultValue])：可以获取客户的输入	     
			
					 window.alert("alert弹出框");
					 var b=window.confirm("confirm弹出框");
					 alert("b="+b);
					 var v=window.prompt("prompt弹出框：你的年龄？","18");
					 alert("v="+v);
			 
			    2： 窗口打开和关闭
				     oNewWindow = window.open( [sURL] [, sName] [, sFeatures] [, bReplace]);
                     [ bClosed = ] window.closed();
					 
				3： 窗口移动
        			window.moveTo(iX, iY)
					window.moveBy(iX, iY)
				
                4：延迟执行
                    iTimerID = window.setTimeout(vCode, iMilliSeconds [, sLanguage])
                    iTimerID = window.setInterval(vCode, iMilliSeconds [, sLanguage])
				    window.clearInterval(iIntervalID)
                    window.clearTimeout(iTimeoutID)
					
			 事件：
               	 1 onload :文档加载成功时
                 2 onunload: 文件卸载成功时				 
        
	 
		  */
~~~

#### history

~~~ javascript
history:

function testHistory(){
			    history.go(-1);//后退到上一个页面
			}
~~~

#### document

##### **常用的HTML DOM方法：**

​	getElementById(id)---	获取带有指定id的节点（元素）

​	appendChild(node)---	插入新的子节点（元素）

​	removeChild(node)---	删除子节点（元素）

##### **常用的HYML DOM属性：**

​	innerHTML---	节点（元素）的文本值

​	parentNode---	节点（元素）的父节点

​	childNode---	节点（元素）的子节点

​	attributes---	（元素）的属性节点.

| 方法                     | 描述                                                         |
| ------------------------ | ------------------------------------------------------------ |
| getElementById()         | 返回带有指定 ID 的元素。                                     |
| getElementsByTagName()   | 返回包含带有指定标签名称的所有元素的节点列表（集合/节点数组）。 |
| getElementsByClassName() | 返回包含带有指定类名的所有元素的节点列表。                   |
| appendChild()            | 把新的子节点添加到指定节点。                                 |
| removeChild()            | 删除子节点。                                                 |
| replaceChild()           | 替换子节点。                                                 |
| insertBefore()           | 在指定的子节点前面插入新的子节点。                           |
| createAttribute()        | 创建属性节点。                                               |
| createElement()          | 创建元素节点。                                               |
| createTextNode()         | 创建文本节点。                                               |
| getAttribute()           | 返回指定的属性值。                                           |
| setAttribute()           | 把指定属性设置或修改为指定的值。                             |



#### 事件

##### 1、onclick

点击事件：为button分配点击事件

~~~ javaScript
document.getElementById(myBtn).onclink=function(){displayDate()};
~~~

##### 2、onload

当用户进入页面时触发

##### 3、onunload

当用户离开页面时触发

##### 4.onchange

鼠标离开文本框，文本框内内容改变时触发

##### 5、onmouseover

鼠标放上去时触发

##### 6、onmouseout

鼠标离开触发

##### 7、onmousedown

鼠标按下不松一直触发

##### 8、onmouseup

鼠标松开触发



~~~ javascript
document:
 /*
			document:对整个html页面的封装  实现页面元素的增删改查
			*/
			//获取 id="div_1"
			var odiv=document.getElementById("div_1");
			//alert("1"+odiv);//文档从上到下执行//null
			
			window.onload=function(){//文档加载成功后
				//查询相关方法：
				//1 获取对象
				//oElement = document.getElementById(sIDValue):通过id获取一个标签
				//collObjects = document.getElementsByName(sNameValue):通过组件name获取集合
				//collObjects = object.getElementsByTagName(sTagName):通过标签名获取集合
			    //获取 id="div_1"
				var odiv=document.getElementById("div_1");
				//alert("3"+odiv);//[object HTMLDivElement]
				//获取name="uenjoy"
				var collEnjoy=document.getElementsByName("uenjoy");
				//alert(collEnjoy+":::"+collEnjoy.length);//[object NodeList]
				//获取所有的div
				var collDiv=document.getElementsByTagName("div");
				//alert(collDiv+":::"+collDiv.length);//[object HTMLCollection]:::4
				
				//2 获取设置标签的文本内容
				//属性： innerHTML 设置或获取标签中的html代码 
                //       innerText 设置或获取标签中的文本内容 
				//动态给按钮注册事件
				document.getElementById("but_1").onclick=function(){
				    odiv=document.getElementById("div_1");
				    alert("innerText:::"+odiv.innerText);//获取文本内容
					//odiv.innerText="<i>啊哈哈哈</i>";//设置文本内容
					
					alert("innerHTML:::"+odiv.innerHTML);
					odiv.innerHTML="<font color='red' size='7'>啊哈哈哈</font>";
				}
				
				//3 获取和设置属性：标签有什么属性 对象也必有什么属性
				var ofont=document.getElementsByTagName("font")[0];
				//alert(ofont.size+":::"+ofont.color);//获取属性
				ofont.size="7";//设置属性
				ofont.color="#aaaaaa";//获取属性
				ofont.className="cla_2";
				//alert(ofont.className);//获取class属性值
				//  通过方法获取和设置属性
				//  vAttrValue = object.getAttribute(sAttrName [, iFlags])
                //  object.setAttribute(sName, vValue [, iFlags])
				//alert(ofont.getAttribute("size"));
				ofont.setAttribute("color","yellow");
				//  获取所有属性：集合：attributes
				var collAttr=ofont.attributes;
				for(var i=0;i<collAttr.length;i++){
				    var oattr=collAttr[i];//Attribute:::有属性name和value
					//获取属性名和值
					//alert(oattr.name+"="+oattr.value);
				}
				
				//4 获取子标签集合/父标签
				// 通过属性获取父节点：parentElement、parentNode
                // 通过集合获取所有子节点：	childNodes、children	
                //获取div_0的父标签
                var odiv0=document.getElementById("div_0");
                //alert(odiv0.parentNode);
				var collZi=odiv0.children;
				for(var i=0;i<collZi.length;i++){
				   alert(collZi[i]);
				}
				
				
				//动态给but_3注册点击事件
				document.getElementById("but_3").onclick=setDivText;
			}
			//遍历整个document
			var str="";
			function setDivText(){
			       getAllElement(document);
				   //把str写到div_2中
				   document.getElementById("div_2").innerHTML=str.fontcolor("red").bold().fontsize(4);
			}
			function getAllElement(node){//所有对象都是node---document/attribute/text/element/comment
			      //alert(node+"::::"+node.nodeType);
				  //document--nodeType=9 element--nodeType=1   text---nodeType=3
				  if(node.nodeType==9){
				      str+=node+"是文档！<br/>";
					  var collZi =node.children;
					  for(var i=0;i<collZi.length;i++){
					      //递归
						  getAllElement(collZi[i]);
					  }
					  return;
				  }
				  if(node.nodeType==3){
				      str+=node+"是文本！ nodeValue="+node.nodeValue+"<br/>";
					  return;
				  }
				  if(node.nodeType==1){
				      var element=node;
				      str+=element+"是标签! 标签名="+element.nodeName+"<br/>";
					  //获取属性
					  var collAttr=element.attributes;
					  for(var i=0;i<collAttr.length;i++){
					      str+=element.nodeName+"的属性："+collAttr[i].name+"="+collAttr[i].value+"<br/>";
					  }
					  //获取所有的子节点
					  var collZi=element.children;
					  if(collZi==null||collZi.length==0){
					       //获取其文本内容
						   if(element.innerText!=null&&element.innerText.length!=0){
						      str+=element.nodeName+"的文本："+element.innerText+"<br/>";
						   }
					  }
					  for(var i=0;collZi!=null&&i<collZi.length;i++ ){
					       getAllElement(collZi[i]);
					  }
					  return;
				  }
			}
			
 /*
			document:对整个html页面的封装  实现页面元素的增删改
			添加：
			添加标签：
			    document的方法： oElement = document.createElement(sTag)
				element的方法：oElement = object.appendChild(oNode)
            添加文本内容：
				属性：innerText
			添加属性：
                方法：object.setAttribute(sName, vValue )
				
				
			修改：
            修改属性值：
                object.setAttribute(sName, vValue )
            修改文本内容：
          		属性：innerText

            删除：
            删除属性：		
			    object.setAttribute(sName,null)
			删除文本内容：
                innerText="";
            删除值标签：
                oRemove = object.removeChild(oNode)
			*/
			//文档加载成功 给but_3注册事件
			window.onload=function(){
			   document.getElementById("but_3").onclick=testAdd;
			   document.getElementById("but_4").onclick=testDelete;
			}
			function testDelete(){
			     //删除font_2的size属性
				 //document.getElementById("font_2").setAttribute("size",null);
				 //删除font_2的color属性
				 document.getElementById("font_2").size="3";
				 document.getElementById("font_2").color="bule";
				 
				 //获取a_1标签
				 var oa_1=document.getElementById("a_1");
				 //删除font_2中的a_1;
				 var  oo=document.getElementById("font_2").removeChild(oa_1);
				 alert(oo.nodeName);
			}
			function testAdd(){
			       //在<div id="div_2"></div>中添加一个button按钮
				   //创建input
				   var obut=document.createElement("input");
				   //设置属性
				   obut.type="button"; obut.value="我是添加的按钮";
				   obut.onclick=function(){
				      alert("点我干啥?");
				   }
				   //把创建的按钮添加到div中
				   document.getElementById("div_2").innerHTML="";//清空div中的所有代码
				   //document.getElementById("div_2").appendChild(obut);
				   
				   document.getElementById("div_2").innerHTML="<input type='button' value='点我'        	onclick='hehe();' />";
			
			}
			function hehe(){
			   alert("点我干啥？");
			}

~~~

## javascript练习

**99乘法表**

~~~ javascript
<html>
   <head>
       <title>js作业</title>
	   <meta charset="UTF-8"/>
	   <style  type="text/css">
	        table{
			   width:800px;
			   font-size:22px;
			   border-collapse:collapse;
			   margin:10px auto;
			}
			table td{
			   border:2px solid blue;
			   padding:5px;
			}
	   </style>
	   
	   
   </head>
   <script  type="text/javascript">
	      document.write("<h1>打印99乘法表1</h1>");
		  document.write("<table>");
		  for(var i=1;i<=9;i++){
		       document.write("<tr>");
			   for(var j=1;j<=i;j++){
			       document.write("<td>"+i+"*"+j+"="+i*j+"</td>");
			   }
			   document.write("</tr>");
		  }
		  document.write("</table>");
	</script>
	 <script  type="text/javascript">
	      document.write("<h1>打印99乘法表2</h1>");
		  document.write("<table>");
		  for(var i=9;i>=1;i--){
		       document.write("<tr>");
			   for(var j=1;j<=i;j++){
			       document.write("<td>"+i+"*"+j+"="+i*j+"</td>");
			   }
			   document.write("</tr>");
		  }
		  document.write("</table>");
	</script>
	
	<script  type="text/javascript">
	      document.write("<h1>打印99乘法表3</h1>");
		  document.write("<table>");
		  for(var i=1;i<=9;i++){
		       document.write("<tr>");
			   for(var j=9;j>=1;j--){
			       if(i>=j){
				      document.write("<td>"+i+"*"+j+"="+i*j+"</td>");
				   }else{
				      document.write("<td> </td>");
				   }
			   }
			   document.write("</tr>");
		  }
		  document.write("</table>");
	</script>
	
	<script  type="text/javascript">
	      document.write("<h1>打印99乘法表4</h1>");
		  document.write("<table>");
		  for(var i=1;i<=9;i++){
		       document.write("<tr>");
			   for(var j=1;j<=9;j++){
			       if(j>=i){
				      document.write("<td>"+i+"*"+j+"="+i*j+"</td>");
				   }else{
				      document.write("<td> </td>");
				   }
			   }
			   document.write("</tr>");
		  }
		  document.write("</table>");
	</script>
	
	
   <body >
     
   </body>
</html>
~~~

**获取1到10000中所有位数上含有1的质数**

~~~ javascript
<script  type="text/javascript">
	      document.write("<h1>获取1到10000中所有位数上含有1的质数</h1>");
		  for(var n=1;n<=10000;n++){
		      //判断是否含有1
			  var a=n%10;
			  var b=parseInt(n/10)%10;
			  var c=parseInt(n/100)%10;
			  var d=parseInt(n/1000)%10;
			  var e=parseInt(n/10000)%10;
			  if((a-1)*(b-1)*(c-1)*(d-1)*(e-1)==0){
			      //判断是不是质数
				  var bb=true;
				  for(var m=2;m<=n/2;m++){
				     if(n%m==0){
					     bb=false;break;
					 }
				  }
				  if(n!=1&&bb){
				     document.write(n+"<br/>");
				  }
			  }
		  }
	</script>
~~~

**冒泡排序**

~~~ javascript
//1 创建数组排序
		   var arr=[1,5,9,0,2,3,4,1,2,3];
		   function mySort(arr1){
		           //冒泡排序
				   for(var i=0;i<arr1.length-1;i++){
				      for(var j=0;j<arr1.length-1-i;j++){
					       if(arr1[j]>arr1[j+1]){
						        var k=arr1[j];
								arr1[j]=arr1[j+1];
								arr1[j+1]=k;
						   }
					  }
				   }
				   document.write("冒泡排序："+arr1+"<br/>");
~~~

**顺序排序**

~~~ javascript
 //顺序排序
				   for(var i=0;i<arr1.length-1;i++){
				      for(var j=i+1;j<arr1.length;j++){
					       if(arr1[i]<arr1[j]){
						        var k=arr1[j];
								arr1[j]=arr1[i];
								arr1[i]=k;
						   }
					  }
				   }
				   document.write("顺序排序："+arr1+"<br/>");
~~~

**插入排序**

~~~ javascript
//插入排序
				   for(var i=1;i<arr1.length;i++){
				       var k=arr1[i];//定义变量记录当前元素的值
					   var j;
					   for(j=i-1;j>=0;j--){
					       if(arr1[j]>k){
						       arr1[j+1]=arr1[j];
						   }else{
						       break;
						   }
					   }
					   arr1[j+1]=k;
				   }
				   document.write("插入排序："+arr1+"<br/>");
~~~

**获取平均值**

~~~ java
//获取平均值
		   function getPJZ(arr1){
		      var sum=0;
			  for(var i=0;i<arr1.length;i++){
			     sum+=arr1[i];
			  }
			  return sum/arr1.length;
		   }
		   document.write(arr+"平均值="+getPJZ(arr)+"<br/>");
~~~

**删除数组中小于平均值的元素**

~~~ javascript
//删除数组中比平均值小的元素
		   function deleteSome(){
			   var array=[1,5,9,0,2,3,4,1,2,3];
			   document.write("移除前："+array+"<br/>");
			   var pjz=getPJZ(array);
			   for(var i=0;i<array.length;i++){
				  if(array[i]<pjz){
				      array.splice(i,1);
					  i--;
				  }
			   }
			   document.write("移除后："+array+"<br/>");
		   }
		   deleteSome();

~~~

**打鱼晒网**

~~~ javascript
// 写一个方法获取从2000-1-1开始三天打渔两天晒网 到 参数字符串表示的日期是在打渔还是晒网
		   //参数字符串格式是xxxx年xx月xx号
		   function pdDaYuShaiWang(str){
		        //截取字符串str获取year month day
				var indexYear=str.indexOf("年");
				var indexMonth=str.indexOf("月");
				var indexDay=str.indexOf("号");
				var year=parseInt(str.substring(0,indexYear));
				var month=parseInt(str.substring(indexYear+1,indexMonth));
				var day=parseInt(str.substring(indexMonth+1,indexDay));
				// 把年月日封装为date对象
				var date=new Date(year,month-1,day);
				var startDate=new Date(2000,1-1,1);
				//获取毫秒值之差：
				var cha=date.getTime()-startDate.getTime();
				var days=cha/1000/60/60/24;
				var yuShu=days%5;
				if(yuShu<3){
				   document.write(str+"正在打渔！<br/>");
				}else{
				   document.write(str+"正在晒网！<br/>");
				}
		   }
		   for(var i=1;i<=100;i++){
		       //pdDaYuShaiWang("2000年1月"+i+"号");
		   }
~~~

**四舍五入** 

~~~ javaScript
//7  写一个方法function siSheWuRu(d,n);获取浮点类型数据d四舍五入保留n位小数的值
           function siSheWuRu(d,n){
		          //123.45678---2
				  //12345
				  var k=d;
				  var c=Math.pow(10,n);
				  k=parseInt(k*c);
				  //0.00678
				  var yuShu=n%(1/c);
				  //大于0.005就+1 否则不加1
				  k+=yuShu>=(1/c/2)?1:0;
				  //12346-123.46
				  k=k/c;
				  document.write(d+":::"+k+"<br/>");
		   }
		   siSheWuRu(123.456789,3);
~~~

**统计字符串中字符出现的次数**

~~~ javascript
//8  写一个方法function getCiShu(str);打印字符串str中每个字符出现的次数
		   function getCiShu(str){
		       //获取str中所有但不重复的字符串
			   var ss="";
			   for(var i=0;i<str.length;i++){
			       var c=str.charAt(i);
				   if(ss.indexOf(c)==-1){
				       ss+=c;
				   } 
			   }
			   //遍历ss 获取所有字符
			   for(var i=0;i<ss.length;i++){
			       var c=ss.charAt(i);
				   var count=0;
				   for(var j=0;j<str.length;j++){
				       var cc=str.charAt(j);
					   if(cc==c){
					       count++;
					   }
				   } 
				   document.write(str+"中字符"+c+"出现的次数是"+count+"<br/>");
			   }
		   }
		   getCiShu("aaabbbsssababc");
~~~

**获取str中所有数字字符组成的最大整数**

~~~ javascript
//写一个方法function getInt(str)；获取str中所有数字字符组成的最大整数：如”abc123kjh98”---98321
		   function getInt(str){
		         var strNew=str;
		         var ss;
				 while(true){
				    ss=strNew.replace(/[^0-9]+/,"");
					document.write(ss+":::"+strNew+"<br/>");
					strNew=ss;
					//if(ss==str){
					if(/^[0-9]+$/.test(ss)){
					   break;
					}
				 }
				 //把ss转换为最大的整数
				 var arr=[];
				 for(var i=0;i<strNew.length;i++){
				     var c=parseInt(strNew.charAt(i));
					 arr.push(c);
				 }
				 //对数组排序
				 arr.sort();
				 arr.reverse();
				 var result=parseInt(arr.join(""));
				 document.write(str+"最大的整数："+result+"<br/>");
				 
		   }
		   getInt("abc123kjh98");
~~~

**获取斐波那契数列第n个数字的值**

~~~ javascript
 //10 写一个方法function getFBNQ(n); 获取斐波那契数列第n个数字的值：1 1 2 3 5 8 13 21 34…..
		   function getFBNQ(n){
				  if(n==1||n==2){
				     return 1;
				  }
				  return getFBNQ(n-1)+getFBNQ(n-2);
		   }
		   function getFBNQ2(n){
		          var a=1,b=1;
				  if(n==1||n==2){
				         return 1;
				  }
				  for(var i=3;i<=n;i++){
				      var c=b;
					  b=c+a;
					  a=c;
				  }
				  return b;
		   }
		   for(var i=1;i<20;i++){
		       document.write(getFBNQ2(i)+"&nbsp;");
		   }
		   document.write("<br/>");
~~~

**删除s中所有的汉字 所有的叠词替换为一个 并且大写转换为小写 小写转换为**大写

~~~ javascript
 //11 写一个方法 function change(s);  删除s中所有的汉字 所有的叠词替换为一个 并且大写转换为小写 小写转换为大写
           //如：”123ABCabc你好111222”--”123abcABC12”
		   function change(s){
		        //去除所有的叠词
				var sNew=s.replace(/(.)\1+/g,"$1");
				//删除所有的汉字
				sNew=sNew.replace(/[\u4e00-\u9fa5]+/g,"");
				var ss="";
				for(var i=0;i<sNew.length;i++){
				    var c=sNew.charAt(i);
					if(/^[a-z]$/.test(c)){
					    c=c.toUpperCase();
					}else if(/^[A-Z]$/.test(c)){
					    c=c.toLowerCase();
					}
					ss+=c;
				}
				document.write(ss+"::::"+s+"<br/>");
		   }
		   change("1111aaas呵呵呵b98888呵呵呵AAAAHHH");
~~~

## 表格操作

方式一：

~~~ javaScript
<html>
   <head>
       <title>表格操作</title>
	   <meta charset="UTF-8"/>
	  
	   <style  type="text/css">
	        table{
			    border:1px solid blue;
				width:800px;
				border-collapse:collapse;
				margin:10px 240px;
			}
			table td{
			    border:1px solid blue;
				padding:10px;
			}
			
			.cla_1{
			   background-color:#cccccc;
			}
			.cla_2{
			   background-color:#99cccc;
			}
			.cla_3{
			   background-color:#cc99cc;
			}
	   </style>
	   <script  type="text/javascript">
	          var odiv,trClassName;
	          window.onload=function(){
			      odiv= document.getElementById("div_1");
			      //给but_create注册事件
				  document.getElementById("but_create").onclick=function(){
				       createTable();
				  };
				  //给delete_hang注册事件
				  document.getElementById("delete_hang").onclick=function(){
				       deleteHang();
				  };
				  //给delete_lie注册事件
				  document.getElementById("delete_lie").onclick=function(){
				       deleteLie();
				  };
			  }
			  //删除列
			  function deleteLie(){
			        //获取表格
			        var otab=document.getElementById("tab");
					if(!otab){
					   alert("要删除的表格不存在!");return;
					}
					//获取所有的行tr
					var colltr=otab.getElementsByTagName("tr");
					//获取第一个tr下的所有td
					var colltd=colltr[0].getElementsByTagName("td");
					//获取deleteLieText的值
					var lie=parseInt(document.getElementsByName("deleteLieText")[0].value);
					if(!lie||lie>colltd.length){
					   alert("要删除的列数"+lie+"不合理!");return;
					}
					//删除列
					//遍历行
					for(var i=0;i<colltr.length;i++){
					     //获取当前行下的所有td
					     colltd=colltr[i].getElementsByTagName("td");
						 //删除列
						 colltr[i].removeChild(colltd[lie-1]);
					}
					setColor();
			  }
			  //删除行
			  function deleteHang(){
			        //获取表格
			        var otab=document.getElementById("tab");
					if(!otab){
					   alert("要删除的表格不存在!");return;
					}
					//获取所有的行tr
					var colltr=otab.getElementsByTagName("tr");
					//获取deleteHangText的值
					var hang=parseInt(document.getElementsByName("deleteHangText")[0].value);
					if(!hang||hang>colltr.length){
					   alert("要删除的行数"+hang+"不合理!");return;
					}
					//删除行
					colltr[hang-1].parentNode.removeChild(colltr[hang-1]);
			  }
			  //创建表格
			  function createTable(){
			         var hang=document.getElementsByName("createHang")[0].value;
					 var lie=document.getElementsByName("createLie")[0].value;
					 hang=parseInt(hang);
					 lie=parseInt(lie);
					 if(!hang||!lie){
					     alert("行数或者列数不合理！");return;
					 }
					 //创建表格
					 var otab=document.createElement("table");
					 var otbody=document.createElement("tbody");
					 otab.id="tab";
					 for(var i=1;i<=hang;i++){
					     var otr=document.createElement("tr");
						 for(var j=1;j<=lie;j++){
						     var otd=document.createElement("td");
							 otd.innerText=i+":"+j;
							 otr.appendChild(otd);//把td添加到tr下
						 }
						 //给tr添加鼠标悬停事件
						 otr.onmouseover=function(){
						     trClassName=this.className;//记录当前tr的当前classname值
							 this.className="cla_3";
						 }
						 //给td添加鼠标移出事件
						 otr.onmouseout=function(){
						     this.className=trClassName;
						 }
						 
						 otbody.appendChild(otr);//把tr添加到table下
					 }
					 otab.appendChild(otbody);
					odiv.innerHTML="";//清空div中所有的html代码
					odiv.appendChild(otab);//把table添加到div下
					setColor();//实现各行变色
			  }
			  //实现各行变色
			  function setColor(){
			        //获取表格
			        var otab=document.getElementById("tab");
					//获取所有的tr
					var colltr=otab.getElementsByTagName("tr");
					for(var i=0;i<colltr.length;i++){
					     //设置tr的clas 值
					     colltr[i].className=(i%2==0)?"cla_1":"cla_2";
					}
			  }
	   </script>
   </head>
   <body >
       <div  id="div_1">
	        <p><font></font></p>
	   </div>
       <h1>创建表格</h1>
       行数:<input   type="text" name="createHang"/><br/>
	   列数:<input   type="text" name="createLie"/>
	   <input  type="button"   value="创建表格"  id="but_create"/><br/>
	   <h1>删除表格</h1>
	   行号：<input    type="text" name="deleteHangText"/>
	   <input  type="button"   value="删除行"  id="delete_hang"/><br/>
	   列号：<input   type="text" name="deleteLieText"/>
	   <input  type="button"   value="删除列"  id="delete_lie"/><br/>
     
   </body>
</html>
~~~

**方式二**

~~~ javascript
<html>
   <head>
       <title>表格操作2</title>
	   <meta charset="UTF-8"/>
	  
	   <style  type="text/css">
	        table{
			    border:1px solid blue;
				width:800px;
				border-collapse:collapse;
				margin:10px 240px;
			}
			table td{
			    border:1px solid blue;
				padding:10px;
			}
			
			.cla_1{
			   background-color:#cccccc;
			}
			.cla_2{
			   background-color:#99cccc;
			}
			.cla_3{
			   background-color:#cc99cc;
			}
	   </style>
	   <script  type="text/javascript">
	          var odiv,trClassName;
	          window.onload=function(){
			      odiv= document.getElementById("div_1");
			      //给but_create注册事件
				  document.getElementById("but_create").onclick=function(){
				       createTable();
				  };
				  //给delete_hang注册事件
				  document.getElementById("delete_hang").onclick=function(){
				       deleteHang();
				  };
				  //给delete_lie注册事件
				  document.getElementById("delete_lie").onclick=function(){
				       deleteLie();
				  };
			  }
			  //删除列
			  function deleteLie(){
			        //获取表格
			        var otab=document.getElementById("tab");
					if(!otab){
					   alert("要删除的表格不存在!");return;
					}
					//获取deleteLieText的值
					var lie=parseInt(document.getElementsByName("deleteLieText")[0].value);
					if(!lie||lie>otab.rows[0].cells.length){
					   alert("要删除的列数"+lie+"不合理!");return;
					}
					//删除列
					//遍历行
					for(var i=0;i<otab.rows.length;i++){
					     //tr的特有方法：TR.deleteCell( [iIndex])
					     otab.rows[i].deleteCell(lie-1);
					}
					setColor();
			  }
			  //删除行
			  function deleteHang(){
			        //获取表格
			        var otab=document.getElementById("tab");
					if(!otab){
					   alert("要删除的表格不存在!");return;
					}
					//获取deleteHangText的值
					var hang=parseInt(document.getElementsByName("deleteHangText")[0].value);
					//通过table的集合对象rows获取所有的行集合
					if(!hang||hang>otab.rows.length){
					   alert("要删除的行数"+hang+"不合理!");return;
					}
					//删除行 通过table的特有方法 object.deleteRow( [iRowIndex])
					otab.deleteRow(hang-1);
			  }
			  //创建表格
			  function createTable(){
			         var hang=document.getElementsByName("createHang")[0].value;
					 var lie=document.getElementsByName("createLie")[0].value;
					 hang=parseInt(hang);
					 lie=parseInt(lie);
					 if(!hang||!lie){
					     alert("行数或者列数不合理！");return;
					 }
					 //创建表格
					 //table的特有方法：oTR = object.insertRow([iIndex])
					 //tr   的特有方法：oTD = TR.insertCell( [iIndex])
					var otab=document.createElement("table");
					otab.id="tab";
					for(var i=1;i<=hang;i++){
					     var otr=otab.insertRow();//创建行
						 for(var j=1;j<=lie;j++){
						     var otd=otr.insertCell();//创建单元格
							 otd.innerText=i+":"+j;
						 }
						 //给tr添加鼠标悬停事件
						 otr.onmouseover=function(){
						     trClassName=this.className;//记录当前tr的当前classname值
							 this.className="cla_3";
						 }
						 //给td添加鼠标移出事件
						 otr.onmouseout=function(){
						     this.className=trClassName;
						 }
					}
					 odiv.innerHTML="";//清空div中所有的html代码
					 odiv.appendChild(otab);//把table添加到div下
					 setColor();//实现各行变色
			  }
			  //实现各行变色
			  function setColor(){
			        //获取表格
			        var otab=document.getElementById("tab");
					//获取所有的tr
					var colltr=otab.getElementsByTagName("tr");
					for(var i=0;i<colltr.length;i++){
					     //设置tr的clas 值
					     colltr[i].className=(i%2==0)?"cla_1":"cla_2";
					}
			  }
	   </script>
   </head>
   <body >
       <div  id="div_1">
	        <p><font></font></p>
	   </div>
       <h1>创建表格</h1>
       行数:<input  type="text" name="createHang"/><br/>
	   列数:<input   type="text" name="createLie"/>
	   <input  type="button"   value="创建表格"  id="but_create"/><br/>
	   <h1>删除表格</h1>
	   行号：<input   type="text" name="deleteHangText"/>
	   <input  type="button"   value="删除行"  id="delete_hang"/><br/>
	   列号：<input  type="text" name="deleteLieText"/>
	   <input  type="button"   value="删除列"  id="delete_lie"/><br/>
     
   </body>
</html>
~~~

**计算器**

~~~ javascript
<html>
   <head>
       <title>计算器</title>
	   <meta charset="UTF-8"/>
	  
	   <style  type="text/css">
	        div{
			   border:2px solid blue;
			   padding:10px;
			}
	        #div_0{
			   width:800px;
			   height:400px;
			   margin:50px auto;
			}
			#div_top{
			   width:400px; 
			   height:100px;
			   margin:10px auto;
			   text-align:center;
			}
			#div_left{
			   width:420px; 
			   height:220px;
			   float:left;
			   padding:10px;
			}
			#div_right{
			   width:320px; 
			   height:220px;
			   float:right;
			}
			#div_top span{
			   display:block;/*把行标签转换为块标签   inline--相反*/
			   font-size:45px;
			   font-weight:bold;
			   color:blue;
			   letter-spacing:20px;
			   text-align:center;
			}
			#div_top input{
			    font-size:22px;
			}
			#div_left input{
			    font-size:42px;
				width:60px;
				height:50px;
				margin:24px 10px;
			}
			#div_right input{
			    font-size:48px;
				width:60px;
				height:60px;
				margin:24px 19px;
			}
	   </style>
	   
   </head>
   <script  type="text/javascript">
        //定义全局变量记录两个运算的数字和运算符
		var num1="",num2="",ysf="";
        //文档加载成功
		window.onload=function(){
		    addButton();
		}
		
		function addButton(){
		    //1 给div_left中添加按钮 0-9
		    var odiv=document.getElementById("div_left");
			for(var i=0;i<=9;i++){
			     var obut=document.createElement("input");//创建button
				 obut.type="button";
				 obut.value=i;
				 obut.onclick=setNum;
				 odiv.appendChild(obut);
			}
			//2 给div_right中添加按钮 0-9
			var arr=['+','-','×','÷','.','='];
			var odiv2=document.getElementById("div_right");
			for(var i=0;i<arr.length;i++){
			     var obut=document.createElement("input");//创建button
				 obut.type="button";
				 obut.value=arr[i];
				 if(arr[i]=="="){
				     obut.onclick=getResult;
				 }else  if(arr[i]=="."){
				     obut.onclick=setDian;
				 }else {
				     obut.onclick=setYSF;
				 }
				 odiv2.appendChild(obut);
			}
		}
		//设置数字的方法
		function setNum(){
		     var v=this.value;
			 //如果运算符有值  v加到num2上  如果没值 v加到num1上
			 if(ysf){
			       num2+=""+v;
			 }else{
			       num1+=""+v;
			 }
			 setTextInput();
		}
		//设置运算符
		function setYSF(){
		     if(!ysf){
			     ysf=this.value;
			 }else{
			    alert("运算符只能赋值一次");
			 }  
			 setTextInput();
		}
		//获取结果
		function getResult(){
		      if(!num2){
			      alert("数据不完整 不能计算！");return;
			  } 
			  var result;
			  switch(ysf){
			     case "+":
				    result=parseFloat(num1)+parseFloat(num2);
					break;
				case "-":
				    result=parseFloat(num1)-parseFloat(num2);
					break;
				case "×":
				    result=parseFloat(num1)*parseFloat(num2);
					break;
				case "÷":
				    result=parseFloat(num1)/parseFloat(num2);
					break;
			  }
			  document.getElementById("input_text").value=num1+ysf+num2+"="+result;
			  num1="";num2="";ysf="";
			  
		}
		//设置点
		function setDian(){
		     if(ysf){
			       if(num2.indexOf(".")!=-1){
				        alert("一个数字只能有一个小数点！");return;
				   }
			       num2+=".";
			 }else{
			       if(num1.indexOf(".")!=-1){
				        alert("一个数字只能有一个小数点！");return;
				   }
			       num1+=".";
			 }
			 setTextInput();
		}
		
	    //给input_text设置内容
		function setTextInput(){
		    document.getElementById("input_text").value=num1+""+ysf+""+num2;
		}
		
		//清空
		function textClear(){
		    document.getElementById("input_text").value="";
			num1="";num2="";ysf="";
		}
      
   </script>
   
   <body >
         <div  id="div_0">
		      <div  id="div_top">
			      <span> 计算器</span>
				  <input type="text" id="input_text"  disabled="disabled"/>
				  <input type="button" value="清空" onclick="textClear();" style="color:red;"/>
			  </div>
			  <div  id="div_left">
			       
			  </div>
			  <div  id="div_right">
			     
			  </div>
		 </div>
   </body>
</html>
~~~

## 下拉列表

~~~ javaScript
<html>
   <head>
       <title>下拉列表2</title>
	   <meta charset="UTF-8"/>
	  
	   <style  type="text/css">
	       div{
		      border:1px solid blue;
		   }
		   #div_0{
		      width:800px;
			  height:400px;
		      position:absolute;
			  top:100px;
			  left:250px;
		   }
		   #div_top{
		      width:600px;
			  height:120px;
		      position:absolute;
			  top:10px;
			  left:100px;
			  text-align:center;
		   }
		   #div_top_left,#div_top_right{
		       width:260px;
			   height:100px;
			   position:absolute;
			   top:10px;
		   }
		    #div_top_left{
			    left:20px;
			}
			#div_top_right{
			    right:20px;
			}
			
			#div_bottom{
			  width:700px;
			  height:220px;
		      position:absolute;
			  bottom:10px;
			  left:40px;
			  text-align:center;
			}
			#div_left,#div_right{
			  width:100px;
			  height:190px;
		      position:absolute;
			  top:15px;
			  text-align:left;
			  padding:2px;
			}
			#div_left{
			   left:40px;
			}
			#div_right{
			   right:40px;
			}
			#div_middle{
			  width:90px;
			  height:160px;
		      position:absolute;
			  top:25px;
			  text-align:center;
			  left:300px;
			}
			#div_bottom select{
			   font-size:13px;
               width:96px;	
               height:188px;		   
			}
			option{
			   border:1px solid blue;
			}
			
			#div_middle input{
			   border:1px solid #000000;
			   width:86px;
			   height:36px;
			   margin:1px;
			   background-image:url("bg.png");
			}
			#but_2_right{
			   background-position:45% 5%;
			}
			#but_all_2_right{
			   background-position:45% 30%;
			}
			#but_2_left{
			   background-position:45% 60%;
			}
			#but_all_2_left{
			   background-position:45% 90%;
			}
	   </style>
	   
   </head>
   <script  type="text/javascript">
          var oSelLeft,oSelRight,oDivLeft,oDivRight;
          window.onload=function(){
		        //给四个对象赋值
				oSelLeft=document.getElementsByName("sel_left")[0];
				oSelRight=document.getElementsByName("sel_right")[0];
				oDivLeft=document.getElementById("div_top_left");
				oDivRight=document.getElementById("div_top_right");
		       //动态给按钮注册事件
			   document.getElementById("but_2_right").onclick=function(){
			       optionChange(oSelLeft,oSelRight,false);
			   };
			   document.getElementById("but_all_2_right").onclick=function(){
			       optionChange(oSelLeft,oSelRight,true);
			   };
			   document.getElementById("but_2_left").onclick=function(){
			       optionChange(oSelRight,oSelLeft,false);
			   };
			   document.getElementById("but_all_2_left").onclick=function(){
			       optionChange(oSelRight,oSelLeft,true);
			   };
			   setDivText();
		  }
		  function optionChange(node1,node2,b){
		       //获取第一个select中的所有option
			   var collOptions=node1.options;
			   //遍历option
			   for(var i=0;i<collOptions.length;i++){
			          if(b||collOptions[i].selected){
					       collOptions[i].selected=false;//取消状态
					       //把option添加到第二个seelct中
						   node2.appendChild(collOptions[i]);
						   i--;
					  }
			   }
			   //修改两个div的文本内容
			   setDivText();
		  }
		  
		  function setDivText(){
		      //获取左边select中的所有option
			  var collOptionsLeft=oSelLeft.options;
			  var collOptionsRight=oSelRight.options;
			  //获取option的文本内容对应的字符
			  var strLeft="";
			  for(var i=0;i<collOptionsLeft.length;i++){
			      strLeft+=collOptionsLeft[i].innerText+"-";
			  }
			  strLeft=strLeft.substring(0,strLeft.length-1);//删除最后的-
			  //把文本内容添加到div中
			  oDivLeft.innerHTML=strLeft.bold().fontcolor("red");
			  var strRight="";
			  for(var i=0;i<collOptionsRight.length;i++){
			      strRight+=collOptionsRight[i].innerText+"-";
			  }
			  strRight=strRight.substring(0,strRight.length-1);//删除最后的-
			  //把文本内容添加到div中
			  oDivRight.innerHTML=strRight.bold().fontcolor("red");
		  }
          
		  
   </script>
   
   <body >
        <div  id="div_0">
		    <div  id="div_top">
			      <div  id="div_top_left"></div>
			      <div  id="div_top_right"></div>
			</div>
			<div  id="div_bottom">
			       <div  id="div_left">
				       <select name="sel_left" size="8" multiple="multiple">
					       <option value="01">选项01</option>
						   <option value="02">选项02</option>
						   <option value="03">选项03</option>
						   <option value="04">选项04</option>
						   <option value="05">选项05</option>
						   <option value="06">选项06</option>
						   <option value="07">选项07</option>
						   <option value="08">选项08</option>
					   </select>
				   </div>
			       <div  id="div_middle">
				       <input type="button" id="but_2_right"/><br/>
					   <input type="button" id="but_all_2_right"/><br/>
					   <input type="button" id="but_2_left"/><br/>
					   <input type="button" id="but_all_2_left"/><br/>
				   </div>
				   <div  id="div_right">
				       <select name="sel_right" size="8" multiple="multiple">
					      
					   </select>
				   </div>
			</div>
		   
		</div>
   </body>
</html>
~~~

**新闻字体，样式控制**

~~~ javaScript
<html>
   <head>
       <title>新闻字体：样式控制</title>
	   <meta charset="UTF-8"/>
	  
	   <style  type="text/css">
	        #div_11 div,.div_cla_1{
			      width:80px;
				  height:80px;
				  margin:5px 20px;
				  float:left;
				  border:1px solid blue;
			}
			
			.cla_1{
			    background:#aa33cc;
			}
			.cla_2{
			    background:#aacc33;
			}
			.cla_3{
			    background:#33aacc;
			}
	   </style>
	   <script  type="text/javascript">
	       window.onload=function(){
		       document.getElementById("div_1").onclick=changeBC;
			   document.getElementById("div_2").onclick=changeBC;
			   document.getElementById("div_3").onclick=changeBC;
			   changeColorFunction();
		   }
		   function changeBC(){
		         //alert(this.style.backgroundColor);
				 document.getElementById("div_text").style.backgroundColor=this.style.backgroundColor;
		   }
	   </script>
   </head>
   <body >
        <div   style="width:800px;border:1px solid blue;margin:50px auto; padding:20px;"  id="div_text">
		
			 扩展题9： 计算圆周率
					中国古代数学家研究出了计算圆周率最简单的办法:
					PI=4/1-4/3+4/5-4/7+4/9-4/11+4/13-4/15+4/17......
					这个算式的结果会无限接近于圆周率的值,
					我国古代数学家祖冲之计算出,圆周率在3.1415926 和3.1415927 之间,
					请编程计算,要想得到这样的结果,他要经过多少次加减法运算?
					注意：此题需要研究 循环的条件和每次加减的数的规律
			扩展题10： 打渔还是晒网
					中国有句老话叫“三天打渔，两天晒网” 。
				   假设有一个人从2000 年1 月1 日开始“三天打渔两天晒网” ，
				   判断今天这个人是在打渔还是在晒网？
					注意：此题需要使用%  和判断月份的天数
				注意后两道题目 难度过大
		</div>
		<hr/>
		<h3>控制背景颜色</h3>
        <div id="div_1" style="background:#aa33cc;"  class="div_cla_1">1</div>   
		<div id="div_2" style="background:#aacc33;"  class="div_cla_1">2</div>
		<div id="div_3" style="background:#33ccaa;"  class="div_cla_1">3</div>
        <hr style="clear:both;"/>	
        <h3>控制文字大小</h3>	
        <select id="selFontSize">
		     <option  value="10px">10px</option>
			 <option  value="20px">20px</option>
			 <option  value="30px">30px</option>
			 <option  value="40px">40px</option>
		<select>	 
        <script  type="text/javascript">
		        var osel=document.getElementById("selFontSize");
				//select可以注册onclick事件
				//一般select给注册onchange事件:值更改事件
				osel.onchange=function(){
				      //获取被选中的select：
					  //方案1：先获取所有的option  再判断哪个option被选中
					  //var collOptions=osel.options;
					  //for(var i=0;i<collOptions.length;i++){if(collOptions[i].selected){}}
					  
					  //select大小有value属性：  是被选中的option的value属性
					  document.getElementById("div_text").style.fontSize=osel.value;
				}
        </script>
        <hr/>
        请输入字体样式：<input type="text" value="宋体1" id="textFontFamily" /><br/>	
       <script  type="text/javascript">
	           var otext=document.getElementById("textFontFamily");
			   //输入移入：内容清空 背景颜色更改  边框取消
			   //获取输入焦点的事件
			   otext.onfocus=function(){
			       otext.value="";//内容清空
				   otext.style.backgroundColor="#ccccff";
				   otext.style.borderWidth="0px";
				   otext.style.borderBottom="3px solid blue";
			   }
			   //失去输入焦点的事件
			   otext.onblur=function(){
			        document.getElementById("div_text").style.fontFamily=otext.value;
			   }
       </script>
       <hr/>	
       请选择字体颜色：红<input type="radio" value="red" name="changeColor"  checked="checked"/>	 |  
	   绿<input type="radio" value="green" name="changeColor"/>	 |  
	   蓝<input type="radio" value="blue" name="changeColor"/>	 |  
	   黄<input type="radio" value="yellow" name="changeColor"/>	 <br/>
	   
	   <script  type="text/javascript">
	         //1 html封装数据   2 css设置样式   3 注册事件  4 写js代码
			 //给所有的changeColor注册点击事件
			 var collColor=document.getElementsByName("changeColor");
			 for(var i=0;i<collColor.length;i++){
			     collColor[i].onclick=changeColorFunction;
			 }
			 
			 function changeColorFunction(){
			       //获取被选择的changeColor
				   for(var i=0;i<collColor.length;i++){
			            if(collColor[i].checked){
						    document.getElementById("div_text").style.color=collColor[i].value;
						}
			       }
			 }
	   </script>
	   <hr/>
	   <div id="div_11">
			<div class="cla_1" >1</div>   
			<div class="cla_2" >2</div>
			<div class="cla_3" >3</div>
		</div>
		<script  type="text/javascript">
		      var collZi=document.getElementById("div_11").getElementsByTagName("div");
			  for(var i=0;i<collZi.length;i++){
			      //鼠标移入
			      collZi[i].onmouseover=function(){
				      var cn=this.className;
					  document.getElementById("div_text").className=cn;
					  
				  }
				   //鼠标移出
			      collZi[i].onmouseout=function(){
				      //取消样式
					  document.getElementById("div_text").className="";
					  //document.getElementById("div_text").setAttribute("class",null);
				  }
			  }
		</script>
   </body>
</html>
~~~





