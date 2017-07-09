# CSS
图解css——核心技术与案例实践

主要是本书的实战体验部分练习

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

translate(tx,ty)

ty为0 时可以省略不写  ​

  ​







