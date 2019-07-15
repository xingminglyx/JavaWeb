1.XML是可扩展标记语言，XML 以文件形式保存数据，没有预置的标签，标签自己定义
XML重在保存与传输数据，HTML用于显示信息
用途：
1.Java程序中XML作为配置描述文件
2.用于保存程序产生的数据（XML是非常好的数据载体）
3.网络间的数据传输

2.a.第一行必须是XML声明
b.有且只有一个根节点
c.XML标签的书写规范与HTML不同
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/37.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/39.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/38.jpg)
3.DTD
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/40.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/41.jpg)
employee一定要与后面的括号隔开一个空格
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/42.jpg)
在xml中引入dtd
格式<!DOCTYPE 根节点 SYSTEM "dtd文件路径">
在DTD 中，对XML标签元素的属性的约束，通过 ATTLIST 来进行声明，语法是<!ATTLIST 元素名称 属性名称 属性类型 默认值>

4.Schema
Schema比dtd更复杂 高级的约束性语言
提供了数据类型 格式限定 数据范围等特性
Schema 是w3c标准
第一个声明根节点
包含子节点的时候必须要有<complexType></complexType>
引入在根节点开头的位置 xmlns：xsi="http://www.w3c.org/2001/XMLSchema-instance" xsi.noNamespaceSchemaLocation="hr.xsd">

5.DOM
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/43.jpg)
6.Dom4j
用于解析xml。应用于java平台。
将整个xml视为Document对象
xml标签被Dom4j定义为Element对象
String file="xml文件路径"；
SAXReader reader=new SAXReader();//SAXReader类是读取XML文件的核心类，用于将XML解析后以“树”的形式保存在内容中
Document document=reader.read(file);
Element root=document.getRootElement();//获取XML文档的根节点
List<Element> employees=root.elements("employee");//获取根节点下所有employee标签的集合
for(Element employee:employees){
Element name=employee.element("name");//element方法用于获取唯一的子节点对象
String empName=name.getText();//getText方法用于获取标签文本
( 或只写String empName=employee.elementText("name");//获取子节点name的文本)
Attribute att=employee.attribute("num");//获取节点属性
String attStr=att.getText();//获取属性值

Element employee=root.addElement("employee");//在根节点下创建一个employee子节点
employee.addAttrubute("num","3311");//在新加的employee节点中加入属性
Element name=employee.addElement("name");//在新加的employee节点中加入name子节点
name.setText("李四");//为name节点设置文本
//以上部分完成后只是在内存中构建了一个新的DOM树，但没有写入xml文件中，要想写入xml文件，还需要进行以下两步
Writer writer=new OutputStreamWriter(new FileOutputStream(file),"UTF-8");//创建输出流
document.write(writer);

7.XPath
XPath路径是XML文档中查找数据的语言，掌握XPath可以极大的提高在提取数据时的开发效率
XPath常用基本表达式：
nodename：选取此节点的所有子节点
/：从根节点选取
//：从匹配选择的当前节点选择文档中的节点，不考虑它们的位置
.：选取当前节点
..：选取当前节点的父节点
@：选取属性
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/44.jpg)
![image](https://github.com/xingminglyx/JavaWeb/blob/master/images/45.jpg)
