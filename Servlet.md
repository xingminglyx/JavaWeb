软件发展史
1.单机时代
优点 安装简单，使用方便 ，结构简单
缺点 不易共享 不够安全
eclipse word
2.联机时代 cs架构 客户端 服务器
优点 数据共享方便，安全性高
缺点 必须要下载客户端 不易维护更新
支付宝 qq 微信
3.互联网时代 bs架构 浏览器 服务器
优点 方便快捷 开发简单 数据容易共享
缺点 执行速度，用户体验差一点
淘宝

bs的执行流程 成对出现
浏览器请求服务器 request
服务器响应浏览器 response

jse标准版
j2ee是企业版，十三个组件
web应用程序是j2ee的核心功能
常用 servlet jsp服务器页面 jdbc数据库交互(增删改查) xml 交互

apache tomcat 外部服务器程序免费开放源代码
j2ee和apache tomcat的关系
j2ee是规范和指南，实现看需求
tomcat是j2ee web(小程序servlet和jsp服务器页面)的标准实现者

servlet(applet)提供了软件实习，生成不同的网页

创建的servlet类都要继承HttpServlet类，要重写service(HttpServletRequest, HttpServletResponse)方法
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/46.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/47.jpg)
参数名1=值&参数名2=值2&参数名3=值3n
html form表单的action属性="端口文件地址"
request.getParameter();接收单个请求参数
request.getParameterValues();接收多个同名参数

get和post方法
get是将数据通过url附加数据显示向服务器发送数据
post 是隐藏向服务器发生数据
请求体：name=zhangsan
在action 属性添加 method="post" 隐藏地址栏sample 请求体发送

service是请求处理的核心方法 无论get和post都会被处理
service方法不区别对待
getmethod()获取方法
区别对待
doGet() 
doPost()
使用场景
doGet() 常用于不包含敏感词信息查询
doPost() 用于安全性较高的功能和服务器的写操作

servlet生命周期：
装载（Tomcat解析XML）此时Tomcat只是解析，并未对其做什么操作
创建 第一次访问的时候，创建servlet对象执行构造函数
初始化 调用init（）方法初始化
提供服务 service( )/doGet( )/doPost( )
销毁 tomcat关闭或重启的时候执行destory( )

使用了该注解，就可以不再web.xml中进行配置了
Servlet核心注解：@WebServlet("/url")
@WebServlet("/anno")

启动时加载：web.cml使用<load-on-startup>设置启动加载
<load-on-startup>0~9999</load-on-startup>（值越小优先级越高）
启动时加载在工作中常用于系统的预处理
或
在注解中设置：
@WebServlet(urlPatterns="/unused" , loadOnStartup=2),一定要设置url，不然注解不会生效。
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/48.jpg)
get请求方式的数据存放在Query String Parmeters中
post请求方式的数据存放在Form Data中。

String uesrAgent=request.getHeader("User-Agent")获得要获取的请求头（User-Agent客户端环境）
response.setContentType("text/html;charset=utf-8")输出中文。
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/49.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/50.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/51.jpg)
多个Servlet(JSP)之间跳转有两种方式：
1、request.getRequestDispatcher("要跳转的url映射地址").forward(request,response)请求转发（地址栏中的url地址不会变）
2、response.sendRedirect("/工程名字/要跳转的url映射地址")响应重定向（地址栏中的url地址会变成跳转后的url映射地址）。
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/52.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/53.jpg)
设置请求自定义属性：
设置请求属性：request.setAttribute(属性名（必须是字符串），属性值（任何有效的java对象）);
获取请求属性：Object attr=request.getAttribute（属性名）。

浏览器cookiecookie(小甜饼)是浏览器保存本地的文本内容
cookie常用于保存登陆，用户资料和小文本
cookie具有时效性，cookie内容会伴随请求发送给tomcat
对象。

创建cookie
Cookie cookie =new Cookie("user","admin");
response.addCookie(cookie);
获取cookie
Cookie[] cs = request.getCookies();
for(Cookie c:cs) {
System.out.println(c.getName()+":"+c.getValue());
}
设置cookie的有效期
cookie.setMaxAge(60*60*24*7);

cookie存储在客户端
session存储在服务器端
获取session对象
HttpSession session = request.getSession();
session.setAttribute("name", "张三");
//获取session属性
String name=(String)session.getAttribute("name");
response.setContentType("text/html;charset=utf-8");

session与浏览器绑定，并且把数据存储到Tomcat内存中的对象。每个浏览器的sessionId都不同
String sessionId=session.getId();
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/54.jpg)
一个Wed应用只会创建一个ServletContext对象
ServletContext对象随着Web应用启动而被自动创建。Web应用程序重启或者关闭则被销毁
ServletContext context=request.getServletContext();获取ServletContext全局对象
Java Web三大作用域对象：
HttpServletRequest请求对象
HttpSession用户会话对象
ServletContext web应用全局对象。

request.setCharacterEncoding方法用于将请求体中的字符集转换为UTF-8。(一定要写在post方法的第一行才会生效)

对于Tomcat8.x的版本，默认get请求发送中文就是UTF-8，不需要修改字符集
对于URIEncoding属性只需要在Tomcat7（包含）以前的版本中的servet.xml中Connector配置，8以上无需配置。

web.xml是servlet得配置描述文件

welcom-file是6个配置文件，如果有容易一个存在就会进行加载
url(/cookies/*)匹配前缀是cookies
url转参
localhost:8091/项目名/文件/参数值
getRequestURL().toString();获取url
lastIndexOf("/")+1 最后一次出现的位置
subString()截取

全局参数的配置
content-param标签定义全局参数
param-name
param-value
需要在servlet文件获取servletcontext对象
getinitparameter()获取初始化参数
getinitparamener()
修改方便

对404/500页面替换
xml配置
error-page标签
<error-code>报错数字
<location>现实页面
</error-code>
