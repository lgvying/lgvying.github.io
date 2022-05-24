---
layout: post
title: Filter过滤器和Listener监听器
description: Filter过滤器和Listener监听器
category: Servlet+Jsp
photos:
link: http://www.google.com/
tags:
---
# Filter：过滤器

Filter:过滤器

​         和servlet使用起来非常一样

作用：

​        servlet:接受指定的请求  处理数据  给予响应

​         filter:拦截某一个或者某一类请求 选择是否放行

## 创建

### 1  实现接口：javax.servlet.Filter

> 实现其doFilter方法  选择实现init和destroy方法

~~~ java
package com.zhiyou100.web08_filter;
/*
 * filter的生命周期：参考servlet
 * */
public class Demo01Filter  implements Filter{
	{
		System.out.println("Demo01Filter--------构造代码块");
	}
	
	public void doFilter(ServletRequest arg0, ServletResponse arg1, FilterChain arg2)
			throws IOException, ServletException {
		System.out.println("Demo01Filter-------doFilter");
	}

	public void destroy() {
		System.out.println("Demo01Filter-----destroy");
	}
	public void init(FilterConfig filterConfig) throws ServletException {
		System.out.println("Demo01Filter-----init");
	}	
}
~~~

### 2 在web.xml中对filter配置

~~~ xml
<!-- 对过滤器：Demo01Filter配置 -->
<filter>
    <filter-name>f1</filter-name>
    <filter-class>com.zhiyou100.web08_filter.Demo01Filter</filter-class>
</filter>
<filter-mapping>
    <filter-name>f1</filter-name>
    <url-pattern>/day08/*</url-pattern>
    <!--
         <url-pattern>/day08/login</url-pattern>只拦截登陆请求
         <url-pattern>/day08/*</url-pattern>拦截虚拟目录为/day08的所有请求
         <url-pattern>*.action</url-pattern>拦截虚拟目录以.action结尾的所有请求
      -->
</filter-mapping>
~~~

### 3 测试

![image-20210326101031049](C:/Users/AppData/Roaming/Typora/typora-user-images/image-20210326101031049.png)



## 案例：编码集过滤器

### 1 在web.xml中定义初始化参数

![image-20210326101142632](https://i.loli.net/2021/03/26/Qfc9aBIpVeWYgsk.png)



### 2 创建过滤器

![image-20210326101240754](https://i.loli.net/2021/03/26/kqrJMsUE69lLRTZ.png)

### 3 配置过滤器 在web.xml中

![image-20210326101309372](https://i.loli.net/2021/03/26/Iqs281f6T9mQ7bd.png)

### 4 创建servlet：

![image-20210326101422106](https://i.loli.net/2021/03/26/kFEUZ7hcIfGnKJx.png)

### 5 创建jsp发出请求

![image-20210326101505000](https://i.loli.net/2021/03/26/PXJwO9VTvqBsYzC.png)

### 6 测试

控制台和页面都没有乱码：编码集过滤器起到作用

![image-20210326101704084](https://i.loli.net/2021/03/26/jPZJrni471xOpmI.png)

## 生命周期

* 创建对象：tomcat启动前 会创建过滤器Filter的单例对象
* 初始化：Filter对象一创建 tomcat就调用Filter对象的init方法对对象进行初始化
* 过滤请求：当tomcat接收到的请求 与Filter配置的url-pattern匹配时  请求就会被Filter拦截

​                        执行Filter对象的doFilter方法 在其中通过调用FilterChain的doFilter方法来放行

* 销毁对象：当tomcat关闭之前 会调用Filter对象的destroy方法 来销毁对象 释放资源

## 过滤器作用

* 共同代码的提取
* 访问权限的控制
* request和response对象功能的加强

# listener监听器

Listener:监听指定事件  事件发生就执行对应的代码

分类：属性监听器+生死监听器

​            属性监听器----监听指定域对象中域属性的增删改

​            生死监听器----监听指定域对象的创建和销毁

## 属性监听器

### request域属性监听器

~~~ java
@WebListener
public class Demo03AttributeListener  implements javax.servlet.ServletRequestAttributeListener{
	{
		System.out.println("Demo03RequestAttributeListener---属性监听器创建了");
	}
	public void attributeAdded(ServletRequestAttributeEvent srae) {
		    System.out.println("ServletRequest：-添加属 性:"+
                               srae.getName()+"="+srae.getValue());
	}

	public void attributeRemoved(ServletRequestAttributeEvent srae) {
		    System.out.println("ServletRequest：----删除属性:"+
                               srae.getName()+"="+srae.getValue());
	}
	public void attributeReplaced(ServletRequestAttributeEvent srae) {
		  System.out.println("ServletRequest：------修改属性:"+
                             srae.getName()+"=旧值为"+srae.getValue()
		  +",新值为："+srae.getServletRequest().getAttribute(srae.getName()));
	}
}
~~~

### session属性监听器类似

> 实现接口：javax.servlet.http.HttpSessionAttributeListener
>
> 有三个方法分别监听 属性的增删改

### application属性监听器类似

> 实现接口：javax.servlet.ServletContextAttributeListener
>
> 有三个方法分别监听 属性的增删改

## 生死监听器

### request生死监听器

~~~java
@WebListener
public class Demo04LifeListener  implements  javax.servlet.ServletRequestListener{
	public void requestDestroyed(ServletRequestEvent sre) {
		HttpServletRequest req=(HttpServletRequest)sre.getServletRequest();
		System.out.println("request死监听：：："+req.getParameter("id"));
	}
	public void requestInitialized(ServletRequestEvent sre) {//流量统计
		System.out.println("request生监听：：："+
                           sre.getServletRequest().getParameter("id"));
		HttpServletRequest req=(HttpServletRequest)sre.getServletRequest();
		System.out.println("getServletPath="+req.getServletPath());
		System.out.println("getQueryString="+req.getQueryString());
	}
}
~~~

### session生死监听器类似

> 实现接口：javax.servlet.http.HttpSessionListener
>
> 两个方法分别监听session的创建和销毁

### ServletContext生死监听器类似

> 实现接口：javax.servlet.ServletContextListener
>
> 两个方法分别监听servletContext的创建和循环
