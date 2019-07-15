掌握el表达式的书写方法
1.什么是el表达式？
简化jsp的输出
el表达式格式
${
表达式
}
例：！<h1>学生姓名：${student.name}</h1>
requestScope() 后面的属性从哪取值
四种作用域对象
pagescope 从当前页面取值
requestscope 从当前请求中获取属性值取值
sessionscope 从当前会话中取值
applicationscope 当前应用全局中获取属性值
如果没有书写作用域对象，就会从小到大的去查找作用域的值

el表达式输出
语法${[作用域].属性名.[子属性]}
支持运算结果输出
支持大多数对象输出，本质是执行yostring()方法

el输出参数值
内置对象param
语法${param.属性}

优点，不用考虑导包和输出的问题，更方便维护
