1.Ajax介绍
Asynchronous JavaScript And XML
可以实现在不刷新页面的前提下，进行页面局部更新。

2.![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/60.jpg)

3.![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/61.jpg)

4.发送Ajax请求：
1.xmlhttp.open()用于创建请求
这里有三个参数：请求方式(post,get)，请求地址，是否异步（true是异步，false是同步，绝大多数是true）同步时，onreadystatechange会失效。
这里的请求地址和表单中的action类似，前面要有上下文（一般是工程名）路径
2.xmlhttp.send()用于发送请求。

5.处理服务器响应
xmlhttp.onreadystatechange()事件用于监听AJAX的执行过程
xmlhttp.readyState属性说明XMLHttpRequest当前状态![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/62.jpg)
xmlhttp.status属性服务器响应状态码，200：成功 404：未找到

响应的内容通常采用json的数据格式。![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/63.jpg)
