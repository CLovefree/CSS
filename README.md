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







