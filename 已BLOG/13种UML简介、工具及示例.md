---
title: 13种UML简介、工具及示例 
tags: uml,13种,简介,工具及示例,用例图,类图,对象图,活动图,状态机图,通信图,顺序图,包图,部署图,组件图,交互总图,时间图,复合结构图.
grammar_cjkRuby: true
---

# 概要
UML(Unified Modeling Language ,统一建模语言或标准建模语言). UML图形有13种,UML规范用来描述建模的概念有，类（对象的）、对象、关联、职责、行为、接口、用例、包、顺序、协作，以及状态.一起细细品读下.

## 1.用例图(UseCase Diagram)
静态图.对系统的使用方式分类. 帮助开发团队以一种可视化的方式理解系统的功能需求。
元素关系包含有: 参与者,用例,子系统,关系(关联,泛化,包含,扩展,依赖,项目,注释)

这是用visio画用例图的界面截图:

![enter description here][1]

这是一个示例图: 


![enter description here][2]

参考文章: 
http://www.cnblogs.com/heyongjun1997/p/5692310.html


## 2.类图 (Class diagram)
静态图.显示类和它们的相互关系.
关系: 泛化（Generalization）,  实现（Realization），关联（Association)，聚合（Aggregation），组合(Composition)，依赖(Dependency)

**泛化**（Generalization）:一种继承关系
![enter description here][3]

**实现**（Realization）: 类是接口所有特征和行为的实现
![enter description here][4]



**关联**（Association) :一种拥有的关系，它使一个类知道另一个类的属性和方法
![enter description here][5]

**聚合**（Aggregation）:是整体与部分的关系，且部分可以离开整体而单独存在
![enter description here][6]

**组合**(Composition):是整体与部分的关系，但部分不能离开整体而单独存在.
  如公司和部门是整体和部分的关系，没有公司就不存在部门.
  组合关系是关联关系的一种，是比聚合关系还要强的关系.
![enter description here][7]

**依赖**(Dependency): 是一种使用的关系，即一个类的实现需要另一个类的协助，所以要尽量不使用双向的互相依赖
![enter description here][8]

UML综合示例图
![enter description here][9]


工具示例,staruml:
![enter description here][10]


参考文章: http://www.open-open.com/lib/view/open1328059700311.html

## 3.对象图(Object Diagram) 
静态图.对象图只显示对象及它们的相互关系
概述:
![enter description here][11]

和类图对比:
![enter description here][12]

对象图示例:
![enter description here][13]

![enter description here][14]


参考文章: http://blog.csdn.net/shan9liang/article/details/6712867

## 4.活动图(Activity Diagram）
动态图.显示人或对象的活动，其方式类似于流程图
包含有: 初始节点(开始),最后一个节点(结束),活动,,转换,判定(决策), 同步条,分岔或汇合,泳道等

**开始/结束** 实心圆表示初始节点，圆圈内加一个实心圆来表示活动终点
![enter description here][15]

**活动** 最主要的元素之一，它用来表示一个活动
![enter description here][16]

**转换** 当一个活动结束时，控制流就会马上传递给下一个活动节点，在活动图中称之为“转换”，用一条带箭头的直线来表示
![enter description here][17]

**决策** 分支是用菱形表示的，它有一个进入转换（箭头从外指向分支符号），一个或多个离开转换（箭头从分支符号指向外）。而每个离开转换上都会有一个监护条件，用来表示满足什么条件的时候执行该转换 	

![enter description here][18]

**同步条**
![enter description here][19]


**分岔或汇合** 分叉用于将动作流分为两个或者多个并发运行的分支，而汇合则用于同步这些并发分支，以达到共同完成一项事务的目的。

![enter description here][20]


**对象流** 用活动图描述某个对象时，可以把涉及到的对象放置在活动图中，并用一个依赖将其连接到进行创建、修改和撤销的动作状态或者活动状态上，对象的这种使用方法就构成了对象流

  ![enter description here][21]

**泳道**
![enter description here][22]

**活动图举例:** 
![enter description here][23]
**活动图-工具-Visio**
![enter description here][24]


| 流程图    |  活动图   |     |     
| --- | --- | --- | --- |
| 描述处理过程    |   描述对象的活动顺序  |     |     
|  控制结构：顺序，分支，循环   |  控制结构：对象的动作行为决定。   |     |     
|    面向过程 |   面向对象  |     |     
|    不可以描述并发过程 |   可以描述并发过程  |     |     

参考文章:
http://www.cnblogs.com/finehappy/archive/2009/11/22/1608026.html
http://www.uml.org.cn/oobject/201409092.asp 
http://www.cnblogs.com/ywqu/archive/2009/12/14/1624082.html

## 5.状态机图(Statechart Diagram)
动态图.显示生命-周期比较有趣或复杂的对象的各种状态。
包括: 状态、状态表示法及状态机,转换.
**状态** : 是指在对象生命周期中满足某些条件、执行某些活动或等待某些事件的一个条件和状况。一个状态通常包括名称、进入/退出活动、内部转换、子状态和延迟事件 等五个部分组成
![enter description here][25]

**状态机** 是计算机科学理论的一部分，但UML中的状态机模型主要是基于David Harel所做的扩展，是用来展示状态与状态之间转换的图
**转换** 另一个则是在状态之间的、包含一些文字描述的有向箭头线，这些箭头线称为转换。 下图中红线箭头为转换.

![enter description here][26]

**转换五要素** ：
•源状态：即受转换影响的状态。
•目标状态：当转换完成后对象的状态
•触发事件：用来为转换定义一个事件，包括调用、改变、信号、时间四类事件
•监护条件：布尔表达式，决定是否激活转换
•动作：转换激活时的操作

![enter description here][27]


**复杂转换**

| 转换类型    |   描述  |    语法 |     |
| --- | --- | --- | --- |
|  外部转换   |  对事件做出响应，引起状态变化或自身转换，同时引发一个特定动作，如果离开或进入状态将引发进入转换、离开转换    |  事件 ( 参数 )[ 监护条件 ]/ 动作   |     |
|  内部转换   | 对事件做出响应，并执行一个特定的活动，但并不引起状态变化或进入转换、离开转换    |事件 ( 参数 )[ 监护条件 ]/ 动作	     |     |
|   进入转换  | 当进入某一状态时，执行相应活动|  entry/ 活动   |     |
|  退出转换  | 当离开某一状态时，执行相应活动 | exit/ 活动   |     |

只有动作描述，进入和退出和操作方法写在了里面
•进入和退出转换 ：当进入一个状态时，执行某个动作；或当退出某个状态时，执行什么动作。这时就可以使用进入和退出转换 来表示

•内部转换 ：用来处理一些不离开该状态的事件

**活动与延迟事件**
•活动：当对象处于一个状态时，它一般是空闲的，在等待一个事件的发生。但是某些时间，你可能希望描述个正在进行的活动。在处于一个状态的同时，对象做着某些工作，并一直继续到被某个事件中断

• 延迟事件：延迟事件是一种特殊的事件，它是指该事件不会触发状态的转换，当对象处于该状态时事件不会丢失，但会被延迟执行。例如，当E-mail程序中正 在发送第一封邮件时，用户下达发送第二封邮件执令就会被延迟，但第一封邮件发送完成后，这封邮件就会被发送。这种事件就属于延迟事件

符合状态表示法:
![enter description here][28]



状态图Visio:
![enter description here][29]


参考文章: http://www.cnblogs.com/sura/archive/2012/07/01/2572083.html

## 6. 通信图(Communication  Diagram)  
UML2.0之前叫协作图(Collaboration Diagram)
显示在某种情形下对象之间发送的消息。 协作图显示了一系列的对象和在这些对象之间的联系以及对象间发送和接收的消息
**作用**
1). 强调的是发送和接收消息的对象之间的组织结构。 
2). 说明系统的动态情况。 
3). 描述协作对象间的交互和链接，显示对象、对象间的链接以及对象间如何发送消息。 
4). 表示一个类操作的实现
**协作图中的要素**
![enter description here][30]

![enter description here][31]


**协作图中的关系**
![enter description here][32]

示例:
![enter description here][33]

画图工具: StarUML
![enter description here][34]

![enter description here][35]


参考文章: http://www.cnblogs.com/wolf-sun/p/UML-collaboration-diagram.html
http://blog.csdn.net/wuyuxing24/article/details/50885827

## 7.顺序图 (Sequence Diagram 时序图)
动态图.显示与通信图类以的信息，但强调的是顺序，而不是连接。
要素：活动者,对象,生命线,控制焦点,消息(同步消息,异步消息,返回消息,自关联消息)

1 活动者
2 对象
3 生命线
4 控制焦点
5 消息
 
 
 VISIO
 ![enter description here][36]

参考文章: http://www.cnblogs.com/xueyuangudiao/archive/2011/09/22/2185364.html
## 8.包图(Package Diagram)
显示相关的类如何组合，对开发人员有用。
包可直接理解为命名空间，文件夹，是用来组织图形的封装，包图可以用来表述功能组命名空间的组织层次Package之间的关系非常的简单，两个字，依赖，UML中依赖用带箭头的虚线表示。

•名称：每个包都必须有一个与其它包相区别的名称

•拥有的元素：在包中可以拥有各种其它元素，包括类、接口、构件、节点、协作、用例，甚至是其它包或图

 ![enter description here][37]
 
•包的可见性：
用“+”来表示“public”，
用“#”来表示“protected”，
用“-”来表示“private”

示例:
![enter description here][38]

包图-StarUML:

![enter description here][39]

参考文章: http://www.cnblogs.com/fsjohnhuang/articles/2368470.html
http://blog.csdn.net/kimylrong/article/details/40043389

## 9.部署图(Deployment Diagram)
静态图.显示安装已完成系统的机器、过程和部署制品。用来显示系统中软件和硬件的物理架构。从部署图中，您可以了解到软件和硬件组件之间的物理关系以及处理节点的组件分布情况。使用部署图可以显示运行时系统的结构，同时还传达构成应用程序的硬件和软件元素的配置和部署方式。
**作用**
         一个UML部署图描述了一个运行时的硬件结点，以及在这些结点上运行的软件构件的静态视图。
         部署图显示了系统的硬件，安装在硬件上的软件，以及用于连接异构机器之间的中间件。
         创建一个部署模型的目的包括∶
　　• 描述系统投产的相关问题．
　　• 描述系统与生产环境中的其它系统间的依赖关系，这些系统可能是已经存在，或是将要引入的。
　　• 描述一个商业应用主要的部署结构。
　　• 设计一个嵌入系统的硬件和软件结构。
　　• 描述一个组织的硬件/网络基础结构。
**包含元素**
   **节点** :代表一个运行时计算机系统中的硬件资源。包括节点的表示，节点的分类，节点中的构件，节点属性，节点与构件。
   1)节点表示
 ![enter description here][40]
 2)节点分类
  2.1)处理器（Processor）:处理器是能够执行软件、具有计算能力的节点。 
 2.2) 设备（Device） :设备是没有计算能力的节点，通常情况下都是通过其接口为外部提供某种服务，例如打印机、IC读写器，如果我们的系统不考虑它们内部的芯片，就可以把它们看作设备
 
 3)节点中的构件
  当某些构件驻留在某个节点时，可以在该节点的内部描述这些构件. 示例如下2图.
 
 ![enter description here][41]
 
 ![enter description here][42]
 
  **连接** 部署图用连接表示各节点之间通信路径，连接用一条实线表示。对于企业的计算机系统硬件设备间的关系，我们通常关心的是节点之间是如何连接的，因此描述节点间的关系一般不使用名称，而是使用构造型描述
  
  ![enter description here][43]
	
![enter description here][44]

参考文章: http://blog.csdn.net/u010168160/article/details/19926715
http://blog.csdn.net/wangyongxia921/article/details/8250129
## 10组件图(Component Diagram)
静态图.显示可重用的组件（对象或子系统）及期接口。又称为构件图，它描述的是在软件系统中遵从并实现一组接口的物理的、可替换的软件模块。
构件图=构件（Component）+接口（Interface）+关系（Relationship）+端口（Port）+连接器（Connector）
在面向对象系统的物理方面进行建模要用到两种图：组件图和配置图。
包含的元素:组件（Component）->构件,接口（Interface,外部接口——端口,连接器（Connector）——连接件,依赖关系（Dependency）.
### 10.1 组件
　• 组件是定义了良好接口的物理实现单元，是系统中可替换的物理部件。
　• 组件代表系统的一个物理实现块，代表逻辑模型元素如类、接口、协同等的物理打包。
　• 构件通过它的提供接口和请求接口展现行为。
　• 由于在UML2.0中，构件是一种类，因此构件具有属性、操作和可见性。这些概念的含义与在类图中定义的是一样的，只是在这里把这些概念应用在构件上。

**组件的命名**
组件的名称有两种：简单名和路径名。并依据目标操作系统可以添加相应的扩展名，例如Java和dll。
**表示方式**
组件用一个左侧带有突出两个小矩形的矩形来表示。
![enter description here][45]
UML2.0如下: 
![enter description here][46]

UML2.0把构件分为基本构件和包装构件
• 基本构件注重于把构件定义为在系统中可执行的元素。
• 包装构件扩展了基本构件的概念，它注重于把构件定义为一组相关的元素，这组元素为开发过程的一部分。也即, 包装构件定义了构件的命名空间方面。在构件的命名空间中，可以包括类、接口、构件、包、用况、依赖（如映射）和制品。按照这种扩展，构件也具有如下的含义：可以用构件来装配大粒度的构件，方法为把所复用的构件作为大粒度构件的成分，并把它们的请求和提供接口连接在一起（简单理解：组件包含组件，组拼大组件）
**组件的种类**
• 配置组件（Deployment Component）：运行系统需要配置的组件，是形成可执行文件的基础--操作系统、JAVA虚拟机、DBMS；
• 工作产品组件（Work Product Component）：包括模型、源代码和用于创建配置组件的数据文件，它们是配置组件的来源--UML图、java类和数据库表；
执行组件（Execution Component）：在运行时创建的组件，是最终可运行的系统产生的允许结果--.net组件

### 10.2 接口（Interface）

• 接口（interface）接口由一组操作组成，它指定了一个契约，这个契约必须由实现和使用这个接口的构件的所遵循。
• 接口分提供接口和请求接口
把构件实现的接口称为提供接口（供接口），这意味着构件的提供接口是给其它构件提供服务的。实现接口的构件支持由该接口所拥有的特征，包括接口拥有的约束。
构件使用的接口被称为请求接口（需接口），即构件向其它构件请求服务时要遵循的接口
• 表示方式：
供接口用“棒棒糖”式的图形表示，即由一个封闭的圆形与一条直线组成。
需接口用“插座”式的图形表示，即由一个半圆与一条直线组成。
![enter description here][47]

![enter description here][48]

### 10.3 外部接口——端口
• 端口是UML2.0引入的概念
• 端口描述了在构件与它的环境之间以及在构件与它的内部构件之间的一个显示地交互点
• 端口是一个封装构件的显示的对外窗口，所有进出构件的交互都要通过端口。
使用端口能在更大的程度上增加构件的封装性和可替代性。
• 端口是构件的一部分，端口的实例随着它们所属的构件的实例一起被创建和撤消。
<1>接口与端口的关系
提供接口说明了通过端口来提供服务，请求接口说明了通过端口需要从其它构件获得服务。
一个构件可以通过一个特定端口同另一个构件通讯，而且通讯完全是通过由端口支持的接口来描述的。
<2>表示方式
尾部加小方框的正常接口表示，小方框就被称为端口。

![enter description here][49]


###  10.4 连接器（Connector）——连接件
**UML2.0提供两种类型的连接器**：
• 代理连接器（Delegation Connector）——委托连接件：连接外部接口的端口和内部接口。
• 组装连接器（Assembly Connector）——组装连接件：组件连接器表示构件之间的关系，它连接构件内部的类，将一个构件的供接口和一个构件的需接口捆绑在一起
• 连接端口意味着请求端口要调用提供端口中的操作，以得到服务。
• 立端口和接口的优点在于在设计时，两个构件彼此不需要了解对方的内部，只要它们的接口是相互兼容的即可。
• 如果一个端口提供一个特定的接口而另一个端口需要这个接口，且接口是兼容的，那么这两个端口-便是可连接的。

**1)组装连接件**
有两种表示装配连接件的方法：
•如果要显式地把两个构件实例衔接在一起，在它们的端口之间画一条线即可。
•如果两个构件实例相连是由于它们有兼容的接口，则可以使用一“球－穴”标记来表示构件实例之间的连接关系。 

装配连接件是两个构件实例间的连接件，它定义一个构件实例提供服务，另一个构件实例使用这些服务。装配连接件用于把一个请求接口或端口与一个提供接口或端口的连接起来。在执行时，消息起源于一个请求端口，沿着连接件传递，被交付到一个提供端口z

**2)委托连接件**
委托有这样的含义：具体的消息流将发生在所连接的端口之间，可能要跨越多个层次，最终到达要对消息进行处理的最终部件实例。这样，使用委托连接件可对构件行为的层次分解建模。
委托连接件把外部对构件端口的请求分发到构件内部的部件实例进行处理，或者通过构件端口把构件内部部件实例向构件外部的请求分发出去。
构件内部的一个部件可以是另一个构件或是一个类。注意，必须在两个提供端口间或两个请求端口间定义委托连接件。 

### 10.5 依赖关系（Dependency）
组件图用依赖关系表示各组件之间存在的关系类型。
在UML中，组件图中依赖关系的表示方法与类图中依赖关系相同，都是一个由客户指向提供者的虚线箭头。

![enter description here][50]

参考文章: http://blog.csdn.net/fanxiaobin577328725/article/details/51647248

## 11交互总图
使用顺序图喧赤活动的务个步骤。
### 11.1 协作图
**定义**
    它描述了系统中,对象间通过消息进行的交互,强调了对象在交互行为中承担的角色.
**作用**
    强调了交互发生时,每个对象承担的职责.
    可以显示对象相互协作时充当的角色
    用例显示对象之间如何进行交互
**元素**
    对象:在图中位置没有限制
    链
    消息:为了说明交互过程中消息的时间顺序,需要给消息添加顺序号.
	![enter description here][51]
	
	示例:
	![enter description here][52]
	
### 11.2 顺序图
**定义**
    用来描述为了完成某确定事务，对象之间按照时间顺序进行消息交互的图．
 
**目的作用**
    在项目的需求阶段，分析师能通过提供一个更加正式层次的表达，把用例带入下一层次。那种情况下，用例常常被细化为一个或者更多的序列图。
    组织的技术人员能发现，序列图在记录一个未来系统的行为应该如何表现中，非常有用。在设计阶段，架构师和开发者能使用图，挖掘出系统对象间的交互，这样充实整个系统设计。
 
**要素**
    顺序图的五要素是：活动者、对象、生命线、控制焦点、消息
        •生命线:对象存在的时间
        •控制焦点:表示这个时间对象将执行操作
        •消息:表示对象之间传输的信息
        •消息类型:
            调用(同步)消息
            异步消息
            返回消息
            阻止消息
            超时消息

![enter description here][53]
			
		
示例:
![enter description here][54]


 参考文章:http://blog.csdn.net/kwy15732621629/article/details/49702561

## 12时间图
显示消息和对象状态的准确时间限制。UML 时间图被用来显示随时间变化，一个或多个元素的值或状态的更改。也显示时控事件之间的交互和管理它们的时间和期限约束。
**状态生命线**
状态生命线显示随时间变化，一个单项状态的改变。不论时间单位如何选择，X轴显示经过的时间，Y轴被标为给出状态的列表。状态生命线如下所示：

![enter description here][55]

**值生命线**
值生命线显示随时间变化，一个单项的值的变化。X轴显示经过的时间，时间单位为任意，和状态生命线一样。平行线之间显示值，每次值变化，平行线交叉。如下图所示。

![enter description here][56]


**综合**
状态和值的生命线能叠加组合。它们必须有相同的X轴。 消息可以从一个生命线传递到另一个。每一个状态和值的变换能有一个定义的事件，一个时间限制是指一个事件何时必须发生，和一个期限限制说明状态或值多长时间必须有效。一旦这些已经被应用，其时间图可能显示如下。

![enter description here][57]


## 13复合结构图
显示对象在聚合或复合中的相互关系，显示接口和协作的对象.
**复合图**
复合结构图显示类元内部结构，包括它与系统其他部分的交互点。也显示各部分的配置与关系，这些部分一起执行类元的行为。
类元素已经在类图部分被详细地阐述，这部分用来说明类表现复合元素的方式，如：暴露接口，包含端口和部件。
 ![enter description here][58]

**部件**
 •部件是代表一组（一个或多个）实例的元素，这组实例的拥有者是一类元实例，例如：如果一个图的实例有一组图形元素，则这些图形元素可以被表示为部件，并可以对他们之间的某种关系建模。注意：一个部件可以在它的父类被删除之前从父类中被去掉，这样部件就不会被同时删除了。
 •部件在类或组件内部显示为不加修饰的方框。
 
 ![enter description here][59]
 
**端口** 	
•端口是类型化的元素，代表一个包含类元实例的外部可视的部分。端口定义了类元和它的环境之间的交互。端口显示在包含它的部件，类或组合结构的边缘上。端口指定了类元提供的服务，以及类元要求环境提供的服务。
•端口显示为所属类元边界指定的方框。

![enter description here][60]


**接口**
•接口与类相似，但是有一些限制，所有的接口操作都是公共和抽象的，不提供任何默认的实现。所有的接口属性都必须是常量。然而，当一个类从一个单独的超级类继承而来，它可以实现多个接口。
•当一个接口在图中单列出来，它既可以显示为类元素的方框，带 «interface» 关键字和表明它是抽象的斜体名称，也可以显示为圆环。
![enter description here][61]

•注意：圆环标注不显示接口操作。当接口显示为类所有的接口，它们会被当作暴露接口引用。暴露接口可以定义为是提供的，还是需求的。提供接口确认包含它的类元提供指定接口元素定义的操作，可通过类和接口间实现的连接来定义。需求接口说明该类元能与其他类元进行通信，这些类元提供了指定接口元素所定义的操作。需求接口可通过在类和接口间建立依赖连接来定义。
•提供接口显示为“带棒球体”，依附在类元边缘。需求接口显示为“带棒杯体”，也是依附在类元边缘。

![enter description here][62]

**委托**
委托连接器用来定义组件外部端口和接口的内部工作方式。委托连接器表示为带有 «delegate» 关键字的箭头。它连接组件的外部约定，表现为它的端口，到组件部件行为的内部实现。
![enter description here][63]


**协作**
•协作定义了一系列共同协作的角色，它们集体展示一个指定的设计功能。协作图应仅仅显示完成指定任务或功能的角色与属性。隔离主要角色是用来简化结构和澄清行为，也用于重用。一个协作通常实现一个模式。
•协作元素显示为椭圆。
![enter description here][64]

 **角色绑定**
•角色绑定连接器是一条从连接协作到所要完成该任务类元的连线。它显示为虚线，并在类元端显示作用名。
![enter description here][65]

**表现**
•表现连接器用于连接协作到类元来表示此类元中使用了该协作。显示为带关键字 «represents»的虚线箭头
![enter description here][66]

**发生**
•发生连接器用于连接协作到类元来表示此协作表现了（同原文）该类元；显示为带关键字«occurrence»的虚线箭头。
![enter description here][67]



  [1]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%94%A8%E4%BE%8B%E5%9B%BE-visio.png
  [2]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%94%A8%E4%BE%8B%E5%9B%BE.jpg
  [3]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-%E6%B3%9B%E5%8C%96.png
  [4]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-%E5%AE%9E%E7%8E%B0.png
  [5]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-%E5%85%B3%E8%81%94.png
  [6]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-%E8%81%9A%E5%90%88.png
  [7]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-%E7%BB%84%E5%90%88.png
  [8]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-%E4%BE%9D%E8%B5%96.png
  [9]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-%E5%90%88%E9%9B%86.png
  [10]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%B1%BB%E5%9B%BE-staruml.png
  [11]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%AF%B9%E8%B1%A1%E5%9B%BE-%E6%A6%82%E8%BF%B0%E4%BB%8B%E7%BB%8D.png
  [12]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%AF%B9%E8%B1%A1%E5%9B%BE-%E7%B1%BB%E5%9B%BE%E5%AF%B9%E6%AF%94.png
  [13]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%AF%B9%E8%B1%A1%E5%9B%BE-%E7%A4%BA%E4%BE%8B1.jpg
  [14]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%AF%B9%E8%B1%A1%E5%9B%BE-%E7%A4%BA%E4%BE%8B2.jpg
  [15]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E5%BC%80%E5%A7%8B%E5%92%8C%E7%BB%93%E6%9D%9F.png
  [16]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E6%B4%BB%E5%8A%A8.png
  [17]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E8%BD%AC%E7%A7%BB.png
  [18]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E5%88%A4%E5%AE%9A.png
  [19]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E5%90%8C%E6%AD%A5%E6%9D%A1.png
  [20]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E5%88%86%E5%B2%94-%E6%B1%87%E5%90%88.png
  [21]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E5%AF%B9%E8%B1%A1%E6%B5%81.png
  [22]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E6%B3%B3%E9%81%93.png
  [23]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-%E7%A4%BA%E4%BE%8B1.png
  [24]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%B4%BB%E5%8A%A8%E5%9B%BE-Visio.png
  [25]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%8A%B6%E6%80%81%E5%9B%BE-%E7%8A%B6%E6%80%81.png
  [26]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%8A%B6%E6%80%81%E5%9B%BE-%E8%BD%AC%E6%8D%A21.png
  [27]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%8A%B6%E6%80%81%E5%9B%BE-%E8%BD%AC%E6%8D%A22.png
  [28]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%8A%B6%E6%80%81%E5%9B%BE-%E5%A4%8D%E5%90%88%E7%8A%B6%E6%80%81%E6%A0%87%E7%A4%BA%E6%B3%95.png
  [29]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%8A%B6%E6%80%81%E5%9B%BE-Visio.png
  [30]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8D%8F%E4%BD%9C%E5%9B%BE-%E4%BA%8B%E7%89%A9%E5%90%8D%E7%A7%B0.png
  [31]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8D%8F%E4%BD%9C%E5%9B%BE-%E6%B6%88%E6%81%AF.png
  [32]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8D%8F%E4%BD%9C%E5%9B%BE-%E5%85%B3%E7%B3%BB.png
  [33]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8D%8F%E4%BD%9C%E5%9B%BE-%E7%A4%BA%E4%BE%8B.png
  [34]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-StarUML.png
  [35]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8D%8F%E4%BD%9C%E5%9B%BE-StarUML.png
  [36]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E9%A1%BA%E5%BA%8F%E5%9B%BE-Visio.png
  [37]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8C%85%E5%9B%BE-%E5%85%83%E7%B4%A0.png
  [38]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8C%85%E5%9B%BE-%E7%A4%BA%E4%BE%8B.png
  [39]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%8C%85.%E7%B1%BB%E5%9B%BE-StarUML.png
  [40]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E9%83%A8%E7%BD%B2%E5%9B%BE-%E8%8A%82%E7%82%B9.png
  [41]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E9%83%A8%E7%BD%B2%E5%9B%BE-%E6%9E%84%E4%BB%B6.png
  [42]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E9%83%A8%E7%BD%B2%E5%9B%BE-%E6%9E%84%E4%BB%B6-%E4%BE%8B%E5%AD%90.png
  [43]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E9%83%A8%E7%BD%B2%E5%9B%BE-%E8%BF%9E%E6%8E%A5.png
  [44]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E9%83%A8%E7%BD%B2%E5%9B%BE-%E7%A4%BA%E4%BE%8B.png
  [45]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%BB%84%E4%BB%B6%E5%9B%BE-%E7%BB%84%E4%BB%B6.png
  [46]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%BB%84%E4%BB%B6%E5%9B%BE-%E7%BB%84%E4%BB%B6UML2.0.png
  [47]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%BB%84%E4%BB%B6%E5%9B%BE-%E6%8E%A5%E5%8F%A3.png
  [48]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%BB%84%E4%BB%B6%E5%9B%BE-%E6%8E%A5%E5%8F%A3-2.png
  [49]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%BB%84%E4%BB%B6%E5%9B%BE-%E7%AB%AF%E5%8F%A3.png
  [50]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E7%BB%84%E4%BB%B6%E5%9B%BE-%E8%BF%9E%E6%8E%A5-%E4%BE%9D%E8%B5%96%E5%85%B3%E7%B3%BB.png
  [51]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E4%BA%A4%E4%BA%92%E5%9B%BE-%E5%8D%8F%E4%BD%9C%E5%9B%BE-%E5%85%83%E7%B4%A0.png
  [52]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E4%BA%A4%E4%BA%92%E5%9B%BE-%E5%8D%8F%E4%BD%9C%E5%9B%BE-%E7%A4%BA%E4%BE%8B.png
  [53]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E4%BA%A4%E4%BA%92%E5%9B%BE-%E9%A1%BA%E5%BA%8F%E5%9B%BE-%E5%85%83%E7%B4%A0.png
  [54]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E4%BA%A4%E4%BA%92%E5%9B%BE-%E9%A1%BA%E5%BA%8F%E5%9B%BE-%E7%A4%BA%E4%BE%8B.png
  [55]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%97%B6%E9%97%B4%E5%9B%BE-%E7%8A%B6%E6%80%81%E7%94%9F%E5%91%BD%E7%BA%BF.png
  [56]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%97%B6%E9%97%B4%E5%9B%BE-%E5%80%BC%E7%94%9F%E5%91%BD%E7%BA%BF.png
  [57]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E6%97%B6%E9%97%B4%E5%9B%BE-%E7%A4%BA%E4%BE%8B.png
  [58]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E5%A4%8D%E5%90%88%E5%9B%BE.png
  [59]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E9%83%A8%E4%BB%B6.png
  [60]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E7%AB%AF%E5%8F%A3.png
  [61]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E6%8E%A5%E5%8F%A3.png
  [62]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E6%8E%A5%E5%8F%A32.png
  [63]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E5%A7%94%E6%89%98.png
  [64]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E5%8D%8F%E4%BD%9C.png
  [65]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E8%A7%92%E8%89%B2%E7%BB%91%E5%AE%9A.png
  [66]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E8%A1%A8%E7%8E%B0.png
  [67]: https://raw.githubusercontent.com/bobshute/public/master/imgs/csdn/UML%E5%9B%BE/UML-%E5%A4%8D%E5%90%88%E7%BB%93%E6%9E%84-%E5%8F%91%E7%94%9F.png