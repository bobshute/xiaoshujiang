

# 1. 绿色版安装主要命令

##移除服务
D:\MySQL\mysql-5.7.13\bin>mysqld -remove
Service successfully removed.


----------
##初始化服务

D:\MySQL\mysql-5.7.13\bin>mysqld --initialize


----------
##安装服务

D:\MySQL\mysql-5.7.13\bin>mysqld --install
Service successfully installed.


----------
##启动服务

D:\MySQL\mysql-5.7.13\bin>net start mysql
MySQL 服务正在启动 .
MySQL 服务已经启动成功。


----------
##停止服务

停止服务: net stop mysql

注意: 
密码在:NBJSHU-PC.err中.
2016-06-07T06:10:39.100858Z 1 [Note] A temporary password is generated for root@localhost: id!:f.4KFox:


----------


##修改密码:
set password=password('123456');
flush privileges;

mysql -uroot -p123456

# 2. 创建用户及数据库 


----------
##登录

mysql -uroot -p

---
##创建用户及密码:


CREATE USER 'crawler'@'%' IDENTIFIED BY '123456';
FLUSH PRIVILEGES;


----------
##删除用户:
drop user 'crawler'@'%' 
或: Delete FROM mysql.user Where User='crawler'  and Host='%';

----------
##创建数据库 : 


create database afdata DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
grant all privileges on `crawlerdata`.* to 'crawler'@'%' identified by '123456';

---
##创建表:


create table `crawlerTable` (
`id` int (11),
`type` varchar (48),
`userId` varchar (192),
`phoneNum` varchar (48),
`createtime` timestamp 
); 


----------
##删除数据库

drop database  crawlerdata;


----------
##授权;
grant all privileges on `crawlerdata`.* to 'crawler'@'%' identified by '123456';