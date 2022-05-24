---
layout: post
title: Jsp
description: Jsp
category: Servlet+Jsp
photos:
link: http://www.google.com/
tags:
---
# JSP(Jave Sever Page)

# 1 概念

* jsp:java  server pages  java服务器端页面
* 动态资源
* javaweb的13种技术规范之一 
* jsp解决的web问题：servlet的输出流拼凑页面太麻烦：jsp帮助你创建动态页面

> 深入理解： jsp本质就是个servlet
>
> 深入理解：jsp一般用于数据获取和结果显示  servlet一般用于处理数据和控制跳转
>
> 深入理解：jsp=html+java片段+jap标签

~~~html
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%><!-- jsp指令标签 -->
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>jsp_1</title>
</head>
<body>
    <!-- html注释 -->
    <%--jsp注释 --%>
    <h1>html代码</h1><!-- html代码-->
    
    <% System.out.println("我是java片段1");%><!-- java片段 1：jsp对应的servlet的service方法体-->
    <% int a=1,b=2; %>
    <%="我也是java片段2"%><!-- java片段 2：jsp对应的servlet的service方法体中通过字符输出流 打印数据到页面-->
    <br/>
    <%="a+b="+(a+b)%><!-- java片段2 --><br/>
    
    <%! 
        public static final int a=11; //java注释：：：定义一个成员变量
        public static int hehe(){
        	return (int)(Math.random()*10);
        }
    %><!-- java片段 2：jsp对应的servlet的成员变量和成员方法-->
    hehe()=<%=hehe() %><br/>
</body>
</html>
~~~

> jsp对应的servlet所在位置：通过tomcat的启动日志可以找到C:\Users\Administrator\Desktop\workspace\.metadata\.plugins\org.eclipse.wst.server.core\tmp0\work

![image-20210324152645764](https://i.loli.net/2021/03/24/FN3XhVgy7SZe5I4.png)

> 每个jsp对应一个servlet

![image-20210324152813480](https://i.loli.net/2021/03/24/COTHpVyK3PtZJN6.png)

> 此类是一个servlet类

![image-20210324152958075](https://i.loli.net/2021/03/24/dHMDmBXPkI4ZTlO.png)

> jsp中的html代码和注释 会通过response的输出流来输出到页面

![image-20210324153217392](https://i.loli.net/2021/03/24/Wfb8SRPqvX3HVz2.png)

![image-20210324153256642](https://i.loli.net/2021/03/24/Ss6xpLt1vTbK4qZ.png)

> java片段：<%! %>对应的是servlet的成员

![image-20210324153426289](https://i.loli.net/2021/03/24/qg4P27n3hcRNW1e.png)

![image-20210324153500759](https://i.loli.net/2021/03/24/A3XrfDJsdhTUVib.png)

> java片段：<%%>对应的是servlet的service方法的方法体中的代码

![image-20210324153639497](https://i.loli.net/2021/03/24/369dITVipJcBzON.png)

![image-20210324153709218](https://i.loli.net/2021/03/24/wlTSVkpPBMmvdue.png)

> java片段：<%= %>对应的是service方法体中通过response的字符输出流来拼凑页面的数据

![image-20210324153834050](https://i.loli.net/2021/03/24/ePkDqyAGj1NfCh7.png)

![image-20210324153910596](https://i.loli.net/2021/03/24/uo3MHkdNnGKlxw7.png)

# 2 jsp指令标签

~~~html
<%--
       jsp=java片段+jap标签+html
       jsp重点： 
          1：jsp标签=jsp指令标签+jsp动作标签
          2：jsp的九大内置对象
          3：el表达式：替换<%= %>
          4：jstl表达式：加强el表达式
     --%>
     <%int a=1; %><%--  <%java片段是在设置jsp对应的servlet的service方法的方法体 --%>
     <% a++; %>
     <%=a %><br/><%--  <%=java片段是在jsp对应的servlet的service方法中通过response的输出流out对象 拼凑页面的数据 --%>
     <%!public static int b=1; %><%--  <%!java片段 是在设置jsp对应的servlet的成员变量 --%>
     <%b++; %><%--方法体中使用成员变量 --%>
     <%--注意：尽量避免在jsp中设置成员变量：： --%>
     <%--
         jsp标签之jsp指令标签
                            指令标签：给当前jsp页面的属性设置
                            格式: <%@ 标签名   /%>                 
         1:page指令标签
         <%@ page 
             autoFlush="true"  :响应输出流是否自动刷新  
             buffer="8kb":响应输出流的缓冲区大小
             contentType="text/html; charset=utf-8":
             设置响应字符输出流的编码集为utf-8 等价于response.setCharacterEncoding("utf-8");
             设置页面的contentType响应头 等价于reposne.setContentType(text/html; charset=utf-8);
             pageEncoding="utf-8" 
             设置响应字符输出流的编码集为utf-8 等价于response.setCharacterEncoding("utf-8");
             errorPage="" :指定当前页面异常时 要跳转的页面
             extends="java.lang.Object"：指定此jsp对应的servlet要继承的父类
             info="作者：苗天宝"：指定此jsp的基本信息：版本  作者 时间
             isELIgnored="false"：是否屏蔽el表达式
             isThreadSafe="true"：是否线程安全
             isErrorPage="false"：是否为错误页面
             language="java"：其中的片段使用的语言
             session="true"：是否可用session
             trimDirectiveWhitespaces="false"：是否去除两边的空白字符
             %>
		 2:include指令标签:静态包含
		      <%@include file="1.txt" %>
		                 把1.txt文件中的所有代码复制到当前位置    ：实现页面代码的复用   
		 3: taglib指令标签：引入标签库
		      <%@ taglib  
		          prefix="c" :  指定引入的标签的前缀
		          uri="xxx"  :  指定引入的标签的路径
		      %>             
      --%>
~~~

# 3 jsp动作标签

![image-20210325104427140](https://i.loli.net/2021/03/25/3ql8mIRK7PiJOwL.png)

![image-20210325104458581](https://i.loli.net/2021/03/25/O9ZfGNijRnFx2Bo.png)

# 4 jsp的九大内置对象

~~~
 jsp的九大内置对象：jsp对应的servlet中service方法中可以直接使用的对象
     request:请求对象：HttpServletRequest :装与请求相关的所有内容
     1:获取请求参数
     2:获取请求头
     3:请求转发 请求包含
     4:域对象---同一个请求链之间的数据共享
     5:其他方法
     response:响应对象：HttpServletResponse :装与响应相关的所有内容
     1：设置响应头
     2：设置响应体
     3：重定向
     4：其他功能
     out:响应的字符输出流：PrintWriter：通过响应的getWriter方法获取
     conifg:servlet的配置信息： ServletConfig: web.xml中的配置信息
     session:回话对象：HttpSession:同一个浏览器对服务器发出的几个连贯的请求
     application:上下文对象：ServletContext: 实现整个项目之间的数据共享
     exception:异常对象：Throwable:  只有设置了 isErrorPage=true的jsp才有此对象
     page:this：HttpServlet：当前servlet对象
     pageContext:当前页面的上下文对象:PageContext
~~~

* PageContext的作用

~~~ java
//pageContext：
//1 作为域对象：当前jsp页面： 使用场景：当前jsp与当前jsp引入的标签库之间实现数据共享
//pageContext.setAttribute("ww", "ww_pageContext");
//request.setAttribute("ww", "ww_request");
//session.setAttribute("ww", "ww_session");
application.setAttribute("ww", "ww_application");
out.print("pageContext.getAttribute(ww)="+pageContext.getAttribute("ww")+"<br/>");

//2 全域查找：从小到大找：pageContext-request-session-application
//Object findAttribute(xxx);
out.print("pageContext.findAttribute(ww)="+pageContext.findAttribute("ww")+"<br/>");

//3 获取其他八大内置对象
//xxx pageContext.getXxx()
out.print((request==pageContext.getRequest())+"<br/>");
out.print((session==pageContext.getSession())+"<br/>");
out.print((out==pageContext.getOut())+"<br/>");

//4代理其他域对象
//代理其他域设置域属性
pageContext.setAttribute("hh", "hh_request", PageContext.REQUEST_SCOPE);
//代理其他域获取域属性
out.print("pageContext.getAttribute(hh,PageContext.REQUEST_SCOPE)="+pageContext.getAttribute("hh",PageContext.REQUEST_SCOPE)+"<br/>");       
out.print("request.getAttribute(hh)="+request.getAttribute("hh")+"<br/>");
~~~

# 5 el表达式

~~~
el:expression language:表达式语言
   jsp2.0的规范
作用：简化jsp的书写  替换<%= %>
格式 ：${} 
使用范围：    html+js+自定义标签
使用场景：         
    1 操作域对象获取域属性 
    2 实现对象导航 
    3 操作集合  
    4 基本运算  
~~~

* 使用范围

~~~html
    <!-- 在html中使用el表达式 -->
     html没有运算能力：1+1=(1+1)<br/>
              使用java片段1：   1+1=<%=1+1%><br/>
              使用java片段2：   1+1=<%out.print((1+1));%><br/>
              使用el表达式：    1+1=${1+1}<br/>
    <div id="div1"></div> 
    <!-- 在js中使用el表达式 -->           
    <script type="text/javascript">
          document.getElementById("div1").innerText="1+1="+${1+1};
    </script> 
    <!-- 在jsp标签中使用el表达式 --> 
    <jsp:useBean id="stu" class="com.zhiyou100.web07jsp.Student" scope="page"/>
    <jsp:setProperty property="score" name="stu" value="${1+1}"/>
    score=<jsp:getProperty property="score" name="stu"/><br/>
~~~

* 使用场景

~~~html
 <!-- 作用1：操作域对象 -->
    <%
        //pageContext.setAttribute("aa", "aa_page");
        pageContext.setAttribute("aa1", "aa1_page");
	    //request.setAttribute("aa", "aa_request");
	    request.setAttribute("aa2", "aa2_request");
	    session.setAttribute("aa", "aa_session");
	    session.setAttribute("aa3", "aa3_session");
	    application.setAttribute("aa", "aa_application");
	    application.setAttribute("aa4", "aa4_application");
    %>
    pageContext.aa1=<%=pageContext.getAttribute("aa1")%><br/>
    pageContext.aa1=<%out.print(pageContext.getAttribute("aa1"));%><br/>
    pageContext.aa1=${pageScope.aa}<br/><!-- 指定域 -->
    aa=${aa}<br/><!-- 全域查找 -->
    
    <!-- 作用2：基本的运算 
		    算术型：+、-（二元）、*、/、div、%、mod、-（一元）
			逻辑型：and、&&、or、||、!、not
			关系型：==、eq、!=、ne、<、lt、>、gt、<=、le、>=、ge
			空判断：empty 空操作符是前缀操作，可用于确定值是否为空。
			条件型： A ?B :C。根据 A 赋值的结果来赋值 B 或 C。
    -->
    5/3=${5/3}=${5 div 3}<br/>
    5%3=${5%3}=${5 mod 3}<br/>
    1>3=${1>3}=${1 gt 3}<br/>
    1>=3=${1>=3}=${1 ge 3}<br/>
    1==2=${1==2}=${1 eq 2}<br/>
    
    ""是空的吗?${ empty " "}<br/>
    "1"是不是不为空的吗?${ not empty "1"}<br/>
    1&gt;2 并且 1&lt;3 吗？${1>2 &&  1<3}<br/>
    1>2?3:4====${1>2?3:4}<br/>
    
    <% int a=11; %>
    a=<%=a %><br/>
    a=<% out.print(a);%><br/>
    a=${a}<br/><!--如果找不到不报错-->
    <% pageContext.setAttribute("a", a);%>
    a=${a}<br/><!--el表达式操作的变量必须是域属性-->
    
    
    <%--作用3：对象导航：如果对象a有getXxx方法 即可通过el表达式${a.xxx}调用此方法--%>
    <%
        Student ss=new Student(111,"韩梅梅",33.5f,1,new Date(),'女');
        pageContext.setAttribute("ss1", ss);
    %>
    <jsp:useBean id="sss" class="com.zhiyou100.web07jsp.Student" scope="page"/>
    <jsp:setProperty property="sid" name="sss" value="222"/>
    <jsp:setProperty property="sname" name="sss" value="韩庚"/>
    <jsp:setProperty property="score" name="sss" value="34"/>
    <jsp:setProperty property="tid" name="sss" value="1"/>
    <jsp:setProperty property="sex" name="sss" value="男"/>
    ss=${ss1}<br/>
    sss=${sss}<br/>
    名字=${ss1.sname}<br/><!-- 调用ss这个域属性对应的对象中的getSname方法 -->
    调用对象的getHaha方法=${ss1.haha}<br/>      
    <%-- a=${ss1.a}<br/> ss1对象中没有getA方法 报错--%>
    
    <!--作用4：操作集合 -->
    <%
        ArrayList<Student> list=new ArrayList<Student>();
        list.add(new Student(11111,"韩梅11",33.1f,1,new Date(),'女'));
        list.add(new Student(11112,"韩梅12",33.2f,1,new Date(),'女'));
        list.add(new Student(11113,"韩梅13",33.3f,1,new Date(),'女'));
        list.add(new Student(11114,"韩梅14",33.4f,1,new Date(),'女'));
        
        Map<String,Student> map=new HashMap<String,Student>();
        map.put("a",new Student(111,"韩梅1",33.1f,1,new Date(),'女'));
        map.put("b",new Student(112,"韩梅2",33.1f,1,new Date(),'女'));
        map.put("1",new Student(1131,"韩梅3",33.1f,1,new Date(),'女'));
        map.put("a-1",new Student(111,"韩梅a-1",33.1f,1,new Date(),'女'));
        map.put("b-2",new Student(112,"韩梅b-2",33.1f,1,new Date(),'女'));
        map.put("c-3",new Student(1131,"韩梅c-3",33.1f,1,new Date(),'女'));
        
        //el只能操作域属性
        pageContext.setAttribute("list", list);
        pageContext.setAttribute("map", map);
    %> 
    list[0]=${list[0]}<br/><!--获取元素：list[下标]-->
    list[0].sname=${list[0].sname}<br/>
    
    map.a=${map.a}<br/>    <!--获取元素1：map.key-->
    map[1]=${map['1']}<br/><!--获取元素2：map['key']-->
    map.b=${map.b}<br/>
    map['b-2']=${map['b-2']}<br/>
~~~

# 6 el的11大内置对象

~~~
11个内置对象：(隐式对象)
           4个域对象：
	           pageScope:page域对象
	           requestScope:request域对象
	           sessionScope:session域对象
	           applicationScope:application域对象     
	                               注意：request和resuqestScope的区别   
	       2个操作请求参数：parameter
	           param:  获取单值请求参数
	           paramValues:获取多值请求参数
	       2个操作请求头：header
	           header:获取单值请求头
	           headerValues:获取多值请求头  
	       1获取cookie：
	           cookie: 
	       1获取初始化参数：
	           initParam
	                                 获取web.xml中的初始化参数
		           <context-param>
				      <param-name>encoding</param-name>
				      <param-value>UTF-8</param-value>
				   </context-param>
	       1 pageContext
~~~

* 代码

~~~html
<%
   //添加cookie到响应头中
   response.addCookie(new Cookie("c1","c1_value"));
   response.addCookie(new Cookie("c2","c1_value"));
   response.addCookie(new Cookie("c3","c1_value"));
   Cookie c=new Cookie("c4","c4_value");
   %>
<%
       //设置域属性
       pageContext.setAttribute("aa", "aa_pageContext");
       request.setAttribute("aa", "aa_request");
       session.setAttribute("aa", "aa_session");
       application.setAttribute("aa", "aa_application");
 %>
    pageContext.aa=<%=pageContext.getAttribute("aa") %><br/>
    pageContext.aa=<%out.print(pageContext.getAttribute("aa")); %><br/>
    pageContext.aa=${aa}<br/><!--全域查找-->
    <!-- 操作域对象 -->
    pageContext.aa=${pageScope.aa}<br/><!--指定域查找-->
    request.aa=${requestScope.aa}<br/><!--指定域查找-->
    session.aa=${sessionScope.aa}<br/><!--指定域查找-->
    application.aa=${applicationScope.aa}<br/><!--指定域查找-->
    <!-- 操作请求参数 -->
    单值请求参数：name=${param.name}<br/>
    多值请求参数：enjoy=${paramValues.enjoy[0]},${paramValues.enjoy[1]}<br/>
    <!-- 操作请求头 -->          
    客户端浏览器信息：${header['User-Agent']}  <br/>
    服务器端地址：${header['Host']}  <br/>
    <!-- 操作cookie --> 
    cookies:${cookie}<br/> 
    c1:${cookie['c1']}<br/> <!-- 获取cookie对象 -->  
    c1:${cookie['c1'].name}=${cookie['c1'].value}<br/> 
                            <!-- cookie对象有getName和getValue方法 -->  
    <!-- 获取项目的初始化参数 -->
    encoding=<%=application.getInitParameter("encoding") %><br/>
    encoding=${initParam.encoding}<br/> 
    <!-- pageContext --> 
    获取请求方式： <%=pageContext.getRequest().getMethod() %><br/>
    获取请求方式： ${pageContext.request.method}<br/><!--调用getReuqest方法  然后调用getMethod方法  -->
    id:${pageContext.session.id}<br/>
~~~

# 7 jstl

## 概念

~~~
JSTL:JSTL（Java server pages standarded tag library，即JSP标准标签库）
       Web开发人员一个标准通用的标签库，并由Apache的Jakarta小组来维护。
                    开发人员可以利用这些标签取代JSP页面上的Java代码，从而提高程序的可读性，
                    降低程序的维护难度。
     使用：1 先引入jar包：         jstl-1.2.jar+ standard-1.1.2.jar
          2 在要jsp页面中通过taglib来引入此标签库   
                 prefix="c" 标签的前缀
                 uri="http://java.sun.com/jsp/jstl/core"  标签库的位置
      JSTL标签库：含有五种标签
           sql---针对于数据库
           xml---xml解析
           fmt---格式化相关的方法
           functions--字符串操作的方法
           core---核心标签        
~~~

## fmt格式化包的使用

~~~html
     <f:setLocale value="zh_cn"/>  
     <f:formatNumber value="0.3" type="number"/><br />  <!-- 0.3 -->
     <f:formatNumber value="0.3" type="currency"/><br />   <!-- ￥0.30 -->
     <f:formatNumber value="0.3" type="percent"/><br />  <!-- 30% -->
~~~

## functions功能包的使用

~~~html
"1234abc"长度=${fn:length("1234abc")}<br/>
是否包含：${fn:contains("abc","ab") }<br/>
转换为大写：${fn:toUpperCase("abc123") }<br/>
转换为小写：${fn:toLowerCase("ABC123") }<br/>
判断参数1是否以参数2结尾：${fn:endsWith("abc1","1") }<br/>
判断参数1是否以参数2开头：${fn:startsWith("abc1","abc") }<br/>
获取参数1第一次出现参数2的位置：${fn:indexOf("abcabcabc","ab")}<br/>
<%
   String[] arr=new String[]{"1","2","a","b"};
   pageContext.setAttribute("arr", arr);
   request.setAttribute("stu", new Student());
%>            
    拼接数组： ${fn:join(arr,"-") } <br/> 
    获取子串： ${fn:substring("abcdefghijk",3,5) } <br/> 
    切割： ${fn:split("abcabcab123ac","ab") } <br/> 
    替换： ${fn:replace("abcabcab123ac","a","") } <br/>  
~~~

## core核心包的使用

~~~html
<!-- core核心标签库(重点) --> 
<!--1： url标签 -->
url标签作用1:<c:url value="/1.txt" /> <br/><!--给value指定的路径前加项目路径 --> 
<a href="demo02_el.jsp">跳转到demo02_el.jsp</a> <br/><!-- 相对路径  避免使用 -->
<a href="/java34_web/day07_jsp/demo02_el.jsp">跳转到demo02_el.jsp</a> <br/>
                     <!-- 相对路径  避免使用 -->
<a href="${pageContext.request.contextPath}/day07_jsp/demo02_el.jsp">
    跳转到demo02_el.jsp
</a> <br/><!-- 相对路径  避免使用 --> 
<a href="<c:url value='/day07_jsp/demo02_el.jsp'/>">
   跳转到demo02_el.jsp
</a> <br/><!-- 相对路径  避免使用 -->    
url标签作用2:<c:url value="/1.txt" var="u1"  scope="session"/> <!-- 在session域中添加一个名字为u1的属性 值为/java34_web/1.txt -->
${sessionScope.u1}<br/>

<!--2:set 在指定域中添加属性 
      等价于：setAttribute(xx,xx);-->
<c:set scope="session" value="aa_value" var="aa"/>
aa=${sessionScope.aa}<br/>
stu=${stu}<br/>

<!--3:out 输出域属性    
	value:指定属性名
	default:如果此域属性不存在  显示默认值
	escapeXml:是否对域属性值--特殊字符转换
	等价于：getAttribute(xx);-->
<c:set value="<script type='text/javascript'>alert(11);</script>" var="bbc"/>
aab=<c:out value="${aab}" default="啊哈哈" escapeXml="true"/><br/>
<%-- bbc=<c:out value="${bbc}" default="啊哈哈" escapeXml="false"/><br/>--%>
<!--4：remove 
	等价于：removeAttribute(xx,xx);-->
<c:set  value="aa_requset" var="aa" scope="request"/>
<c:set  value="aa_session" var="aa" scope="session"/>
<c:set  value="aa_page" var="aa" scope="page"/>
<c:set  value="aa_app" var="aa" scope="application"/>
<c:remove var="aa" scope="session"/><!-- 删除指定域中的aa属性 -->
<c:remove var="aa"/><!-- 删除所有域中的aa属性 -->
pageScope.aa=<c:out value="${pageScope.aa}"/><br/>
requestScope.aa=<c:out value="${requestScope.aa}"/><br/>
sessionScope.aa=<c:out value="${sessionScope.aa}"/><br/>
applicationScope.aa=<c:out value="${applicationScope.aa}"/><br/>

<!-- 5 if:单分支-->
<c:set var="age" value="11"/>
<c:if test="${pageScope.age ge 18}">
    age=${age}是成年人！<br/>
</c:if>
<c:if test="${pageScope.age lt 18}">
    age=${age}是未成年人！<br/>
</c:if>
<c:set var="name" value="hmm"/>
<c:if test="${empty pageScope.name}">
    name=${name}不能为空<br/>
</c:if>
<c:if test="${fn:length(pageScope.name) lt 8}">
    name=${name}长度不能小于8<br/>
</c:if>

<!-- 6 choose when otherwise：多分支 -->
<c:set var="score"  value="98"/>
<c:choose>
    <c:when test="${pageScope.score lt 60 and pageScope.score ge 0}">
        分数是${score}，级别是不及格<br/>
    </c:when>
    <c:when test="${pageScope.score lt 70 and pageScope.score ge 60}">
        分数是${score}，级别是及格<br/>
    </c:when>
    <c:when test="${pageScope.score lt 80 and pageScope.score ge 70}">
        分数是${score}，级别是良好<br/>
    </c:when>
    <c:when test="${pageScope.score lt 100 and pageScope.score ge 80}">
        分数是${score}，级别是优秀<br/>
    </c:when>
    <c:otherwise>
        分数是${score}，无效<br/>
    </c:otherwise>
</c:choose>

<!-- 7:foreach循环 -->
<!-- 从1跑到10 每次加2 变量名为a -->
<c:forEach var="a" begin="1" end="10" step="2">
    a=${pageScope.a}<br/>
</c:forEach>
<%
   int[] array={1,6,8,9,7,4,3,2,3};
   pageContext.setAttribute("array", array);
%>
    <c:forEach items="${pageScope.array}" var="n" varStatus="vs">
        第${vs.index+1}元素::::n=${n}<br/>
    </c:forEach>

<%
    Map<Integer,String> map=new HashMap();
    map.put(1, "1-1");map.put(2, "2-1");map.put(3, "3-1");map.put(4, "4-1");
    pageContext.setAttribute("map", map);
 %>
    <c:forEach items="${pageScope.map}" var="v" varStatus="">
        v=${v.key}:${v.value}<br/>
    </c:forEach>

<!-- 8:redirect重定向 -->
<c:redirect url="/day07_jsp/demo02_el.jsp"/>
~~~

# 1 创建数据库

~~~sql
CREATE TABLE `student` (
  `sid` int(11) NOT NULL AUTO_INCREMENT,
  `sname` varchar(11) DEFAULT NULL,
  `score` float(4,1) DEFAULT NULL,
  `stime` datetime DEFAULT NULL COMMENT '添加或者最后的修改时间',
  `tid` int(11) DEFAULT NULL COMMENT '添加或者最后的修改的老师编号',
  PRIMARY KEY (`sid`),
  KEY `kf_1` (`tid`),
  CONSTRAINT `kf_1` FOREIGN KEY (`tid`) REFERENCES `teacher` (`tid`)
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8
CREATE TABLE `teacher` (
  `tid` int(11) NOT NULL AUTO_INCREMENT,
  `tname` varchar(11) DEFAULT NULL,
  `tpwd` varchar(11) DEFAULT NULL,
  PRIMARY KEY (`tid`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8
~~~

# 2 创建 项目、分包、导入jar

![image-20210325164209105](https://i.loli.net/2021/03/25/eXa6DP9s8u5KBVg.png)

# 3 创建工具类

# 4 根据表创建实体类

# 5 为每个实体类创建dao

# 6 创建页面













