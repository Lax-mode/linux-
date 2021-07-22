# Mysql 

1. mysql启动

```
sudo docker run -d -p 3306:3306 --privileged=true -v /usr/local/docker/mysql/conf/:/etc/msql -v /usr/local/docker/mysql/data:/var/lib/mysql -v /usr/local/docker/mysql/logs:/var/log/mysql -e MYSQL_ROOT_PASSWORD=root --name mysql --restart=always mysql:5.7 --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci --lower-case-table-names=1
```

# Niginx 

1. nginx启动

```
docker run -d -p 88:80 -v /docker/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v /docker/nginx/logs/:/var/log/nginx -v /docker/nginx/conf.d/default.conf:/etc/nginx/conf.d/default.conf --name nginx --restart=always nginx
```

# Redis

https://www.cnblogs.com/ludada/articles/13947838.html

1. redis启动

```
sudo docker run -p 6379:6379 --name redis -v /usr/local/docker/redis/redis.conf:/etc/redis/redis.conf -v /usr/local/docker/redis/data:/data -d --restart=always redis redis-server /etc/redis/redis.conf 
```

# Jenkins

1. rpm卸载

```
rpm -e jenkins
```

1. 检查是否卸载成功

```
rpm -ql jenkins
```

3、彻底删除残留文件：

```
find / -iname jenkins | xargs -n 1000 rm -rf
```

查看安装路径

```
whereis jenkins
```

# Linux常用命令

把端口添加到防火墙

```
firewall-cmd --zone=public --add-port=82/tcp --permanent
firewall-cmd --reload
```

文件设置权限

```
chmod u+x *
```

移动文件

```
mv apache-maven-3.6.2/* /opt/maven 
```

 复制文件

```
cp -r apache-maven-3.6.2/* /opt/maven
```

配置生效

```
source /etc/profile 
```

安装目录

```
whereis git 
```

查看进程

```
ps -ef | grep mysql
```

杀死进程

```
sudo kill -9 
```

# Maven

```
<!--开始处更改下载依赖的存放路径， 以下目录需要已经创建-->
<localRepository>D:\javasource\maven-repository</localRepository>
<!--在 mirrors 标签下 添加阿里云maven私服库-->
<mirrors>
<mirror>
<id>alimaven</id>
<mirrorOf>central</mirrorOf>
<name>aliyun maven</name>
<url>http://maven.aliyun.com/nexus/content/groups/public/</url>
</mirror>
</mirrors>
<!-- 在 profiles 标签下指定jdk版本 -->
<profile>
<id>jdk-1.8</id>
<activation>
<activeByDefault>true</activeByDefault>
<jdk>1.8</jdk>
</activation>
<properties>
<maven.compiler.source>1.8</maven.compiler.source>
<maven.compiler.target>1.8</maven.compiler.target>
<maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
</properties>
</profile>
```

# Git

撤销commit

```
git reset --soft HEAD~ 
```

