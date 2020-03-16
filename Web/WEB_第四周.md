# HTML5表单  
## 表单新增属性  
新增的属性值  
type="email  url  tel  date  time  month  week  number  search  color range "  

``` html
<!DOCTYPE html>
<html>
<head>
	<title></title>
	<meta charset="utf-8">
</head>
<body>
    <form action="#" style="width: 500px">
    	<fieldset><!--对表单元素分组-->
    		<legend>用户登录</legend>
    		姓名：<input type="text" name="userName" id="userName" />
    	    <br/>
    	    密码：<input type="password" name="pwd" id="pwd">
    	</fieldset>
    	
    </form>
</body>
</html>
```

### email  
email提供了默认的电子邮件完整的验证，要求必须包含@，必须包含域名。  
`<input type="email" name="email" />`

### tel  
tel并没有表单验证，其作用是在移动端打开数字键盘  
`<input type="tel" name="tel" />`   

### url  
url验证必须携带`http://`  
`<input type="url" name="url" />`  

### number  
根据设置提供选择数字的功能，其中min为最小值，max为最大值，value为默认值，step为点击箭头时数字的变化量，max、min、step、value均可不写，目前某些浏览器还不支持。  
`<input type="number" name="number" min=2 max=100 step=5 value="15"/>`

### range  
会以一个滑块的形式表现包含一定范围内数字值的输入域，max为最大值，min为最小值，value为默认值，如果没有设置max和min，默认值是1-100  
`<input type="range" name="range" min=20 max=200 value="60"/>`  

### search  
用于搜索域，若加上result="s"属性，则会在搜索框前面加一个搜索图标（我这里浏览器显示不出效果） 
`<input type="search" name="search" result="s"/>`  

### color
color类型会提供颜色拾取器，供用户选择颜色，并将用户选择的颜色填充到此元素中  
`<input type="color" name="color"/>`  

### 日期和时间类型  
date：选取日、月、年  
`<input type="date" name="date"/>`  

month：选取月、年  
`<input type="month" name="month"/>`  

week：选取周、年  
`<input type="week" name="week"/>`  

time：选取小时、分钟  
`<input type="time" name="time"/>`  


## 新增input属性，后面为支持该属性的元素
`autofocus`：在打开页面时使元素自动获取焦点    //input,button,select,textarea  
`placeholder`: 在用户输入时进行提示  // input,textarea  
`form`：用于表明元素属于哪个表单，无论元素的位置在哪里，所属表单都能获取该元素的值      //input,output,button,select,textarea,fieldset    
`required`：表明该元素是必填项，当提交表单的时候会自动验证该元素的内容是否不为空  //input,textarea  
`max/min/step`：限制值的输入范围，以及值的变化程度。上面的新增number元素有介绍。   //input  
`autocomplete`：使form元素或者input元素拥有自动完成功能，既记录用户之前输入的值，关闭为off，默认为on。     //form,input  
`multiple`:type=file，可以选择多个文件上传。  
`pattern`：添加正则表达式  



`datalist`：建立选项列表，需要建立一个输入框与datalist关联，才能生效  
选择科目：<input type="text" name="km" list="sub">
<datalist id="sub">
	<option value="英语" label="不会"></option>
	<option value="语文" label="简单"></option>
</datalist>
``` html
<input type="text" name="km" list="sub">
<datalist id="sub">
	<option value="英语" label="不会"></option>
</datalist>
```


--------------------------------------------------


# 多媒体元素基本属性  
1. embed：直接插入音频或视频文件，本质上调用本机上已经安装的软件，兼容性差。    
2. flash插件：安装flash插件，学习flash难

video元素与audio元素相同属性：  

* `src`属性和`autoplay`属性  
    * `src`属性用于指定媒体数据的URL地址。  
    * `autoplay`属性用于指定媒体是否在页面加载和自动播放。  
    * 使用方法：`<video src="xxx.mov" autoplay="autoplay"></video>`  
* `perload`属性
    * 用于指定音视频文件是否预加载。  
    * `none` 表示不预加载 `metadata` 表示只加载媒体元数据 `auto` 表示加载全部音视频  
    * 使用方法：`<video src="xxx.mov" preload="auto"></video>`  
* `controls`属性  
    * 指定是否为音视频添加浏览器自带的播放控制条。  
    * 使用方法：`<video src="xxx.mov" controls="controls"></video>`  


## video  

|浏览器|MP4|WebM|Ogg|
|:-:|:-:|:-:|:-:|
|Internet Explorer|YES|NO|NO|
|Chrome|YES|YES|YES|
|Firefox|YES|YES|YES|
|Safari|YES|NO|NO|
|Opera|YES (从Opera25起)|YES|YES|

* MP4 = 带有 H.264 视频编码和 AAC 音频编码的 MPEG 4 文件  
* WebM = 带有 VP8 视频编码和 Vorbis 音频编码的 WebM 文件  
* Ogg = 带有 Theora 视频编码和 Vorbis 音频编码的 Ogg 文件  

属性：  

* `loop` 循环播放  
* `poster` 当视频加载失败或者还没点击播放时，加载一个默认图片。  
* `width` `height` 设置视频宽度高度  

注意：一般设置视频高度时，不要同时设置宽度，让其自动等比缩放  

``` html
<video  controls="controls"  width="300">
         <source src="move.ogg" type="video/ogg" >
         <source src="move.mp4" type="video/mp4" >
         您的浏览器暂不支持video标签。播放视频
</video>
```
此种方式可以让浏览器来选择支持的视频格式进行播放，如上，如果ogg格式支持，则播放ogg视频，如果ogg不支持，则判断mp4是否支持，如果MP4支持，则播放mp4格式视频。如果mp4格式也不支持，则显示自定义文本。  

## audio  

||IE 9|Firefox 3.5|Opera 10.5|Chrome 3.0|Safari 3.0|
|:-:|:-:|:-:|:-:|:-:|:-:|
|Ogg Vorbis||√|√|√||
|MP3|√|||√|√|
|Wav||√|√||√|


属性：  

* `loop` 循环播放 

例如：  
<audio src="https://file-xian.oss-cn-qingdao.aliyuncs.com/mk-media/新房客-王菲.mp3" controls="controls">您的浏览器暂不支持audio标签。</audio>  


#### 参考 [HTML5笔记-2 最骚的就是你](https://www.cnblogs.com/libin-1/p/6231375.html)  
------------------------------------------------


# CSS  
## CSS选择器  
### 子元素选择器  
子元素选择器和后代选择器类似，子选择器选择的时该元素的直接下一代，而后代选择器选择的是该元素的所有后代。  
语法： 选择器>选择器  
``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>子选择器</title>
	<style>
		.food>li{
			border: 1px solid red;
		}
		/*该元素所有后代第一个li*/
		.food li:first-child{
			background-color: yellow;
			border: 1px solid red;
		}
		/*该元素直接下一代的最后一个子元素*/
		.food>li:last-child{
			background-color: #808080;
		}
	</style>
</head>
<body>
    <h1>食物</h1>
    <ul class="food">
    	<li>水果
    		<ul>
    			<li>香蕉</li>
    			<li>苹果</li>
    			<li>橘子</li>
    		</ul>
    	</li>
    	<li>蔬菜
    		<ul>
    			<li>白菜</li>
    			<li>茄子</li>
    			<li>油菜</li>
    		</ul>
    	</li>
    </ul>
</body>
</html>
```


### 相邻兄弟元素选择器  
如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器   
E +F  

### 兄弟选择器  
位置无须紧邻，只须同层级，A~B 选择A元素之后所有同层级B元素。  
A~B  


### 属性选择器  
对带有指定属性的HTML元素设置样式。  
可以为拥有指定属性的HTML元素设置样式，而不仅限于class和id属性。  

> 选择具有属性att且值为x的属性。  
  `E[att="x"]`  
  选择具有att属性且值为一用空格分隔的字词列表。  
  `E[att~="x"]`  
  选择具有att属性值以x开头并且用"-"分隔的字符串。  
  `E[att|="x"]`  
  选择具有att属性，且值为x开头的元素。  
  `E[att^="x"]`  
  选择具有att属性，且值为x结尾的元素。  
  `E[att$="x"]`  
  选择具有att属性，且值包含x的元素。  
  `E[att*="x"]`  

**注释**：只有在规定了!DOCTYPE时，IE7和IE8才支持属性选择器。在IE6 及更低的版本中，不支持属性选择。  

下面的例子为带有title属性的所有元素设置样式：  
``` html
[title]
{
color:red;
}
```
选则p标签中带有id的元素：  
``` html
p[id]{
	color:green;
}
```

### 结构伪类选择器  
|选择符|版本|简介|
|:-:|:-:|:-:|
|E:link|css1|链接伪类选择器，设置超链接未被访问前的样式|
|E:visited|css1|链接伪类选择器，设置链接地址已经被访问过时的样式|
|E:hover|css1|用户操作伪类选择器，设置元素在鼠标悬停时的样式|
|E:active|css1|用户操作伪类选择器，设置元素在被用户激活时（鼠标点击释放之间）时的样式|
|E:first-child|css2|匹配父元素的第一个子元素E|
|E:last-child|css3|匹配父元素的最后一个子元素E|
|E:only-child|css3|匹配父元素仅有的一个子元素E|
|E:nth-chlid(n)|css3|匹配父元素的第n个子元素E|
|E:nth-last-chlid(n)|css3|匹配父元素的倒数第n个子元素E|
|E:first-of-type|css3|匹配同类型中的第一个同级的兄弟元素E|
|E:last-of-type|css3|匹配同类型中的最后一个同级的兄弟元素E|
|E:only-of-type(n)|css3|匹配同类型中唯一的一个同级的兄弟元素E|
|E:nth-of-type(n)|css3|匹配同类型中的第n给同级兄弟元素E|
|E:nth-last-of-type(n)|css3|匹配同类型中的倒数第n个同级兄弟元素E|
|E:empty|css3|空值 匹配没有任何子元素(包括text)的元素E|

注意： nth-child(索引值|关键字) 索引值从1开始 关键字可以设置 even 偶数 odd 奇数等 

### 伪元素选择器
|选择器|版本|简介|
|:-:|:-:|:-:|
|E:before|css3|定义在一个元素内容之前插入content属性定义的内容与样式|
|E:after|css3|定义在一个元素内容之后插入content属性定义的内容与样式|
|E::first-letter|css3|文本的第一个字母或字（不是词组）|
|E::first-line|css3|文本第一行|
|E::selection|css3|可改变选中文本的样式|


``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>伪元素选择器</title>
	<style>
		/*使用E:before或者E:after，content属性必须定义*/
		li:before{
			content: "注意: ";
			color: red;
		}
		li:after{
			content: "呵呵";
			color: blue;
		}
	</style>
</head>
<body>
	<ul>
		<li>列表项目1</li>
		<li>列表项目2</li>
		<li>列表项目3</li>
	</ul>
</body>
</html>
```
效果：  
![伪元素选择器](https://file-xian.oss-cn-qingdao.aliyuncs.com/images/20200311103140.png)  


## 文本阴影  

<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>文本阴影</title>
	<style>
		.demo{
			width: 500px;
			background-color: #808080;
			font: bold 32px "微软雅黑";
			margin:  20px auto;
			color: white;
			text-align: center;
			line-height: 50px;
		}
		/*text-shadow：x轴 y轴 模糊值 颜色*/
		.demo1{
			text-shadow: -2px -2px 5px red;
		}
		.demo2{
			text-shadow: 0px 0px 20px white;
		}
		.demo3{
			text-shadow: 0px 0px 30px red;
		}
		.demo4{
			color: black;
			text-shadow: 0px 1px 0px white;
		}
		.demo5{
			text-shadow: -1px -1px 0px #eee, -2px -2px 0px #ddd;
		}
		.demo6{
			color: transparent; /*transparent 透明*/
			text-shadow: 0px 0px  5px orange;
		}
	</style>
</head>
<body>
    <div class="demo demo1">咸闲贤鱼</div>
    <div class="demo demo2">咸闲贤鱼</div>
    <div class="demo demo3">咸闲贤鱼</div>
    <div class="demo demo4">咸闲贤鱼</div>
    <div class="demo demo5">咸闲贤鱼</div>
    <div class="demo demo6">咸闲贤鱼</div>
</body>
</html>

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>文本阴影</title>
	<style>
		.demo{
			width: 500px;
			background-color: #808080;
			font: bold 32px "微软雅黑";
			margin:  20px auto;
			color: white;
			text-align: center;
			line-height: 50px;
		}
		/*text-shadow：x轴 y轴 模糊值 颜色*/
		.demo1{
			text-shadow: -2px -2px 5px red;
		}
		.demo2{
			text-shadow: 0px 0px 20px white;
		}
		.demo3{
			text-shadow: 0px 0px 30px red;
		}
		.demo4{
			color: black;
			text-shadow: 0px 1px 0px white;
		}
		.demo5{
			text-shadow: -1px -1px 0px #eee, -2px -2px 0px #ddd;
		}
		.demo6{
			color: transparent; /*transparent 透明*/
			text-shadow: 0px 0px  5px orange;
		}
	</style>
</head>
<body>
    <div class="demo demo1">咸闲贤鱼</div>
    <div class="demo demo2">咸闲贤鱼</div>
    <div class="demo demo3">咸闲贤鱼</div>
    <div class="demo demo4">咸闲贤鱼</div>
    <div class="demo demo5">咸闲贤鱼</div>
    <div class="demo demo6">咸闲贤鱼</div>
</body>
</html>
```

## 盒模型  

<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>盒模型</title>
	<style>
		.boxtest{
			width: 400px;
			height: 200px;
			background-color: #808080;
			margin: auto;
		}
		.boxc1{
			width: 200px;
			height: 100%;
			background-color: red;
			float: left;
		}
		.boxc2{
			width: 200px;
			height: 100%;
			background-color: blue;
			float: left;
		}
	</style>
</head>
<body>
    <div class="boxtest">
    	<div class="boxc1">Nginx + GeoIP 区分用户 IP 归属国</div>
    	<div class="boxc2"></div>
    </div>
</body>
</html>

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>盒模型</title>
	<style>
		.boxtest{
			width: 400px;
			height: 200px;
			background-color: #808080;
			margin: auto;
		}
		.boxc1{
			width: 200px;
			height: 100%;
			background-color: red;
			float: left;
		}
		.boxc2{
			width: 200px;
			height: 100%;
			background-color: blue;
			float: left;
		}
	</style>
</head>
<body>
    <div class="boxtest">
    	<div class="boxc1">Nginx + GeoIP 区分用户 IP 归属国</div>
    	<div class="boxc2"></div>
    </div>
</body>
</html>
```

## 圆角  

<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>圆角</title>
	<style>
		.divfillet{
			width: 200px;
			background-color: red;
			height: 100px;
			border-radius: 20px;
			margin: auto;
			/*椭圆*/
			/*border-radius: 100px/50px;*/
		}
	</style>
</head>
<body>
	<div class="divfillet"></div>
</body>
</html>

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>圆角</title>
	<style>
		.divfillet{
			width: 200px;
			background-color: red;
			height: 100px;
			border-radius: 20px;
			/*椭圆*/
			/*border-radius: 100px/50px;*/
			margin: auto;
		}
	</style>
</head>
<body>
	<div class="divfillet"></div>
</body>
</html>
```

## 颜色渐变  

linear-gradient 线性渐变   
参数  

1. to left / to right / to top / to bottom
2. 起点颜色  
3. 终点颜色  

<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>颜色渐变</title>
	<style>
		.divcolor{
			width: 200px;
			height: 200px;
			background: linear-gradient(to right,red,blue);
			margin: auto;
		}
	</style>
</head>
<body>
    <div  class="divcolor"></div>
</body>
</html>

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>颜色渐变</title>
	<style>
		.divcolor{
			width: 200px;
			height: 200px;
			background: linear-gradient(to right,red,blue);
			margin: auto;
		}
	</style>
</head>
<body>
    <div  class="divcolor"></div>
</body>
</html>
```

可以定义颜色位置：如从0%到50%是红色，50%到100%是绿色  
`background: linear-gradient(to right,red 0%,red 50%,green 50%,green 100%);`  

## 过渡 transition
参数  

* 设置过渡样式 transition-property: left;
* 设置过渡时间 秒 毫秒 transition-duration: 2s;
* 设置运动速度 linear均速 ease先慢后快再慢 transition-timing-function: ease;
* 过渡效果的延迟 秒 transition-delay: 2s;
* transition: left,10s,linear,0s;

浏览器前缀  
-moz-  firefox    
-webkit-  chrome Safari   

Safari 需要前缀 -webkit-。  
**注释：**Internet Explorer 9 以及更早的版本，不支持 transition 属性。  
**注释：**Chrome 25 以及更早的版本，需要前缀 -webkit-。  

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title></title>
	<style>
		.boxc3{
			width: 200px;
			height: 200px;
			background-color: red;
			position: absolute;
			left: 100px;
			top: 100px;
			/*设置过渡效果*/
			transition-property: left;
			/*设置过渡时间*/
			transition-duration: 2s;
		}
		.boxc3:active{
			left: 1000px;
		}
	</style>
</head>
<body>
    <div class="boxc3"></div>
</body>
</html>
```
`transition: left 10s linear 0s,background-color 10s linear 0s;`  

## transform  变形  

Internet Explorer 10、Firefox、Opera 支持 transform 属性。  
Internet Explorer 9 支持替代的 -ms-transform 属性（仅适用于 2D 转换）。  
Safari 和 Chrome 支持替代的 -webkit-transform 属性（3D 和 2D 转换）。  
Opera 只支持 2D 转换。  

transform属性可用于内联(inline)元素和块级(block)元素。它允许我们旋转、缩放和移动元素，他有几个属性值参数：  

1. rotate(旋转)允许你通过传递一个度数值来转动一个对象；  
2. scale是一个缩放功能，可以让任一元素变的更大。它使用一个或者两个正数和负数以及小数作为参数；当使用一个参数时表示X轴和Y轴的缩放相同；  
3. translate就是基于X和Y 坐标重新定位元素，当使用一个参数时表示X轴和Y轴的参数相同；  
4. skew倾斜（ps中的斜切），参数是度数，当使用一个参数时表示X轴和Y轴的参数相同；  
5. matrix矩阵变换，就是基于X和Y 坐标重新定位元素，它使用6个参数。  

### 缩放 scale  
transform:scale(x,y)  
scaleX(x)  
scaleY(y)  

### 旋转 rotate
transform:rotate(30deg)

### 扭曲 skew
transform: skew(30deg)

## 改变元素基点 transform-origin
Internet Explorer 10、Firefox、Opera 支持 transform-origin 属性。  
Internet Explorer 9 支持替代的 -ms-transform-origin 属性（仅适用于 2D 转换）。  
Safari 和 Chrome 支持替代的 -webkit-transform-origin 属性（3D 和 2D 转换）。  
Opera 只支持 2D 转换。  

* transform-origin是变形原点，也就是该元素围绕着那个点变形或旋转，该属性只有在设置了transform属性的时候起作用  
* 因为我们元素默认基点就是其中心位置，换句话说我们没有使用transform-origin改变元素基点位置的情况下，transform进行的rotate,translate,scale,skew,matrix等操作都是以元素自己中心位置进行变化  
* transform-origin(X,Y):用来设置元素的运动的基点（参照点）。默认点是元素的中心点。其中X和Y的值可以是百分值,em,px，其中X也可以是字符参数值left,center,right；Y和X一样除了百分值外还可以设置字符值top,center,bottom 。 

left，center，right是水平方向取值，对应的百分值为left=0%;center=50%;right=100%  
而top center bottom是垂直方向的取值，其中top=0%;center=50%;bottom=100%;  
如果只取一个值，表示垂直方向值不变。  

注：transform-origin并不是transform中的属性值，他具有自己的语法，但是他要结合transform才能起作用。  

transform-origin: x-axis y-axis z-axis;