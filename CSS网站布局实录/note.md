### 高度自适应

- height：100%不起作用（需要设置父级元素高度）


- body,html{height:100%}兼容IE与Firefox

### 上下margin加倍问题

- 空白外边距叠加，以大的margin为准

- 某个元素设置float后将不再叠加

- 但IE6中设置float会出现外边距加倍，通过设置display:inline解决

### 清除浮动

- clear：left
- 需要另起一行则<div></div>；div{clear:both}

### 相对定位

保持与其原始位置相对，并不破坏原始位置的信息  