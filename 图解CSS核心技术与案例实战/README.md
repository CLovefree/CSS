problems：13.5动画不成功，待解决

# CSS

图解css——核心技术与案例实践

主要是本书的实战体验部分练习

## 第四章：CSS背景

background-color

background-image

background-repeat

background-position(0 0)//(0% 0%)//(left top)/*不加逗号*/

background-attachment:scoll//fixed

fixed一般运用在html和body标签上，其他标签达不到效果

background-origin：绘制起点   决定border-position的起始位置

- padding-box
- border-box
- content-box

background-clip:背景图片的显示范围

background-size：背景图片尺寸大小

- auto原始宽高
- length取具体的整数值如px
- persentage相对于元素的宽度来计算
- cover放大铺满整个容器但是会失真；同时一个设置position在center
- contain保持背景图的长款比例，放到宽度高度正好适应所定义背景容器区域

background-break：内联元素的背景图片进行平铺时的循环方式

- 浏览器支持力度低，一般不用

### 多背景属性

制作花边边框

## 第五章：CSS文本

text-shadow：制作3D立体文本

text-overflow：clip//ellipisis

实现文本溢出时显示省略标记。。。，需要

- overflow：hidden

- white-space：nowrap强制文本在一行显示

- text-overflow:ellipisis

- 定义容器宽度

  ​

text-transform:定义文本大小写

none(默认)uppercase(大写)lowercase(小写)capitalize(首字大小写)

word-spacing   词与词的间距

letter-spacing字符之间的间距

vertical-align文本的垂直对齐方向sub、supper、bottom、top、middle、text-bottom（行内文本底端对齐）

text-indent

white-space文字与文字之间的空白符间距*?*

text-shadow

## 第十章：CSS渐变

text-transform: capitalize          **首字母大写**

cursor: pointer                            **指标变小手**

###线性渐变

	.toTop{	
	background-image:-webkit-linear-gradient(to top ,orange,green);
	background-image: linear-gradient(to top ,orange, green);
		}
多色线性渐变

	.toLeftN-deg{
	background-image:-webkit-linear-gradient(-90deg,red,yellow,orange,green,blue,indigo,violet);
	background-image: linear-gradient(-90deg ,red,yellow,orange,green,blue,indigo,violet);
		}
自定义渐变

		.toRightN01{background-image:-webkit-linear-gradient(to right,
				rgba(255,0,0,0) 0%,
				rgba(255,0,0,0.8) 7%,
				rgba(255,0,0,1) 11%,
				rgba(255,252,0,1) 28%,
				rgba(0,234,255,1) 45%,
				rgba(255,0,198,0.8) 88%,
				rgba(255,0,198,0) 100%);
			background-image: linear-gradient(to right,
				rgba(255,0,0,0) 0%,
				rgba(255,0,0,0.8) 7%,
				rgba(255,0,0,1) 11%,
				rgba(255,252,0,1) 28%,
				rgba(0,234,255,1) 45%,
				rgba(255,0,198,0.8) 88%,
				rgba(255,0,198,0) 100%);
通过box-shadow多个阴影实现3D立体效果（两层阴影，且active状态阴影变化像移动效果）

### 径向渐变

box-sizing:border-box 　　不改变盒模型大小而改变padding和border

10.3.4  制作斑点纹理背景      ***帅***

制作圆形button

	background: -weblit-radial-gradient(circle at top center,#f28fb8,#e982ad,#ec568c);
				background: radial-gradient(circle at top center,#f28fb8,#e982ad,#ec568c);
	.item13{width: 400px;height: 300px;
			margin: 50px auto;
			border: 5px solid hsla(60,50%,80%,.8);
			background-image: -webkit-radial-gradient(farthest-side ellipse at 30% 75%,hsla(120,70%,60%,.9),hsla(360,70%,60%,.9));
			background-image: radial-gradient(farthest-side ellipse at 30% 75%,hsla(120,70%,60%,.9),hsla(360,70%,60%,.9));
			}

### 重复渐变

重复渐变制作记事本纸张效果

			background-image: -webkit-repeating-linear-gradient(#669999,#666699 40px,#339999 80px,#669999 130px);
			background-image: repeating-linear-gradient(#669999,#666699 40px,#339999 80px,#669999 130px);

## 第十一章：CSS变形

- 设置button的转缩放效果

### transform


- translate移动

- scale缩放

- rotate旋转

- skew倾斜

- matrix定义矩阵变形

### transform-origin

### transform-style

  属性值：flat和preserve-3d

### perspective

  查看者的位置，长度单位不接受百分比

  *激活3D空间！！！*

- 注意：transform-style属性和perspective属性都在父节点设置！！！

- .demo01{

      		.demo01{
      		/* -----------重点---------- */
      			transform-style: preserve-3d;
      			perspective: 700px;
      		}
      		数字越小，3D效果越明显！！！！！

    rotate逆时针是负数deg，Y轴朝外是正数

    __重点是分清XYZ轴__

### prespective()函数和prespective属性

    - 相同：可以激活一个3D空间
    - 不同点：prespective用在舞台元素上（变性元素们共同父元素）；prespective()函数就是用在当前变形元素，并且可以与其他的transform函数一起使用；


### perspective-origin

实际上设置X和Y轴，默认50% 50%，也就是center；

第一个长度值X轴：长度单位值，百分比或者left/right/center;

第二个长度值Y轴：长度单位值，百分比或top/center/bottom;

- __注意__

  perspective-origin属性必须定义在义父元素上，可就是与perspective的位置，两者一起使用！！！

### backface-visibility

  元素旋转背面是否可见

- visible和hidden


### CSS2D变形

##### translate(tx,ty)

- ty为0 时可以省略不写；
- tx右为正值，ty下！！！为正值！

##### scale（sx,sy）  

scale（1.5）和scale（1.5，1.5）  效果相同

##### rotate（a）a为正时顺时针

##### skew(ax,ay)

##### 2D矩阵（暂未学）

*可以实现水平翻转*

### 3D变形基本同理

## 第十二章CSS过渡

transition

步骤：

①默认样式中声明元素初始状态

②声明过渡元素最终样式状态

③在*默认样式*添加过渡函数，添加一些不同的样式

### 过渡子属性

transition-property：过渡的CSS属性（属性具有一个中点值才具备过渡效果）

transition-duration：过渡所需时间

transition-timing-function:制定过渡函数

transition-delay：延迟时间

*一个属性同时设置多个样式，用逗号隔开*

#### 过渡函数

- ease
- linear
- ease-in:渐显
- ease-out：渐隐
- ease-in-out
- 贝塞尔曲线cubic--bezier(P0,P1,P2,P3)可以借助互联网上的工具
- step（7，end）七个步骤，结束发生在最后一步

### CSS3触发过渡

- 伪类触发

：hover

：active

：focus

：checked

- 媒体查询触发：如根据设备宽度和方向改用样式
- JavaScript触发

### 技巧

- 几乎无限延迟的过渡（设置恢复状态的delay时间无限长，持续时间为0秒）

- 通过硬件加速过渡更加流畅（过渡动画有时并不流畅，会有滞后痕迹，如webkit问题。）

  解决方法：在transition后添加一行代码来启用硬件加速

  -webkit-transform:translate(0);

## 第十三章CSS动画

animation 

①使用关键帧声明一个动画

②在animation调用关键帧动画

| 值                         | 描述                      |
| ------------------------- | :---------------------- |
| animation-name            | 规定需要绑定到选择器的 keyframe 名称 |
| animation-duration        | 规定完成动画所花费的时间，以秒或毫秒计。    |
| animation-timing-function | 规定动画的速度曲线。              |
| animation-delay           | 规定在动画开始之前的延迟。           |
| animation-iteration-count | 规定动画应该播放的次数。            |
| animation-direction       | 规定是否应该轮流反向播放动画。         |
| animition-play-state      | 控制动画的播放状态               |
| animition-fill-mode       | 设置动画的时间外属性              |

1. 设置动画播放次数：正数或者可以带小数点；infinite无限次
2. 动画播放方向：normal向前播放；alternate偶数次向前，奇数次反向
3. 动画播放状态：running和paused
4. animition-fill-mode:none;forwards(结束后应用最后关键帧）；backward；both

 @keyframes  动画名称{

 from{}

persentage{}

to{}

}

*浏览器前缀添加在keyframes关键词前如：@-moz-keyframes*

```
div{

width:100px;

height:100px;

background:red;

position:relative;

animation:myfirst 5s linear 2s infinite alternate;

/* Firefox: */

-moz-animation:myfirst 5s linear 2s infinite alternate;

/* Safari and Chrome: */

-webkit-animation:myfirst 5s linear 2s infinite alternate;

/* Opera: */

-o-animation:myfirst 5s linear 2s infinite alternate;

}

@keyframes myfirst{
0%   {background:red; left:0px; top:0px;}

25%  {background:yellow; left:200px; top:0px;}

50%  {background:blue; left:200px; top:200px;}

75%  {background:green; left:0px; top:200px;}

100% {background:red; left:0px; top:0px;}
}

```

## 媒体特性和RWD

媒体特性Media Query能在不同的条件下使用不同的样式，使页面在不同终端设备下达到不同的渲染效果

 **@media 媒体类型 and（媒体特性）{你的样式}**

- @media screen and(max-width:480px){

  .ads{display:none}}


- min-width

- 结合使用:用and连接

  @media screen and (min-width:600px) and (max-width:900px){

  body{background-color:#f5f5f5;}

  }


- 在智能设备上，还可以根据屏幕尺寸设计相应样式或者调用相应样式文件

  <link rel="stylesheet" media="screen and (max-divice-width:480px)" href="iphone.css"/>


- not关键词：排除某种制定的媒体类型

  @media not print and(max-width:1200px){样式代码}

  样式代码将被使用在除打印设备和屏幕宽度小于1200培训的所有设备中


- only 关键词：

responsive Web Design响应式设计

特点 ：

- 网站必须简历灵活的网格基础
- 引用到网站的图片必须是可伸缩的
- 不同的显示风格，必须在Media Query上设置不同的样式

术语：

- 流体网络

- 弹性图片

- 媒体查询

- 屏幕分辨率

- 主要断点

  ​

## 嵌入Web字体

@font-face无需加任何浏览器前缀

@font-face{

font-family:     ;

src:

font-weight:

font-style:                 }

关键点：

①将各种格式字体上传到服务器，一直吃各种浏览器；

②在@font-face中显示指定自定义字体名称以及引用自定义字体的字体来源；

#### 声明字体来源

```css
@font-face {
	font-family: 'YourWebFontName';
	src: url('YourWebFontName.eot'); /* IE9 Compat Modes */
	src: url('YourWebFontName.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
             url('YourWebFontName.woff') format('woff'), /* Modern Browsers */
             url('YourWebFontName.ttf')  format('truetype'), /* Safari, Android, iOS */
             url('YourWebFontName.svg#YourWebFontName') format('svg'); /* Legacy iOS */
   }
```

（ 如何将字体转换成所有格式字体呢？

Fontsquirrel字体转换生成器

Codeandmore字体转换生成器）

### 将图标转换成web字体

