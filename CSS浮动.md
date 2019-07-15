div默认height为0，默认width为上一级元素的宽度。

1.overflow属性设置

![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/3.jpg)

2.outline属性：用于绘制元素周围的一条线，位于边框边缘的外围，起到突出元素的作用。               

属性值：dashed（虚线轮廓）；dotted（点状轮廓）；solid（实线）；double（双线）；none（不显示）。

3.border属性：border-(top,left,right,bottom)；属性值：solid（实线）；none（无边框）；double（双线边框）

4.![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/6.jpg)

padding的距离由哪里产生：

box-sizing属性的默认属性值为content-box：在宽度和高度之外绘制元素的内边距和边框。可以设定为border-box：已设定的宽度和高度分别减去边框和内边距才能得到内容的宽度和高度。

```
5.常见的行级元素（不独占一行）：<a><label><span><img><em
常见的块级元素（独占一行）：<div><p><h1-h6><li><table>
```

6.![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/7.jpg)

脱标流：就是将块状元素从左到右，从上往下。

7.

![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/8.png)float：inherit；继承父元素的浮动；

8.float的初衷：破坏性、崩溃、崩塌：将子元素设置为浮动之后，父元素在没有指定高度的情况下父元素的高度将不存在。

9.清除float：

清除浮动的主流写法（伪元素）：

#div_clear::after{
content:"";
visibility:hidden;
height:0px;
display:block;
clear:both;
}
IE：zoom：1；（解决一些IE里的一些BUG）![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/17.jpg)

box-shadow:水平阴影位置，垂直阴影位置，模糊的距离，阴影的尺寸，阴影的颜色(该属性可以用来设定图片背景边框)
span是行内元素，它占它自身大小的位置，而且不能设置宽高以及外边距
auto是块级元素才有效果，不定宽度相当于块级元素的宽度为100%，所以不会居中
