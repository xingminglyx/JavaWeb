JSTL(JSP Standard Tag Library),JSP标准标签库。

JSTL用于简化JSP开发，提高代码的可读性与可维护性。

JSTL由SUN（Oracle）定义规范，由Apache Tomcat团队实现。

### JSTL 库安装

Apache Tomcat安装JSTL 库步骤如下：

从Apache的标准标签库中下载的二进包(jakarta-taglibs-standard-current.zip)。

- 官方下载地址：http://archive.apache.org/dist/jakarta/taglibs/standard/binaries/
- 本站下载地址：[jakarta-taglibs-standard-1.1.2.zip](http://static.runoob.com/download/jakarta-taglibs-standard-1.1.2.tar.gz)

下载 **jakarta-taglibs-standard-1.1.2.zip** 包并解压，将 **jakarta-taglibs-standard-1.1.2/lib/** 下的两个 jar 文件：**standard.jar** 
和**jstl.jar** 文件拷贝到 **/WEB-INF/lib/** 下。

将 tld 下的需要引入的 tld 文件复制到 WEB-INF 目录下。

接下来我们在 web.xml 文件中添加以下配置（如果可以运行则不需要添加）：

```
<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.4" 
    xmlns="http://java.sun.com/xml/ns/j2ee" 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/j2ee 
        http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd">
    <jsp-config>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/fmt</taglib-uri>
    <taglib-location>/WEB-INF/fmt.tld</taglib-location>
    </taglib>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/fmt-rt</taglib-uri>
    <taglib-location>/WEB-INF/fmt-rt.tld</taglib-location>
    </taglib>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/core</taglib-uri>
    <taglib-location>/WEB-INF/c.tld</taglib-location>
    </taglib>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/core-rt</taglib-uri>
    <taglib-location>/WEB-INF/c-rt.tld</taglib-location>
    </taglib>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/sql</taglib-uri>
    <taglib-location>/WEB-INF/sql.tld</taglib-location>
    </taglib>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/sql-rt</taglib-uri>
    <taglib-location>/WEB-INF/sql-rt.tld</taglib-location>
    </taglib>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/x</taglib-uri>
    <taglib-location>/WEB-INF/x.tld</taglib-location>
    </taglib>
    <taglib>
    <taglib-uri>http://java.sun.com/jsp/jstl/x-rt</taglib-uri>
    <taglib-location>/WEB-INF/x-rt.tld</taglib-location>
    </taglib>
    </jsp-config>
</web-app>
```

使用任何库，你必须在每个 JSP 文件中的头部包含 **<taglib>** 标签。

JSTL的五类标签库：
core 核心标签库，提供JSTL的基础功能
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
fmt 格式化输出标签库
sql SQL操作标签库
xml XML操作标签库
functions 函数标签库。

```
判断标签：
<c:if>用于单分支判断（没有与之匹配的else） eg：<c:if test="${score>60}"></c:if>

而<c:choose>、<c:when>（相当于if语句）、<c:otherwise>（相当于前面when条件不成立时才会执行）用于多分支判断，例：
${grade }
<c:choose>
<c:when test="${grade=='A' }">
<h2>你很优秀</h2>
</c:when>
<c:when test="${grade=='B' }">
<h2>还不错</h2>
</c:when>
<c:otherwise>
<h2>一切随缘</h2>
</c:otherwise>
</c:choose>
```

集合遍历：
<c:forEach>用于遍历集合的每一个对象
用法：
<c:forEach var="p"（把persons中的每一个对象放到p中） items="${persons}"（要被遍历的集合） varStatus="idx"（相当于下标索引）></c:forEach>

fmt格式化标签库：可以对日期进行精准的格式化
fmt格式化标签库 URL:http://java.sun.com/jsp/jstl/fmt
格式化日期标签
<fmt:formateDate value="" pattern="">
格式化数字标签
<fmt:formatNumber value="" pattern="">

<!-- pattern：格式
yyyy---4位年
MM-----2位月
dd-----2位日
HH-----24小时制
hh-----12小时制
mm-----分钟
ss-----秒数
SSS----毫秒
-->
<fmt:formatDate value="${requestScope.now }" pattern="yyyy年MM月dd日HH时mm分ss秒SSS毫秒"/>

<fmt:formateNumber value="" pattern="">格式化数字标签 
<fmt:formatNumber value="request.amt" pattern="0,000.00（保留两位小数，每三位数字之间用逗号隔开）">，会进行四舍五入。
core标签库中的out标签：
<c:out value="${nothing}（原始值）" default="无（设置的值）" escapeXml="true或false（设置是否进行转译）">。
