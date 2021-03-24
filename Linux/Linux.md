

## Linux

### 命令大全

+ [chmod](#chmod)
+ [cat](#cat)
+ [find](#find)
+ [df/du](#df/du)
+ [free](#free)
+ [ls/ll](#ls/ll)
+ [netstat](#netstat)
+ [pwd](#pwd)
+ [rm](#rm)
+ [sudo](#sudo)
+ [service](#service)
+ [systemctl](#systemcal)
+ [scp](#scp)
+ [tail](#tail)
+ [vi/vim](#vi/vim)
+ [grep](#grep)

#### **chmod**

```linux
-- 将当前目录下的所有文件设置成可执行文件
chmod 777 * 
```

#### **cat**

```linux
-- 打开文件内容
cat   fileName 
```

#### **find**   

```linux
-- 更改文件内容 
find /usr/local/flf/cpic -type f -name "*.properties"|xargs sed -i "s/192.168.40.189:3306/192.168.40.197:3306/g"          
 -- 按文件名查询 
find / -name redis  
-- 从根目录递归式查找名称中包含tomcat字段的文件名称
find / -name *tomcat*   
```

#### df/du

```linux
-- 显示磁盘分区上可以使用的磁盘空间 -h以KB、MB、GB的单位来显示，可读性高~~~（最常用）
df -h 

-- 显示每个文件和目录的磁盘使用空间~~~文件的大小。
du -h
```

#### **free**   

```linux
--查看CPU和内存信息 
free -m  
结果集：
Mem为物理内存的容量  
Swap为虚拟内存的容量 
total为总容量   
used为已用容量  
free为空闲容量   
shared为共享容量 
buff/cache为缓冲及缓存的容量    
avaiable为真正可用容量    
一般swap used的值最好不要超过20%
```

#### **ls,ll文件展示**    

```linux
 -- 查看当前目录下的文件    
 ls 
 -- 查看当前目录下的文件信息
 ll 
```

#### **netstat**

```linux
-- 查看端口信息 
netstat -tln   
-- 查看8080端口
netstat -ano|findstr 8080  
-- 监听端口信息
netstat -anp |grep  端口号 
-- 查看所有端口 
netstat  -nultp  
-- 查看3306端口
netstat -tlunp|grep 3306  

-- 使用jps查看启动的java进程列表　　
jps -v 
-- 确认pid进程
ps -ef|grep pid
```

#### **pwd**    

​	查看当前所在的路径

#### rm

```linux
-- -f 即使原档案属性设为唯读，亦直接删除，无需逐一确认。   -r 将目录及以下之档案亦逐一删除。
-- 删除文件/目录  
rm -rf filename/directory 
-- 删除当前目录下的所有文件及目录
rm -r * 
```

#### **sudo**

sudo sudo命令以系统管理者的身份执行指令

#### **service**     

  service mysqId status  -- 查看mysql 服务状态

#### **systemctl**

```linux
关闭防火墙     
--  检测是否开启了firewall  
systemctl status firewalld.service    
-- 关闭firewall 
systemctl stop firewalld.service  
-- 禁止firewall开机自启
systemctl disable firewalld.service   
```

#### **scp**    

 ```linux
用于 Linux 之间复制文件和目录    -r： 递归复制整个目录。     
1、从本地复制到远程        
scp -r  /root/db/   root@192.168.52.2:/root/db/0221zp1.sql       
2、从远程复制到本地        
scp -r root@192.168.52.2:/root/db/0221zp1.sql  /root/db/
 ```

#### **tail**

倒序显示文件内容

tail -f catalina.out       查看运行时的实时日志   

格式：tail [必要参数] [选择参数] [文件]  

参数：-f 循环读取

​			-n<行数> 显示行数

#### vi/vim  

 vi/vim filename; 进入文本编辑模式
        **i** 切换到输入模式，以输入字符。   

 **:** 切换到底线命令模式，以在最底一行输入命令    

**ESC**，退出输入模式，切换到命令模式

命令行模式    q 退出程序     w 保存文件     qw 保存退出     q! 不保存退出

#### grep

查找包含指定字符串的文件 格式： grep “要查找的字符串” 文件名

-n 显示字符串在文件中的行数

-i 不区分字符串的大小写

-e 查找时使用正则表达式

-v 查找不匹配指定字符串的行

### 系统搭建

+ [svn](#svn)
+ [zookeeper](#zookeeper)
+ [nginx](#nginx)
+ [mysql](#mysql)
+ [redis](#redis)

#### **svn**  

  启动：svnserve -d -r /application/svndata/

#### **zookeeper**     

```linux
ZooKeeper服务命令:在准备好相应的配置之后，可以直接通过zkServer.sh 这个脚本进行服务的相关操作
1. 启动ZK服务:    
sh bin/zkServer.sh start
2. 查看ZK服务状态: 
sh bin/zkServer.sh status
3. 停止ZK服务:    
sh bin/zkServer.sh stop
4. 重启ZK服务:    
sh bin/zkServer.sh restart
```

集群启动   

​	sh /usr/local/zookeeper-3.4.9/bin/zkServer.sh start /usr/local/zkdata/zk1/conf/zoo.cfg   

​	sh /usr/local/zookeeper-3.4.9/bin/zkServer.sh start /usr/local/zkdata/zk2/conf/zoo.cfg   

​	sh /usr/local/zookeeper-3.4.9/bin/zkServer.sh start /usr/local/zkdata/zk3/conf/zoo.cfg
​		查看状态  

​	 sh /usr/local/zookeeper-3.4.9/bin/zkServer.sh status /usr/local/zkdata/zk1/conf/zoo.cfg  

 	sh /usr/local/zookeeper-3.4.9/bin/zkServer.sh status/usr/local/zkdata/zk2/conf/zoo.cfg  

 	sh /usr/local/zookeeper-3.4.9/bin/zkServer.sh status/usr/local/zkdata/zk3/conf/zoo.cfg

#### **nginx**   

 启动 /usr/sbin/nginx -c /etc/nginx/nginx.conf

#### **mysql**   

```linux
-- 停止数据库服务       
systemctl stop mysqld.service     
--启动数据库服务       
systemctl start mysqld.service

mysqldump
    （1）导出整zhidao个数据库(包括数据库中的数据）
            mysqldump -u username -p dbname > dbname.sql
    （2）导出专数据库结构（不含数据）属
            mysqldump -u username -p -d dbname > dbname.sql
    （3）导出数据库中的某张数据表（包含数据）
            mysqldump -u username -p dbname tablename > tablename.sql
    （4）导出数据库中的某张数据表的表结构（不含数据）
            mysqldump -u username -p -d dbname tablename > tablename.sql
    注：--skip_add_locks   --skip-lock-tables  可规避表的锁定
```

#### **redis**       

 压缩文件版   :

​	 进入redis 目录 /usr/local/redis     

​     启动 ./bin/redis-server redis.conf  

安装版 :    systemctl start redis
操作redis :   

cd redis/bin  进入redis bin 目录 

 ./redis-cli 启动客户端 （-h主机ip -p 端口 -a 密码）  

select 【0-15】 切换库  

keys * 查询所有key值