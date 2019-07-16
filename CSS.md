1.外部样式表的连接：link rel="stylesheet" href="../CSS/index.css">

2.标签选择器：div{}；类选择器：class="name" .name{}；可以这样命名：class=“name1 name2”，class中的空格是为了给html标签同时赋予多个class类名。

3.设置颜色最好查找一下颜色表。

4.background-position要使用两个关键词来锁定位置，若只规定了一个值，则另一个值默认为50%。

5.文本样式：![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/9.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/8.jpg)

capitalize：首字母大写；uppercase：所有字母大写；lowercase：所有字母小写。

6.字体样式：![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/10.jpg)

italic是斜体字，是一种字体；oblique是倾斜显示。

7.列表样式：![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/11.jpg)

![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/12.jpg)

8.结构性伪类:![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/14.jpg)

first-child，选择的是父元素的第一个元素，如果是p:first-child，那么只有当第一个元素为<p>标签时样式才会生效。所以当第一个不为<p>时应该使用:first-of-type。

状态伪类：![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/13.jpg)

9.伪元素选择器：![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/15.jpg)

6.空格是子孙（后代）选择器，而>是子选择器，不选择孙以及之后的。

其他选择器：![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/16.jpg)

class是可以重复的，id是不可以重复的，id选择器格式为#id；*选择器是选中body里所有内容；逗号选择器可以同时设置几个选择器的样式；+找的是同一级的元素；

7.opacity:0.5(透明效果)

8.background-repeat 属性设置是否及如何重复背景图像。值：repeat：默认。背景图像将在垂直方向和水平方向重复。repeat-x:背景图像将在水平方向重复。repeat-y:背景图像将在垂直方向重复。no-repeat:背景图像将仅显示一次。inherit:规定应该从父元素继承 background-repeat 属性的设置。

9.transform: rotate(180deg);将该元素转180度。
