- 文档结构良好且有意义
- 分配类名和ID尽可能保持名称有意义并与表现方式无关
- ​

##第一章：基础知识

```
<link href="/css/basic.css" rel="stylesheet" type=text/css">
<style type="text/css">
<!--
@import url("/css/advanced.css");
-->
</style>
当老式浏览器不理解导入，可以隐藏他们不理解的复杂样式，而现实简单样式
```

也可以将一个样式表倒入另一个样式表，一般放在最前面，导入的样式表会被覆盖

```
@import url(/css/layout.css);
@import url(/css/color.css);
路径不带引号
```

大型站点简历样式指南

1. 首先概述站点结构、文件结构、命名约定
2. 详细描述布局和样式元素
3. 应给出任何特殊CSS样式说明和示例


组织样式表以便简化和维护：又要考虑到分割，又要考虑性能

## 第二章：可视化格式模型

浮动、定位、盒模型

#### 垂直空白边叠加：普通文档流

1. 行内框、浮动框或绝对定位框之间的空白边不会叠加
2. 一个在一个上面，一个包含另一个，空元素本身，都会发生

#### 定位概念

基本定位机制：普通流、浮动、绝对定位

行内元素可以使用水平填充、边框、空白便调整水平间距，但是垂直上不影响行内框高度！！！高度总是足以容纳它包含的所有行内框，但是设置行高可以增加框的高度！！！

##### 相对定位

元素仍占据原来空间

可看做普通流定位模型一部分

*相对于文档流中的初始位置*

##### 绝对定位

元素位置与文档流无关

不占据空间

*相对于最近的已定位的祖先元素*

##### 相对于相对定位的祖先元素对框进行绝对定位

最好对相对定位的框设置宽高，避免Windows上IE上的bug

##### 固定定位

解决IE低版本不支持的问题，可以用js实现

#### 浮动

浮动框不存在文档的普通流之中，文档在普通流的块框表现的像浮动框不存在一样

```
<div class="news">
<img src="news-pic.jpg>
<p>sdsfsdfsd</p>
</div>
```

##### 清除浮动

将img和p进行浮动，容器div就不能包围浮动元素，因为不占据空间，

解决办法：

1.添加一个空元素<div class="clear">,并清理它.clear{clear:both;}

2.将容器也进行浮动，但是对下一个元素会受到影响

3.应用值为hidden和auto的__overflow__属性会自动清理包含的任何浮动元素，而不需要添加额外的标记

```
<div class="news clear">...
同上
.clear:after{
contant:".";
height:0;
visibility:hideen;
display:block;
clear:both;}
```

4.Holly招数：解决IE和更低版本不起作用问题

## 第三章：背景图像和图像替换

##### 通过背景图像设置标题前面的符号图

```
h1{
padding-left:30px;
background:url(/images/buttlet.gig) no-repeat left center;}
```

##### 图像定位的单位

- 像素：图像左上角到元素左上角
- 百分比：图像距离左上角百分比到父元素上距离左上角百分比

**滑动门技术**

通过控制多层次的背景位置(左上、右上、左下、右下），内部填充使用repeat-y的重复背景

**山顶角技术**

不创建有颜色的角图像，而创建曲线型的位图角蒙版；蒙版区域盖住背景颜色，角区域透明

（虽然CSS3可以很好的实现圆角效果，但是灵活的技术概念会有很好的应用）

## 第四章：对链接应用样式

##### 下划线：通过bg重复图片repeat-x且定位实现生动的下划线效果

#####突出显示不同类型的链接

```
a[href^="http"]{
background:url(images/externallLink.gif) no-repeat right top;
padding-right:10px;
}
用属性选择器突出显示外部链接
a[href^="http://www.yousite.com"],[hres^-"http://yoursite.com"]{
background-image:none;
padding-right:0;
}
排除使用绝对定位的站内链接
```

突出显示可下载的文档和提要IE6 和更低不支持属性浏览器，可以加类或者ID用js和DOM实现。

#####Pixy样式翻转

```
a{...background:url() no-repeat left top;}
a:hover{background:url()no-repeat right top;}
但是Windows上IE会出现轻微闪烁，需要将翻转状态应用于链接的父元素
```

此方式可处理已访问链接样式和未访问链接样式a:visited

#####纯CSS的工具提示

```
<span>    </span>
a span{diaplay:none}
a:hover sapn{diaplay:block;position......}
```

## 第五章：对列表应用样式和创建导航条

```
<ul>
<li><a></a></li>
</ul>
对锚应用样式而不是列表li
结合pixy翻转技术
```

#### **导航条突出显示当前页面 ** 

1. 每个页面的主体元素添加一个id或者类名，如<body id="home">;<body  id="about">...

2. 在导航条的每一项加类名

3. 可以使用ID和类组合是被当前页面

```
#home #mainNav .home a,
#about #mainNav .about a,
#news #mainNav .news a,..{
    background-position:right bottom;
    color:#fff;
    cursor:defaule;}(鼠标经过被选中的链接光标不会改变）
```
##### 远距离翻转

在页面的其他地方触发显示方式的改变

方法：在锚链接内嵌套一个或者多个元素，然后使用绝对定位对嵌套元素进行单独的定位。<a><span></span><span></span></a>

结果：尽管显示在不同地方，但是其实都包含在同一个父锚中。因此当鼠标停留在一个元素时，可以影响另一个元素样式

## 第六章：对表单和数据表格应用样式



