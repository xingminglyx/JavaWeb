JSP（全称Java Server Pages）：java服务器页面，由web服务器来执行
作用:：降低动态网页的开发难度
将java代码和HTML分离，降低了开发难度
jsp的本质就是servlet

jsp运行要求
1，可正常运行的Tomcat
2，所有jsp页面的扩展名必须是.jsp
3，jsp页面应该放在Web应用程序目录下

<%jsp代码块%>用于在JSP中嵌入Java代码
JSP声明构造块：JSP声明构造块用于声明变量或方法，语法：<%!声明语句%>
JSP输出指令：用于在JSP页面中显示java代码执行结果，语法：<%=java代码%>
JSP处理指令：用于提供JSP执行过程中的辅助信息，语法：<%@jsp指令%>
常用处理指令：<%@page%>定义当前JSP页面全局设置
<%@include%>将其他JSP页面与当前JSP页面合并
<%@taglib%>引入JSP标签库

<%@ page import="java.util.*" contentType="text/html; charset=utf-8" %> 中的contentType="text/html; charset=utf-8" 是使页面显示中文

jsp九大内置对象 面试经常
1.request 请求
2.response 响应
3.session 会话
4.out 输出对象printWriter
5.exception 应用异常 throwable
6.page 当前页面
7.config 应用配置 servletConfig
8.pageContext 页面上下文
9.applicant 应用全局 servletContext

内置对象的使用办法 
可以在java代码中直接调用
application本质就是servletcontext
pageContext中转站获取其他的内置对象

<%@ page contextType="text/html;charset=ytf-8" isErrorPage="true"%>声明当前jsp文件为专门显示错误的界面
exception.getMessage()'获取错误信息

getClass() 获取类
getSimpleName() 类名.
