### 背景图标居中：

	.link-travle .icon{background:#f00 url(images/travle.png) no-repeat center center;}
- 位置：距离左边 距离上边


- 而不用position属性！！！

### transform配合transition使用

- 同时注意浏览器兼容

### transition定义在div上，而不是div：hover

### 四条线

- 相对于父元素绝对定位，计算好长度和位置
- 注意border的影响
- 主要是判断初始位置和最终位置

### 设置两个class的优势

- 一个共性的，一个自身特性的

###子元素宽度不超过父元素

所以提示信息不能相对于link定位，而是相对box

### 三角形

- width和hight为0
- overflow：hidden
- 三角形的大小取决于border大小
- 向下的三角形定义border-top；向上的定义bottom

  border:7px solid transparent;
  border-top-color:#2bcd70;