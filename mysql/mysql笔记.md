<center>MySql笔记</center>

### 简介

**SQL语言分类**

* DQL（Data Query Language）：数据查询语言 select 相关语句

* DML（Data Manipulate Language）：数据操作语言 insert 、update、delete 语句

* DDL（Data Define Languge）：数据定义语言 create、drop、alter 语句
* DCL （Data Control Language）：数据控制语句 grant：允许用户访问数据库的权限。revoke：撤销用户访问数据库的权限。

* TCL（Transaction Control Language）：事务控制语言 set autocommit=0、start transaction、savepoint、commit、rollback

### 1.MySql安装

window安装 ：		教程参考(<https://www.cnblogs.com/honeynan/p/12408119.html>)

```window
mysql服务启动
-- 查看MySQL版本
mysql -V
mysql --version

方式1：
-- 打开服务
services.msc

方式2：
-- 关闭服务
net stop mysql (mysql服务名称)
-- 启动服务
net start mysql
-- mysql连接
mysql -P3306 -uroot -proot
```

### 2.MySQL命令

##### desc

```mysql
-- 查看表结构：
desc table_name;
```

##### use

```mysql
-- 切换数据库
use database_name;
```

##### select

```mysql
-- 查看版本
select version();
-- 查看当前所在库
select database();
```

##### show

```mysql
-- 查看所有数据库
show databases;
-- 查看数据库表
show tables;
show tables from database_name;
-- 查看表的创建语句
show create table biz_tags;
-- 查看当前mysql支持的存储引擎
SHOW ENGINES;
-- 查看系统变量及其值
SHOW VARIABLES;
SHOW VARIABLES like 'wait_timeout';
--  查看所有事件
show events; 
-- 查看事件状态 （开启事件：SET GLOBAL event_scheduler = 1; or SET GLOBAL event_scheduler = 'no';）
show variables like 'event_scheduler';  
-- 查看所有过程
show procedure status;
--  查看存储过程或函数的创建代码
show create procedure proc_name;
--  查看用户权限
show grants for 'username'; 
```



