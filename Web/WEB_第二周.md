# CSS样式  
CSS：层叠样式表 Cascading Style Sheets，所谓层叠是指将整个网页想象为一层一层的结构，层次高的覆盖层次低的。  

**CSS优势**   

* 内容与表现分离  
* 页面的表现统一，容易修改  
* 丰富的样式，使得页面布局更加灵活  
* 减少网页的代码量，增加网页的浏览速度，节省网络带宽  
* 运用独立于页面的CSS，有利于网页被搜索引擎收录  

行内样式 内部样式 外部样式  

## CSS基本语法结构  
``` html
选择器{
	样式属性1:属性值;
	样式属性2:属性值;
}
body{
	background-color:aquamarine;/*设置背景颜色*/
}
h1{
	color: red;              /*设置字体颜色*/
	text-align: center;      /*设置字体居中*/
	font-size: 20;           /*设置字体大小*/
	font-family: "微软雅黑";  /*设置字体类型*/
	font-weight: 700;		 /*设置字体粗细*/
}
p{
	color:blue;
	border: 1px solid black; /*设置边框*/
}
a{
	color: #51A96E;
	text-decoration: none;   /*去掉文本下划线*/
}
```
### 选择器
类型选择器（标签选择器）：选择HTML相应的标签名作为选择器。  
类选择器：`.class`   
ID选择器：`#ID`  
通配符选择器：`*`表示当前页面所有的标签都共用该样式。  
包含选择器（后代选择器）：`#menu .test1`多个选择器之间用空格隔开  
选择器分组：创建由逗号隔开的多个选择器，可以将样式应用到单个选择器匹配的所有元素中  

##　CSS设置字体、文本样式  
### 字体样式   
font-family: "宋体";  
font-size: 50px;  三种单位： px 默认16px / 百分比 相对于父元素/em 相对于父元素  
font-style:   
font-weight: 100-900  
可以通过font属性依次设置 ： 字体风格 字体粗细 字体大小 字体类型  
font: italic bold 20px "微软雅黑";  
### 文本样式  
`color`  设置文本颜色  例如：`color:#00C;`  
`text-align`  设置元素水平对齐方式  例如：`text-align:right;`  
`text-indent`  设置首行文本的缩进  例如：`text-indent:20px;`  
`line-height`  设置文本的行高  例如：`line-height:25px;`  
`text-decoration`  设置文本的装饰（下划线等）  例如：`text-decoration:underline;`  
`letter-spacing`  字符间距  
**垂直方向：**  
`vertical-align:top`	顶端对齐  
`vertical-align:middle`	垂直居中  
`vertical-align:bottom`	底端对齐

## CSS设置超链接样式  
`a:link`         未单击访问时超链接样式      示例：`a:link{color:#9ef5f9;}`  
`a:visited`    单击访问后超链接样式          示例：`a:visited{color:#333;}`  
`a:hover`     鼠标悬浮其上的超链接样式   示例：`a:hover{color:#ff7300;}`  
`a:active`  鼠标单击未释放的超链接样式  示例：`a:active{color:#999;}`  
**注意：尽量不要在页面中加过多伪类**  

## CSS设置光标样式  


## CSS设置背景样式  
**设置背景样式** 
`background: url(img) #808080 no-repeat top center fixed;`  
子属性：  
`background-color`  
`background-image`  
`background-repeat`  
`background-position`  
`background-attachment`  
**设置背景图片的位置**  
`background-position:x y;`  

1. x代表水平位置 y代表垂直  
2. px ：0px 0px 代表在左上角 默认值  
3. x% y%：使用百分比设置图片位置  
4. top、center、bottom、left/right  ：right top 左上角  

## CSS设置列表样式  
无序列表常见属性：  
`list-style-image:url(图片地址)`用一张图片作为列表标记   
`list-style-tyep: none / disc  / circle / square`  
`list-style-type:`  
`decimal`	数字开头，默认值  
`decimal-leading-zero`  以零开头  
`lower-eoman`	小写罗马数字 i ii  
`upper-eoman`	大写罗马数字  
`lower-alpha`	小写英文字母  
`upper-alpha`	大写英文字母  

## CSS设置边框  
> `border-color`  设置边框颜色  
>> `border-top-color`  
>> `border-right-color`  
>> `border-bottom-color`  
>> `border-left-color`  

> `border-width`  设置边框的宽度  
>> `border-top-width`  
>> `border-right-width`  
>> `border-bottom-width`  
>> `border-left-width`  

`border-style`  设置边框线
`none` 无线    `dotted` 点线    `solid` 实线    `dashed` 虚线    `double` 双线  

使用border属性进行简写 边框宽度 》 边框的样式 》 边框的颜色  
`border:10px double blue;`  

`border-collapse:collapse;`	合并单元格  



