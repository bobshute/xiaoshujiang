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
**四大原则:**
1) 使用POJO进行轻量级和最小侵入式开发
2) 通过依赖注入和基于接口编程实现松耦合
3) 通过AOP和默认习惯进行声明式编程
4) 使用AOP和模板(Template)减少模块化代码
Spring所有功能的设计和实现都是基于以上四大原则的.
### 1.3.1 IOC
**控制反转:** (IOC-Inversion of Control)
**依赖注入:** (DI-dependency injection)
在Spring 环境下是等同的,控制翻转是通过依赖注入实现的. 依赖注入指的是容器负责创建对象和维护对象间的依赖关系,而不是通过对象本身负责自己的创建和解决自己的依赖.
**Spring Ioc容器**(ApplicationContext)负责创建 Bean,并通过容器精功能类 Bean注入到你需要的 Bean中。 spring提供使用 xml、注解、 Java配置、 groovy配置实现 Bean的创建和注入。
**元数据:**  包括  xml配置、注解配置和Java配置. 元数据本身不具备住何可执行的能力, 只能通过外界代码来对这些元数据行解析后通行一些有意义操作。Spring容器解析这些配置元数据进行 Bean初始化、配置和管理依赖。
***声明 Bean的注解**:*
o   @Component组件,没有明确的角色。
o   @service在业务逻輯层( service层)使用。
o   @Repository 在数据访问层( dao层)使用 。
o   @controller在展现层( MVC→Sprmg MVC)使用 。

***注入 Bean的注解, 一般情况下通用***
o   @Autowired: Spring提供的注解。
o   @Inject: JSR-330提供的注解。
o   @Resource: JSR-250提供的注解。

***常用注解举例***
o   @Configuration:表明当前类是一个配置类,这个意味着这个类里可能有0个或多个@Bean注解.

### 1.3.2 AOP
**AOP:**面向切面编程,相对于OOP面向对象编程.
AOP的目的是解耦,AOP让一组类共享相同的行为.在OOP中只能通过继承类和实现接口,来使代码的耦合度增强,且类继承只能为单继承,阻碍更多行为添加到一组类上,AOP弥补了OOP的不足.
Spring 支持AspectJ的注解切面编程.


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