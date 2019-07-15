# 一.HTML
1.html文件的扩展名可以为.html或.htm，通常设定为.html。

2.<p></p>自动换行，段落间添加空行，<br><!--换行但不添加空行-->。<!--....-->为注释。

3.<h1-h6>标签主要是为了给SEO优化，即关键词优化，为了使被搜索引擎更容易搜索进去。但<h1>不要过多，最好一个就够了。

4.图片<img src="" alt=""/>(src属性必写)标签路径问题：../ 表示从当前html文件所在位置返回上一级，这是相对路径的写法，从当前文件位置开始找图片位置，
如：../image/head/1.gif；绝对路径的写法就是从盘符出发来寻找，如：d:/image/head/1.gif。（上下两种写法效果相同）

5.超链接：<a href="">，a标签的target属性：_blank:在新打开、未命名的窗口打开链接；_parent:在父窗口打开链接；_self:在当前窗口打开链接；_top：top目标会
清除所有被包含的frame框架。
超链接的锚点：锚点必须先定义再使用。用法：用<a name=""></a>定义，用<a href="#..."></a>（打开同一个文件的一个位置）或<a href="文件名#..."></a>
（打开不同文件的一个位置）使用。

6.列表前的符号可以用type属性改变，属性值有‘a’，‘A’，‘i’，‘I’，‘1’，‘disc’，‘square’，‘circle’。

7.name属性是允许重复的，而id属性是唯一的不允许重复。

8.<a href="#">代表的是访问原页面，而且不刷新。

9.表单<form></form>；<input>里的type的属性值：text（单行文本框）；password（密码框，隐藏输入）；radio（单选框，name必须一样才会几个选一个）；
checkbox（复选框）；button（普通按钮）；submit（提交按钮）；file（上传文件）；hidden（隐藏文本框）
disabled属性：disabled="disabled"禁止文本输入。
列表框用<select><option></option></select>，可以用size属性设置列表框的长度。普通列表框用multiple属性值设为true可以进行复选，按住ctrl键点击即可。
多行文本框用<textarea></textarea>；用rows属性设置几行，cols属性设置几列。
input文本框内添加提示文字，填写内容时消失：用placeholder属性作为提示语。

10.控件的常用属性：name:指定控件的名称，可重复；id：指定标签的唯一标识；value：输入（收集、设置）控件的值；checked：复选框（单选）组默认被选中的项目；
selected：列表框组默认被选中的项目；src：图片框的图片来源；onclick：鼠标单击事件；disabled：禁用该控件；multiple：允许多选（适合普通列表框）。
