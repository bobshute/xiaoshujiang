---
title: Spring Boot实战学习笔记
tags:Spring Boot实战
grammar_cjkRuby: true
---


# 1.Spring 基础
## 1.1 Spring 主要模块
### 1.1.1 核心容器(Core Container)
**Spring-Core**:核心工具类,Spring其它模块大量使用Spring-Core
**Spring-Beans**:Spring定义的Bean的支持
**Spring-Context**:运行时Spring容器
**Spring-Context-Support**:Spring容器对第三方包的集成支持
**Spring-Expression**:使用表达式语言在运行是查询和操作对象
### 1.1.2 AOP
**Spring-AOP**:基于代理的AOP支持
**Spring-Aspects**:基于AspectJ的支持.
### 1.1.3 消息(Messaging)
**Spring-Messageing**:对消息架构和协议的支持
### 1.1.4 Web
**Spring-Web**:提供基础的Web集成的功能,在Web项目中提供Spring的容器
**Spring-Webmvc**:提供基于Servlet的Spring MVC
**Spring-WebSocket**:提供WebSocket功能
**Spring-Webmvc-Portlet**:提供portlet环境支持.
### 1.1.5 数据访问/集成(Data Access/Integration)
**Spring-JDBC**: 提供以 JDBC访间数据库的支持
**Spnng-TX**: 提供编程式和声明式的事务支持
**Spnng-0RM**: 提供对对象/关系映射技术的支持
**Spring-0XM**:提供对对象/xml映射技术的支持:
**Spring-JMS**: 提供对 JMS的支持。
## 1.2 Spring 主要生态
[Spring.io 生态体系请点击查看][1]

##  1.3 Spring基础配置
四大原则:
1) 使用POJO进行轻量级和最小侵入式开发
2) 通过依赖注入和基于接口编程实现松耦合
3) 通过AOP和默认习惯进行声明式编程
4) 使用AOP和模板(Template)减少模块化代码



# 2.Spring 常用配置
# 3.Spring 高级话题
# 4.Spring mvc基础
# 5.Spring Boot基础
# 6.Spring Boot核心
# 7.Spring Boot的Web开发
# 8.Spring Boot的数据访问
# 9.Spring Boot的企业级开发
# 10.Spring Boot开发部署与测试
# 11.Spring 应用监控
Spring Boot有四大神器，分别是auto-configuration、starters、cli、actuator
# 12.分布式系统开发


  [1]: http://blog.csdn.net/bobshute/article/details/53221974