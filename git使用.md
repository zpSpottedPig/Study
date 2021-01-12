### 					git使用

#### 1.git下载安装

官网下载地址: <https://git-scm.com/downloads/>

 安装 一键Next , on the Desktop(添加图标在桌面上)

#### 2.配置gitHub

git生成ssh秘钥：  参考<https://www.cnblogs.com/yjlch1016/p/9692840.html>

```git
--  配置GitHub用户名
git config --global user.name "yangjianliang"
-- 配置GitHub邮箱
git config --global user.email "526861348@qq.com"
```

此时，会在C:\Users\Administrator目录下生成.gitconfig配置文件：

```git
-- 生成公钥和私钥按3次Enter
ssh-keygen -t rsa -C "526861348@qq.com"
-- 查看公钥
cat ~/.ssh/id_rsa.pub
```

公钥保存路径  C:\Users\Administrator\.ssh\id_rsa.pub

GitHub添加公钥: settings-->SSh and GPG keys --> New SSH key

