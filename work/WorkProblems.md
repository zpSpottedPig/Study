### WorkProblems工作错误日志

+ [Java](#Java)
+ [前端](#前端)
+ [mysql](#mysql)
+ [redis](#redis)

#### Java

**1.请求数据过大，传输不到后台？**

tomcat默认接收请求大小为2M,修改server.xml，添加maxPostSize="104857600" 配置，设置为100M大小

```xml
    <Connector port="8080" protocol="HTTP/1.1" URIEncoding="UTF-8"
               connectionTimeout="20000"
               redirectPort="8443" maxPostSize="104857600" />
```

#### 前端

**1.请求参数+变为空格，导致数据错误？**

​		前端进行编码： 通过 encodeURIComponent(var) 方法

**2.ajax请求格式 getJSON() 传中文值乱码？**

​		1.换请求格式：$.post();

​		2.前端编码 encodeURI(name,"utf-8");

​			后端解码URLDecoder.decode(request.getParameter("name"),"utf-8");

ajax请求格式:

参考： https://www.cnblogs.com/ranzige/p/jquery_get_ajax.html

#### mysql

**1.mysql 报 You can't specify target table '表名' for update in FROM clause **

翻译为：不能先select出同一表中的某些值，再update这个表(在同一语句中)         把结果集当作一个表，自我查询一遍 格式为：SELECT a.字段名 FROM (结果集)a

#### redis

**1.redis存储tomcat共享session异常:redis.clients.jedis.exceptions.JedisDataException: NOAUTH Authentication**

 redis增加密码了，添加密码配置/取消密码