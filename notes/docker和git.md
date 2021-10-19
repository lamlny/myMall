## docker和git的使用

**docker**：创建一个文件用"touch"，修改文件用"vi"，其中“i”进入插入操作，"Esc"退出插入操作，":w"保存，":q"退出，"pwd"显示当前目录，".."返回上级目录。

```java
1. docker run -p 3306:3306 --name mysql \
//linux端口映射容器端口，容器相当于一个小linux系统
-v /mydata/mysql/log:/var/log/mysql \
-v /mydata/mysql/data:/var/lib/mysql \
-v /mydata/mysql/conf:/etc/mysql \
//将容器中mysql相关的文件挂载到linux系统下的文件，之后修改linux文件内容也会同步到容器中
-e MYSQL_ROOT_PASSWORD=root \
-d mysql:5.7
//后台启动mysql
2. docker exec -it mysql /bin/bash
//进入mysql命令行界面
   docker exec -it myredis redis-cli
//进入redis客户端界面
```



**git**：首先下载Git客户端，在桌面"Git Bash Here"，

```java
//配置用户名和邮箱
git config --global user.name "lamlny"
git config --global user.email "lamlny@163.com"
//配置ssh免密登录
ssh-keygen -t rsa -C "lamlny@163.com"
cat ~/.ssh/id_rsa.pub
//复制ssh-rsa+一大串字符后在GitHub-头像Settings-SSH and GPG keys设置SSH gitKey
//在想要提交内容的文件夹内（如miaosha项目的文件夹）"Git Bash Here"
git init
git checkout -b main
git remote add origin git@github.com:lamlny/myMall.git
git add imgs	//只想添加imgs文件夹
git commit -m "first commit"
git pull origin main
git push origin main
//最后成功添加imgs文件夹至main branch
```

