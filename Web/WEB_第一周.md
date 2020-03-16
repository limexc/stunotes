# 第一课
-----------------------
# 介绍Web前端
软件架构 C/S 和B/S，主要从事B/S软件开发

## C/S架构 ----> Client/Server架构
特点：  
1. 软件使用前必须安装  
2. 软件更新时，客户端和服务端必须同时更新  
3. 软件不能跨平台  
4. 采用自有协议，较安全  

## B/S架构 ----> Browser/Server架构
特点：  
1. 软件使用前不需要安装  
2. 软件更新时，客户端不需要更新  
3. 软件可以跨平台，只需要浏览器  
4. 公有协议 HTTP协议，相对不安全  

## W3C标准
> 结构： HTML  
> 表现： CSS  
> 行为： JavaScript  

## 工具
> 浏览器： 火狐、IE、Chrome、Safari、Opera  
> 编辑器： 记事本、NotePad++、HBulider  
> 图片工具： Photoshop  
---------------------------

#第二课
---------------------------
HTML是用来描述网页的一种标记语言。  
* HTML指超文本标记语言 HyperText Markup Language 

## 示例  
``` html
<!DOCTYPE html>		<!--H5的文档声明-->
<html>
	<!-- head 主要帮助浏览器解析网页-->
	<head>
		<meta charset="utf-8">
		<!-- title 默认显示在浏览器标签-->
		<title>网页标题</title>
	</head>

	<!-- body 网页的主体，网页内所有可见内容-->
	<body>
		<h1>标题</h1>
		<!--可以为标签设置属性,常见：id标签的唯一表示 class为标签分组 title指定标签标题-->
		<h1><font color="red" size="1"> </font></h1>>


		<p>段落
			<b>加粗文本 bold   </b>
			<i>斜体文本 italic </i>
			<strong>定义加重语气</strong>
		</p>
		<!--br:换行 hr:水平线 pre:预定义文本-->
		<p>这个<br/>段落<br/>演示了分行的效果</p>
		<hr/>
		<pre>
			H
				T
					M
						L
		</pre>

		<p>这是<sub> 下标 </sub>和<sup> 上标 </sup></p>
	</body>

</html>
```

------------------
#第三课
## 文件目录  
>HTML  
>>css  
>>>index.css  

>>html  
>>>html_body.html  
>>>html_head.html  
>>>html_Script.html  

>>img  
>>>WEB_1_1.png  
>>>WEB_1_2.png  

>>js  
>>>index.js  

>>index.html  

## 页面头部元素 head  
声明：```<!DOCTYPE html>```  
标题元素：title  
元信息元素：meta  
样式元素：style  
链接元素：link  
脚本元素：script  

#### 示例  
* 头部元素示例  
![头部元素示例](https://file-xian.oss-cn-qingdao.aliyuncs.com/mk-media/WEB_1_1.png ''头部元素示例'')
* CSS示例  
![CSS示例](https://file-xian.oss-cn-qingdao.aliyuncs.com/mk-media/WEB_1_2.png ''CSS示例'')

## 外部js文件  
html_Script.html  
``` html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>外部JS文件</title>
		<script src="../js/index.js"></script>
	</head>
	<body>
		<!--onclick:js点击事件，当点击相关按钮时执行该事件-->
		<button onclick="login()">登录</buttion>
	</body>
</html>
```
index.js  
``` javascript
function login(){
	alert("Hello");
}
```
## 页面主体元素 body  
html_body.html  
``` html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<!--
		background:设置body的背景图片，默认为平铺 这个属性弃用
		background-repeat:no-repeat 设置不平铺
    -->
	<body background="../img/WEB_1_1.png" style="background-repeat:no-repeat;">
		<p>空格:&nbsp;大于:&gt;小于:&lt;引号:&quot;版权:&copy;</p>
	</body>
</html>
```
##### 特殊符号  
|特殊符号|||||
|:----------:|:--------:|:--------:|:----------:|:----------:|  
|    空格    |    大于   |    小于  |    引号    |    版权     |  
|```&nbsp;```|```&gt;```|```&it;```|```&quot;```|```&copy;```|  

------------------------------------  
# 第四课  
## 基本标签  
标题：```<h1>这位是一级标题</h1>```  
换行：```<br/>```  
水平线:```<hr/>```   
预定义文本:```<pre>  </pre>```  
字体(弃用)：```<font size="12" face="宋体" color="red">  </font>```

### 文本格式化  
```<!--以下都是行元素:不独占一行，它的宽度根据文本内容计算-->```  
重要(粗体): ```<strong></strong>```  
重要(斜体): ```<em></em>```  
粗体: ```<b></b>```  
斜体: ```<i></i>```  
小号字体: ```<small></small>```  
字体放大: ```<big></big>```  
下标: ```<sub></sub>```  
上标: ```<sup></sup>```  
插入字: ```<ins></ins>```  
删除字: ```<del></del>```  

## 图像 超链接 列表  
### 图像  
img标签(图片标签): ```<img src="path" alt="提示" title="标题" width="" height=""/>```
>	img是一个行内元素。  
	src :图片路径 相对/绝对。  
	title :当鼠标在图片上时提示。  
	alt : 当图片加载失败时的提示。  
	height : 设置图片的高。  
	width : 设置图片的宽。  
	border :设置图片边款，默认为0。  

### 超链接  
a标签(文本): ```<a href="path" target="打开窗口位置" title="标题">描述链接的文本</a>```  
a标签(图片): ```<a href="path"><img src="path"></a> ```   
a标签(页面/锚链接): ```<a href="#id"></a>```  
>	a标签是一个行内元素。  
	href :链接的路径(http ftp mailto)。  
	target :打开位置(当前页面 _self /新建页面 _blank /在父窗口打开 _parent /取消当前框架在当前窗口打开 _top )  
	title :当鼠标移上时的提示。
锚链接：链接到当前页面的资源,需要id值。  

``` html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>锚链接</title>
	</head>
	<body>
		<a href="#p1">第一章</a><br>
		<a href="#p2">第二章</a><br>
		<br><br><br><br><br><br>
		<p id="p1">第一章</p><br>
		<br><br><br><br><br><br>
		<p id="p2">第二章</p>
	</body>
</html>
```
### 列表  
**列表属于块元素**  

* 无序列表  
`<!--建议使用CSS-->`  
类型type取值: disc 默认实心圆/square 实心正方/circle 空心圆  
style:行内样式/外部样式/页面样式  
``` html
<ul type="square"">
	<li>无序列表</li>
	<li>演示</li>
</ul>

<ul  style="list-style-type:square;color:red">
	<li>style</li>
	<li>演示</li>
</ul>
```  

* 有序列表  
type取值: 1 a/A  i/I  
``` html
<ol type="a">
	<li>有序列表</li>
	<li>演示</li>
</ol>
```  

* 自定义列表  
无项目符号及排序 无style属性
``` html
<dl>
	<dt>标题 /词条</dt>
	<dd>内容/对词条的解释</dd>
	<dt>自定义列表</dt>
	<dd>演示</dd>
</dl>
```

---------------------
# 第五课  
## 表格  
表格基本结构:  
> 表格标签: tabale  
  行标签: tr  
  列标签: td   
  头部标签: th (字体加粗，居中)  
  标题标签: caption  
  边框: border  
  首部元素: thead  
  表体元素: tbody  
  表尾元素: tfoot  
  表格中内容与单元格之间距离: cellpadding  
  单元格与单元格之间距离: cellspacing  

table.html  
``` html  
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>表格</title>
	<style>
		/*标签选择器*/
		table{
		width: 500px;
		text-align: center; /*设置字体居中*/
		margin: 0 auto; /*表格根据body的大小自动左右移动*/ 
		}
		/*组合选择器*/
		table,th,td{
		/*将所有的table,th,td标签的边框合并*/
		border-collapse: collapse;  
		}
	</style>
</head>
<body>
	<table border="1">
		<caption><h3>人员登记</h3></caption>
		<thead style="background-color: #FF0000">
	 		<tr>
				<th>姓名</th>
				<th>性别</th>
				<th>年龄</th>
			</tr>
		</thead>
		<tbody style="background-color: #CCFF00">
			<tr>
				<td>张三</td>
				<td>男</td>
				<td>10</td>
			</tr>
			<tr>
				<td>李四</td>
				<td>女</td>
				<td>20</td>
			</tr>
		</tbody>

		<tfoot style="background-color: #FFCC00">
			<tr>
				<td>备注</td>
				<td colspan="2">colspan合并列 rowspan合并行</td>
			</tr>
		</tfoot>
	</table>
</body>
</html>
```  

## 表单  
> text: 定义常规文本输入。  
  radio: 定义单选按钮输入(多个选择之一)  
  submit: 定义提交按钮(提交表单)  
  textarea 多行文本  
  password 密码框  
  checkbox 多选框  
  reset 重置  
  file 文件  
  hidden 隐藏域，不会在界面上显示，但是源码可见  
  image 图片  
  button 按钮  

  method: 属性规定在提交表单时所用的HTTP方法(GET/POST)  
  action: 定义在提交表单时执行的动作。  
  maxlength type为text或password时，输入的最大字符数。  
  value: 设置初始值
  checked="checked"默认选中 
  size 设置输入框的大小 

from.html  
``` html  
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>表单</title>
</head>
<body>
	<!--
		from:表单标签
		method:表单的提交方式，两种取值。get/post

		action:定义在提交表单时执行的动作。
		输入框 input
  
	-->
	<form action="table.html" method="get">
		用户名:<input type="Text" name="userName" id="userName"><br>
		密码:<input type="password" name="passWd" id="passWd"><br>
		<input type="submit" value="登录">
	</form>
</body>
</html>
```

### GET与POST  
GET(默认方法):  
如果表单提交是被动的（比如搜索引擎查询），并且没有敏感信息。  
使用 GET 时，表单数据在页面地址栏中是可见。查询用get。  
***注释：GET 最适合少量数据的提交。浏览器会设定容量限制(1024字节)。***  
POST：  
如果表单正在更新数据，或者包含敏感信息（例如密码）。  
***POST 的安全性更加，因为在页面地址栏中被提交的数据是不可见的。***  
 
***注意：要使用上传必须修改表单enctype属性修改为"multipart/form-data"***   
file上传按钮。  

###　实例: 注册页  
``` html
<!DOCTYPE html>
<html>
<head>
	<title>注册</title>
</head>
<body>
	<form action="#" method="post" enctype="multipart/form-data">
		<!--span:行内标签-->
		<input type="image" name="imglogin" src="#" id="imglogin"><br/>
		<span>账号：</span>
		<input type="text" name="userName" id="userName" /><br/>
		<span>密码：</span>
		<input type="password" name="passWd" id="passWd" /><br/>
		<span>性别：</span>
		<input type="radio" name="sex" id="man" checked="checked" />男
		<input type="radio" name="sex" id="wan" />女
		<br/>
		<span>爱好：</span>
		<input type="checkbox" name="hobby" value="1" />看书
		<input type="checkbox" name="hobby" value="2" />唱歌
		<input type="checkbox" name="hobby" value="3" />跳舞
		<input type="checkbox" name="hobby" value="4" />上网
		<br/>
		<span>上传：</span>
		<input type="file" name="file" id="file" /><br/>
		<span>颜色：</span>
		<select name="color" id="color">
			<option value="other">---请选择---</option>
			<option value="red">红色</option>
			<option value="green">绿色</option>
			<option value="yello">黄色</option>
		</select><br/>
		<span>备注：</span>
		<!--rows规定行数 cols规定列数-->
		<textarea name="desc" id="desc" rows="5" cols="10"></textarea><br/>
		<input type="submit" />
		<!--设置按钮禁用-->
		<input type="button" value="查询" disabled="disabled"/>
	</form>

</body>
</html>
```  



