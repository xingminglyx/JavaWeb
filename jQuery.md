1.jquery是一个轻量级js库，使用十分简单。
它的核心是选择器，用于获取页面元素。
提供了大量高效方法，开发速度大幅提高。

2.操作元素CSS属性：
css()----获取或设置匹配元素的样式属性
设置
$("a").css("color","red");
$("a").css({"color":"red","font-weight":"bold","font-style":"italic"});-----一次性设置多个
获取
var color=$("a").css("color");
addClass()---为每个匹配的元素添加指定的css类名
$("li").addClass("highlight");
$("li").addClass("highlight myclass");
removeClass()----从所有匹配的元素中删除全部或者指定的类
$("p").removeClass("myclass");
3.基本选择器![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/55.jpg)
4.层叠选择器![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/56.jpg)
5.属性选择器![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/57.jpg)
6.位置选择器![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/58.jpg)
7.表单选择器![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/59..jpg)
8.操作元素属性：传递一个参数表示获取，两个参数表示设置属性值
var href_attr=$("a[href*='163']").attr("href");
var href_attr=$("a[href='163']").attr("href","http://www.163.com");
一个选择器对应多个属性，获取属性值时只输出第一个属性的结果，设置的时候就没有这么麻烦，设置属性值的时候则会把所有选中的元素的属性值进行设置。
移除属性
$("a").removeAttr("href");

9.设置元素内容：
val()----获取或设置输入项的值
//设置参数，表示val更改属性值
$("input[name='uname']").val("administrator");
//不设置val参数，表示选择元素的输入内容
var v=$("input[name='uname']").val();
text()---获取或设置元素的纯文本
设置
$("span.myclass").text("粒粒皆辛苦");
如果文本内容出现标签，不进行转义,直接输出
获取
var text=$("span.myclass").text()；
只显示纯文本内容 如：hanna
html()---获取或设置元素内部的html
设置
$("span.myclass").html("粒粒皆辛苦");
获取
获取内部的html片段，标签符号也会显示。
text和html方法最大的区别是对于文本中的html标签是否进行转义。

10.事件处理方式：
jQuery常用事件
鼠标事件
click  鼠标单击
dbclick  鼠标双击
mouseenter  鼠标移入
mouseleave  鼠标移出
mouseover  鼠标在组件上移动的过程

键盘事件
keypress  键盘按下弹起的过程
keydown  某一个键按下
keyup  某一个键弹起

表单事件
submit  表单提交
change  表单的输入项内容发生变化
focus  表单某一个输入项获得焦点时
blur  失去焦点时

文档/窗口事件
load  文档加载事件
resize  文档或者窗口尺寸发生变化时
scroll  窗口滚动时
unload  窗口关闭或者窗口卸载时
绑定事件：on("click",function(){
}) 
绑定事件的简写形式：click(function(){
}) 
通过键盘事件的参数event，可以知道键盘的每个按键的编码。
