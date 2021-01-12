### 					git使用

#### 1.git下载安装

官网下载地址: <https://git-scm.com/downloads/>

![](./image/1610431636(1).jpg)

 安装 一键Next , on the Desktop(添加图标在桌面上)

![](./image/1610432191(1).jpg)

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

#### 3.git文件上传

GitHub创建仓库（repositories）

克隆仓库分支到本地

```git
git clone git@github.com:zpSpottedPig/study.git
```

![](./image/1610443636(1).jpg)

```git
//查询修改的问题
git status  
//添加新增的文件 '.':添加所有文件 
git add . 
//暂存
git commit -am "***" 
//提交到远程仓库
git push 
```

