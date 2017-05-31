---
title: JSON及fastjson 
tags: JSON,fastjson
grammar_cjkRuby: true
---


# 1.JSON
JSON(JavaScript Object Notation)

## 1.1JSON介绍及使用场景
JSON(JavaScript Object Notation)是轻量级的数据交换格式。具有良好的可读和便于快速编写的特性，可在不同平台之间进行数据交换。兼容性很高、完全独立于语言文本格式。
## 1.2 JSON优缺点(和XML对比)
### 1.2.1 XML优缺点

|XML|  优点 | 缺点  |     |
| --- | --- | --- | --- |
|     |   格式统一，符合标准  | 文件格式复杂,庞大，传输占带宽   |     |
|     |   容易与其他系统进行远程交互，数据共享比较方便  |  服务器端和客户端都<font color=red size=3>需要花费大量代码</font>来解析，导致两端代码复杂且不易维护 |     |
|     |     |   客户端不同浏览器之间<font color=red size=3>解析XML的方式不一致，需要重复编写</font>很多代码  |     |
|     |     |  服务器端和客户端解析XML<font color=red size=3>花费较多的资源和时间</font>  |     |

|   JSON  |  优点   | 缺点   |     |
| --- | --- | --- | --- |
|     |  数据格式比较简单，易于读写，格式都是压缩的，占用带宽小 |   没有XML格式广泛，没有XML那么通用性  |     |	
|     | 易于解析，客户端JavaScripteval()读取  |  JSON格式目前在Web Service中属于初级阶段   |     |
|     | 支持多种语言，服务器端语言，便于服务器端的解析 |     |     |
|     | 各种语言的转JSON工具多  |     |     |
|     | .服务器端和客户端通信容易 |     |     |




| 对比   | JSON    |XML     | 胜者  |
| --- | --- | --- | --- |
| 数据描述|好 |非常好| XML|
| 可读性 |易读|很易读  | XML |
| 数据交互|更方便|方便|JSON
| 数据体积| 小|大| JSON |
| 传输速度|快| 慢 |JSON|
| 编码/解码难度| 容易|容易|平 |
| 解释工具|丰富|丰富 | 平|
| 流行度|流行|很流行| XML|
| 可扩展| 容易|容易| 平 |

[查看参考地址][1]
# 2.java常用JSON转换工具
## 2.1 fastJSON
### 2.1.1 fastjson介绍

Fastjson是一个Java语言编写的JSON处理器。
1、遵循http://json.org 标准，为其官方网站收录的参考实现之一。
2、功能强大，支持java基本类型,JavaBean、Collection、Map、Date、Enum、泛型等。
3、无依赖，不需要例外额外的jar，能够直接跑在JDK上。
4、开源，使用Apache License 2.0协议开源。
### 2.1.2  jar

[仓库地址(1.2.29)][2]

#### 2.1.2.2 gradle build.gradle

````build.gradle
// https://mvnrepository.com/artifact/com.alibaba/fastjson
compile group: 'com.alibaba', name: 'fastjson', version: '1.2.29'
````
####  2.1.2.1 maven pom.xml
````pom.xml
<!-- https://mvnrepository.com/artifact/com.alibaba/fastjson -->
<dependency>
    <groupId>com.alibaba</groupId>
    <artifactId>fastjson</artifactId>
    <version>1.2.29</version>
</dependency>
````

### 2.1.3 代码示例

````FastJsonD.java
package cn.htmlv5.bobshute.je.open.json.fastjson;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

import com.alibaba.fastjson.JSON; 


public class FastJsonD {
 
	public static void main(String[] args) {
		mapAndJson1();		//map<-->JSON
		objectAndJson();	//Object<-->JSON
		listObjectAndJson();//List<VO><-->JSON
		listIntAndJson();	//List<Integer><---->JSON
	}
	
	//1.map<-->JSON
	public static void mapAndJson1(){
		HashMap<Object, Object> map = new HashMap<>();
		map.put("key1", "value1");
		map.put("key2", "value2");
		String jsonStr = JSON.toJSONString(map);
		System.out.println(jsonStr);	//{"key2":"value2","key1":"value1"}
		
		Map<String,String> mapFromJson = (Map<String,String>)JSON.parse(jsonStr);
		String value1 = mapFromJson.get("key1");
		String value2 = mapFromJson.get("key2");
		System.out.println("value1->"+value1+",value2->"+value2);	//value1->value1,value2->value2
		
		/**
		 key2:value2
		 key1:value1
		 */
		 for (String key : mapFromJson.keySet()) { 
             System.out.println(key+":"+mapFromJson.get(key)); 
     } 
	}
 
	//2.Object<-->JSON
	public static void objectAndJson(){
		UserInfo userInfo = new UserInfo();
		userInfo.setAge(30);
		userInfo.setName("name1");
		String jsonStr = JSON.toJSONString(userInfo);
		System.out.println(jsonStr);	//{"age":30,"username":"name1"}
		UserInfo userInfoFromJson = JSON.parseObject(jsonStr, UserInfo.class); 
		System.out.println("userInfoFromJson.getAge():"+userInfoFromJson.getAge()+",userInfoFromJson.getName():"+userInfoFromJson.getName());//userInfoFromJson.getAge():30,userInfoFromJson.getName():name1
	}
	
	//3.List<VO><-->JSON
	public static void listObjectAndJson(){
		UserInfo userInfo1 = new UserInfo();
		userInfo1.setAge(30);
		userInfo1.setName("name1");
		UserInfo userInfo2 = new UserInfo();
		userInfo2.setAge(20);
		userInfo2.setName("name2");
		List<UserInfo> userInfoList = new ArrayList<UserInfo>();
		userInfoList.add(userInfo1);
		userInfoList.add(userInfo2);
		String jsonStr = JSON.toJSONString(userInfoList);	 
		List<UserInfo> userInfoListFromJson= JSON.parseArray(jsonStr,UserInfo.class); 
		System.out.println("userInfoListFromJson.size()->"+userInfoListFromJson.size());	//userInfoListFromJson.size()->2
		
		for(UserInfo userInfoTemp:userInfoListFromJson){
			/*
			  userInfoTemp,age:30,name:name1
			  userInfoTemp,age:20,name:name2
			 */
			System.out.println("userInfoTemp,age:"+userInfoTemp.getAge()+",name:"+userInfoTemp.getName());
		}
	}
	
	//4.List<Integer><---->JSON
	public static void listIntAndJson(){
		List<Object> objectList = new ArrayList<Object>();
		objectList.add(1);;
		objectList.add("strobject");
		String jsonStr = JSON.toJSONString(objectList);	
		System.out.println("jsonStr->"+jsonStr);	//jsonStr->[1,"strobject"]
		
		List<Object> objectFromJson= JSON.parseArray(jsonStr,Object.class);
		for(Object object:objectFromJson){
			/*
			  	object:1
				object:strobject
			 */
			System.out.println("object:"+object);
		}
	}
	
}


````

````UserInfo.java
package cn.htmlv5.bobshute.je.open.json.fastjson;

public class UserInfo {
	private String name;
	private int age;
	
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	
}

````
 

  
  


  [1]: http://www.cnblogs.com/kakawei/p/5990212.html
  [2]: http://mvnrepository.com/artifact/com.alibaba/fastjson/1.2.29