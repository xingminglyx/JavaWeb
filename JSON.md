1.Json介绍 ：
1.JavaScript Object Notation（JavaScript对象表示法）
2.JSON是轻量级的文本数据交换格式
3.JSON独立于语言，具有自我描述性，更易理解。

2.json语法规则：
数据由键（key）/值（value）描述，由逗号分隔
大括号代表一个完整的对象，拥有多个键/值对
中括号保存数据，多个对象之间使用逗号分隔。

3.json与字符串的相互转化
JSON.parse()方法用于将字符串转换为json对象
JSON.stringify()方法将json对象转换为字符串

4.Calendar日历类 Calendar c=Calendar.getInstance();
c.set(2019,0,30,0,0,0)设置时间（分别为年，月，日，时，分，秒）
c.getTime()获取时间
String json = JSON.toJSONString(employee);将java对象转化成json字符串
@JSONField(format="yyyy-MM-dd HH:mm:ss")时间序列化注解
@JSONField(serialize=false)不对某一对象进行序列化
Employee employee = JSON.parseObject(json（Json形式的字符串）,Employee.class（要转换成的对象）);将json字符串转化为实例化的对象。

//json数组，保存多个对象
List emplist=new ArrayList();
for(int i=1;i<=100;i++) {
Employee employee = new Employee();
employee.setEmpno(4488+i);
employee.setEname("员工"+i);
emplist.add(employee);
}
String json = JSON.toJSONString(emplist);
System.out.println(json);

List<Employee> list = JSON.parseArray(json,Employee.class);
for(Employee e:list) {
System.out.println(e.getEmpno()+":"+e.getEname());
}
