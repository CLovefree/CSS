# CSS
图解css——核心技术与案例实践

主要是本书的实战体验部分练习

## 第十章

text-transform: capitalize          **首字母大写**

cursor: pointer                            **指标变小手**

##### 线性渐变

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

#### 径向渐变

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
****

#### 重复渐变

重复渐变制作记事本纸张效果





			background-image: -webkit-repeating-linear-gradient(#669999,#666699 40px,#339999 80px,#669999 130px);
			background-image: repeating-linear-gradient(#669999,#666699 40px,#339999 80px,#669999 130px);









