把加载js的代码放到页面的底部，避免先加载js代码时，还没有加载到html代码。建议以后也是把js代码放到页面的下边

1.js是一门脚本语言
提升功能、完善页面、动态页面(人机交互)
什么是bom？ 浏览器对象模型
什么是dom？ 文档对象模型

2.页面使用js(两种方法)
内部
<script type="text/JavaScript">
alert("单出文本框")
</script>
外部(实用)
<script type="text/JavaScript" src="js1.js">
</script>

3.js变量被称为弱数据类型，被赋什么值就是什么类型![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/20.jpg)

4.JS调试![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/21.jpg)

5.自定义函数![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/22.jpg)

6.数据类型![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/23.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/24.jpg)

7.强制类型转换![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/25.jpg)
如果字符变量前面是数字，后面是字符，如：123a，则parseInt(123a)和parseFloat(123a)会省略后面的字母，得到123，但是Number(123a)不会省略，得到NaN。
如果是null或""，前两个为NaN，后一个为0。有内容的转换为Boolean为true，没有的为false。（0也是false）

8.全局变量和局部变量![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/26.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/27.jpg)
程序控制语句
条件判断类控制语句
if(){
}else{
}
多条件分支类语句
var key=80
switch(key){
case 80：
alert("满分");
breck;
}
循环语句
while 先判断在执行
for 
do-while 先执行在判断
do{循环体}while(条件判断);

9.![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/28.jpg)

var str="dsadadadadasdadasdasdas"，首标为0
str.substr(a,b);从a位置开始截，截b个，a可以为负数，最后一个标记为-1，都是向后截取
str.substring(a,b);从a位置开始截，截到b位置，但不包含b位,当a或b为负数时，自动转化为0
str.indexOf(a);查找字符a在字符串str中第一次出现的位置，如果不存在返回-1
str.indexOf(a,b);从第b位开始查找，字符a第一次出现的位置
str.charAt(a);获取第a位上的值
str.length;获取str的长度
var arr[] = str.split(a);以字符a为介质，将字符串str分割，以数组的形式返回
str.concat(a);在原字符串的后面追加字符a
arr.concat(a,b,c);在原数组的基础上追加a,b,c三个元素
str.replace(a,b);将字符串str中第一次出现的a替换成b

数学函数：
var a = 16.6545854;
Math.round(a);四舍五入取整//17
a.toFixed(2);四舍五入，保留n位小数//16.65
Math.min(a,b,c,d)求a,b,c,d的最小值
Math.max(a,b,c,d)求a,b,c,d的最大值
以上两个方法如果参数是不能转换成数字的非数字值，则返回NaN。
Math.abs(-5);求绝对值
Math.random（）方法:
该方法返回的是一个大于等于0并且小于1的随机数，不是整数，故要获取1—10的随机整数，Math.random()*10 取到的是[0~10) 的数，floor(Math.random()*10)
向下取整，值为[0,9] ， Math.floor(Math.random()*10)+1 取值为 [1,10]
Math.ceil(Math.random()*10) 向上取整，取值为[1,10]
getMonth()的月份是0-11，所以在计算时还要加1；用getFullYear来获取年份，getYear现在不使用。getTime得到的是毫秒，一秒等于1000毫秒。

10.数组 常用 length
1.var arr=new Array(); 长度不指定的数组
2.有长度的数组 var arr2=new Array(5);
3.默认值的数组 var arr3=new Array(2,4,9,"j");
4.简写方法：var arr4=[4,6,5,9];
赋值
arr[0]=0;
遍历 高级循环 for in
for(var str in arr){循环体}

11.JS设置表单元素![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/29.jpg)

事件
onclick 点击事件 onclick="执行的函数,执行函数2";

onload属性设置在<body>里，设置的是刷新(加载，初始化)body之后在当前页面的内容显示的内容。
单选按钮 有共同的name
通过checked属性可以进行判断选项是否被选中。

列表框(三级联动)
select
options.add(new Option("1","1"));(value，列表里显示的部分)
yyyy.selectedIndex=...（通过元素下标设置下拉框中默认元素）
dd.option.length=0;(清空下拉元素，dd为列表框名)
dd.options.remove(1);将第二个元素删除，想循环删除整个列表元素时应该倒着删除，防止不匹配的效果产生。
onchenge 改变事件

12.事件![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/31.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/32.jpg)

事件设置：
1.在标签设置
2.在js设置
例如 document.getElementById("btn").onclick=functions(){
alert("匿名函数");
}

![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/30.jpg)

13.![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/33.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/34.jpg)
document dom模型 浏览器 
document.getElementById().value="999";
按id的名字来取值，使其value等于999。                        
获取名字 documemt.getElementsByName("name");
按name的名字来取值。
onmousedown / onmouseup 鼠标按下/抬起事件
keyCode 获取按下的是哪个按键
onkeydown / onkeyup 键盘按下/抬起事件
onfocus 获取焦点事件
鼠标事件
onmousleave 鼠标离开的时候
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/36.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/35.jpg)

14.在JavaScript中，下面6种值转化为布尔值时为false，其他转化都为true
1、undefined（未定义，找不到值时出现）
2、null（代表空值）
3、false（布尔值的false，字符串"false"布尔值为true）
4、0（数字0，字符串"0"布尔值为true）
5、NaN（无法计算结果时出现，表示"非数值"；但是typeof NaN==="number"）
6、""（双引号）或''（单引号） （空字符串，中间有空格时也是true）
15.setAttribute() 方法添加指定的属性，并为其赋指定的值。如果这个指定的属性已存在，则仅设置/更改值。
例子：设置 input 元素的 type 属性：document.getElementsByTagName("INPUT")[0].setAttribute("type","button");
