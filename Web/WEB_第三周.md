# CSS盒子模型 Box Model  
CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。  
盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。  
下面的图片说明了盒子模型(Box Model)：  
![盒子模型](https://file-xian.oss-cn-qingdao.aliyuncs.com/images/20200302090841.png)  
不同部分的说明：  

* Margin(外边距) - 清除边框外的区域，外边距是透明的。  
* Border(边框) - 围绕在内边距和内容外的边框。  
* Padding(内边距) - 清除内容周围的区域，内边距是透明的。  
* Content(内容) - 盒子的内容，显示文本和图像。  

**外边距 Margin**  
外边距属性为 margin  可以对这四个子属性进行简写  
* `margin-top:1px;`		上边距为1px  
* `margin-right:2px;`	右边距为2px  
* `margin-bottom:1px;`	下边距为1px  
* `margin-left:1px;`	左边距为1px  

**内边距 Padding**  
子属性与margin相同。尽量少使用Padding。  

**标准文档流组成：**  
* 块级元素(block):  
`<h1>... <h6> <p> <div> <dl> <ul> <ol> <table> ...`  
* 内联元素(inline):  
`<span> <a> <img> <strong> <sup> <sub> <samll> <input> ...`  

**标准文档流 按照标签在顺序正确执行**  
**非标准文档流 不是按照标签在顺序正确执行 例如块元素加了浮动定位**  

## display属性  
**作用：**  
* 控制元素的显示和隐藏。
* 控制元素与行级元素的转变。  

|值|说明|
|:--:|:----:|
|block|块级元素的默认值，元素会被显示为块级元素，该元素前后会带有换行符|
|inline|内联元素的默认值，元素会被显示为内联元素，该元素前后没有换行符|
|none|设置元素不会被显示|

行内元素又称内联元素，它的高度和宽度是内容决定的，不能单独设置高度和宽度。  

`div`元素的用法：网页布局、排版网页内容  


## float属性  

浮动:float  
* left 左浮动  
* right 右浮动  

1. 浮动后将脱离标准文档流，变成一个非标准文档流。  
2. 块元素浮动后将失去独占一行的资格，变成一个行内元素。  
3. 浮动元素将紧贴着上一个浮动元素或父元素，宽度不够将会换行。  


```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title></title>
	<style>
		.box1{
			height: 100px;
			width: 100px;
			background-color: #0000FF;
			float: right;
		}
		.box2{
			height: 150px;
			width: 150px;
			background-color: #FFA500;
			float: right;
		}
		.box3{
			height: 200px;
			width: 200px;
			background-color: blueviolet;
			float: right;
		}
	</style>
</head>
<body>
	<div class="box1">盒子一</div>
	<div class="box2">盒子二</div>
	<div class="box3">盒子三</div>
</body>
</html>
```

**清除浮动 clear**

`left`  左侧不允许浮动    
`right` 右侧不允许浮动  
`both`  左右不允许浮动  
`none`

1. 如果父元素没有设置高度，那么其高度就是由没有浮动的内容撑起来的。  
2. 如果子元素设置了浮动，脱离了标准文档流，那么父元素的高度将被忽略。  
3. 如果不清除浮动，父元素就会出现高度不够，那样的话背景属性将得不到正确的解析。  
4. 清除浮动影响的是元素本身，清除的是该元素左右的浮动，只能对块元素有效。  


**OverFlow属性**  
`overflow: visible;`  默认值。内容不会被修剪，会呈现在元素框之外  
`overflow: hidden;`  内容会被修剪，并且其余内容不可见  
`overflow: scroll;`  内容会被修剪，浏览器会显示滚动条以便查看其余内容  
`overflow: auto;`  由浏览器定夺，如果内容被修剪，就会显示滚动条  
`overflow: inherit;`   规定从父元素继承overflow属性的值  


### Position属性
定位把指定的元素固定到某一位置  
positon  设置定位  
值：  
static  默认值，没有定位  
relative  相对定位  
absolute  相对定位  
fixed  固定定位，相对于浏览器窗口定位  

#### position设置为relative时，则该元素开启了相对定位  

1. 当元素设置了相对定位以后，而不设置偏移量时，元素不会发生改变。  
2. 相对定位是相对于元素在文档流中原来的位置进行定位  
3. 相对定位会使元素不会脱离标准文档流  
4. 行内元素也可以使用相对定位，相对定位不会改变元素的本质，块还是块，行内还是行内  

当元素开启相对定位以后，可以通过left、right、top、bottom设置元素的偏移量（static）除外  
left：相对于他原来的位置向左移动  
right：相对于他原来的位置向右移动
top：相对于原来的位置向上移动
bottom：相对于原来的位置向下移动

#### position设置为absolute开启绝对定位  

1. 绝对定位和相对离他最近的开启定位的祖先元素进行偏移  
2. 如果他的祖先元素没有定位，会根据浏览器窗口进行定位（body）  
3. 绝对定位会脱离标准文档流  
4. 开启绝对定位，不设置偏移量，位置不会发生改变。  

#### fixed固定定位  

1. 固定定位永远相对于浏览器窗口进行定位  
2. 固定定位也是一种绝对定位，只是他的参照物是body  
3. 固定定位就是固定在窗口某个位置，不随滚动条滚动而滚动  

只要开启了定位，就会产生层级关系  
*IE6及以下不支持*  

### z-index 层叠顺序  

1. 如果定位元素层级一样，下边的元素会覆盖住双目安定元素  
2. 拥有更高堆叠顺序的元素总是会处于堆叠顺序较低的元素的前面。  
3. 该属性设置一个定位元素沿 z 轴的位置，z 轴定义为垂直延伸到显示区的轴。  
4. 如果为正数，则离用户更近，为负数则表示离用户更远。  

### opacity 可以设置元素透明  

* 0   表示完全透明  
* 1   表示完全不透明  
* 0.5 透明半透明

*IE8及以下浏览器不支持，支持替代的`filter`。例如：`filter:Alpha(opacity=透明度)` 值 0-100*  

HTML5可以省略的标签元素  
![HTML5可以省略的标签元素](https://file-xian.oss-cn-qingdao.aliyuncs.com/images/20200305102702.png)  
HTML5新增元素  
![HTML5新增元素](https://file-xian.oss-cn-qingdao.aliyuncs.com/images/20200305103037.png)  


## 语义标签网页布局  

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title></title>
	<style>
		body{
			width: 980px;
			padding: 0px;
			margin: 0px;
		}
		.default_style{
			background-color: cornflowerblue;
		}
		header{
			width: 100%;
			height: 90px;
			margin-top: 10px;
		}
		header .logo{
			background-color: red;
			width: 100px;
			height: 45px;
			float: left;
			margin:10px 0px 0px 10px; 
			text-align: center;
			font-weight: bold;
			line-height: 45px;/*设置行高，可以使文本居中*/
			border-radius: 10px;
		}
		nav{
			width: 100%;
			height: 70px;
		}
		nav>ul{
			list-style-type: none;
		}
		nav>ul>li{
			float: left;
			margin-right: 20px;
			line-height: 50px;
		}
		nav>ul>li>a:hover{
			color: red;
		}
		main{
			width: 100%;
			height: 400px;
		}
		main>article{
			width: 70%;
			height: 100%;
			float: left;
			margin: 10px 0px 10px 0px;
		}
		aside{
			margin: 10px 0px 10px 0px;
			float: left;
			width: 30%;
			height: 100%;
		}
		aside .aside_div{
			height: 100%;
			margin-left: 10px;
		}
		footer{
			width: 100%;
			height: 40px;
			clear: both;
		}
	</style>
</head>
<body>
	<!--头部-->
    <header class="default_style">
    	<div class="logo">logo</div>
    </header>
    <!--导航-->
    <nav class="default_style">
    	<ul>
    		<li><a href="#"></a>首页</li>
    		<li><a href="#"></a>新闻动态</li>
    		<li><a href="#"></a>公司简介</li>
    	</ul>
    </nav>
    <!--内容-->
    <main>
    	<!--文章-->
    	<article class="default_style">
    		<section>
    			<hgroup>
    			    <h1>标题</h1>
    			    <h3>作者:jk</h3>
    			<hgroup>
    		</section>
    	</article>
        <!--侧边栏-->
        <aside>
        	<div class="default_style aside_div">
        		<span>侧边栏</span>
        	</div>
        </aside>
        <footer class="default_style">
        	尾部
        </footer>
    </main>
</body>
</html>
```



``` html
/*显示度量值*/
<meter min="0" max="10" value="2"></meter>
/*进度条*/
<progress value="30" max="100">
```

