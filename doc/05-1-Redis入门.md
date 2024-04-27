# 1. Redis入门

## 1.1 Redis简介

Redis是一个基于**内存**的key-value结构数据库。Redis 是互联网技术领域使用最为广泛的**存储中间件**。

**官网：**<https://redis.io>
**中文网：**<https://www.redis.net.cn/>

**key-value结构存储：**

![image-20221130173459174](assets/image-20221130173459174.png)

**主要特点：**

- 基于内存存储，读写性能高  
- 适合存储热点数据（热点商品、资讯、新闻）
- 企业应用广泛

Redis是用C语言开发的一个开源的高性能键值对(key-value)数据库，官方提供的数据是可以达到100000+的QPS（每秒内查询次数）。它存储的value类型比较丰富，也被称为结构化的NoSql数据库。

NoSql（Not Only SQL），不仅仅是SQL，泛指**非关系型数据库**。NoSql数据库并不是要取代关系型数据库，而是关系型数据库的补充。

**关系型数据库(RDBMS)：**

- Mysql
- Oracle
- DB2
- SQLServer

**非关系型数据库(NoSql)：**

- Redis
- Mongo db
- MemCached

## 1.2 Redis下载与安装

### 1.2.1 Redis下载

Redis安装包分为windows版和Linux版：

- Windows版下载地址：<https://github.com/microsoftarchive/redis/releases>
- Linux版下载地址： <https://download.redis.io/releases/>

资料中已提供好的安装包：

![image-20210927092053283](assets/image-20210927092053283.png)

### 1.2.2 Redis安装

**1）在Windows中安装Redis(项目中使用)**

Redis的Windows版属于绿色软件，直接解压即可使用，解压后目录结构如下：

![image-20221130180657152-zoom:50%;](assets/image-20221130180657152.png)

**2）在Linux中安装Redis(简单了解)**

在Linux系统安装Redis步骤：

1. 将Redis安装包上传到Linux
2. 解压安装包，命令：tar -zxvf redis-4.0.0.tar.gz -C /usr/local
3. 安装Redis的依赖环境gcc，命令：yum install gcc-c++
4. 进入/usr/local/redis-4.0.0，进行编译，命令：make
5. 进入redis的src目录进行安装，命令：make install

安装后重点文件说明：

- /usr/local/redis-4.0.0/src/redis-server：Redis服务启动脚本
- /usr/local/redis-4.0.0/src/redis-cli：Redis客户端脚本
- /usr/local/redis-4.0.0/redis.conf：Redis配置文件

## 1.3 Redis服务启动与停止

以window版Redis进行演示：

### 1.3.1 服务启动命令

**redis-server.exe redis.windows.conf**

![image-20221130181950351-zoom:50%;](assets/image-20221130181950351.png)

Redis服务默认端口号为 **6379** ，通过快捷键**Ctrl + C** 即可停止Redis服务

当Redis服务启动成功后，可通过客户端进行连接。

### 1.3.2 客户端连接命令

**redis-cli.exe**

![image-20221130182207020-zoom:50%;](assets/image-20221130182207020.png)

通过redis-cli.exe命令默认连接的是本地的redis服务，并且使用默认6379端口。也可以通过指定如下参数连接：

- -h ip地址
- -p 端口号
- -a 密码（如果需要）

### 1.3.3 修改Redis配置文件

设置Redis服务密码，修改redis.windows.conf

```
requirepass 123456
```

**注意：**

- 修改密码后需要重启Redis服务才能生效
- Redis配置文件中 # 表示注释

重启Redis后，再次连接Redis时，需加上密码，否则连接失败。

```
redis-cli.exe -h localhost -p 6379 -a 123456
```

![image-20221130183253539-zoom:50%;](assets/image-20221130183253539.png)

此时，-h 和 -p 参数可省略不写。

### 1.3.4 Redis客户端图形工具

默认提供的客户端连接工具界面不太友好，同时操作也较为麻烦，接下来，引入一个Redis客户端图形工具。

在当天资料中已提供安装包，直接安装即可。

![image-20221130183746355-zoom:50%;](assets/image-20221130183746355.png)

安装完毕后，直接双击启动

**新建连接**

![image-20221130192210418-zoom: 33%;](assets/image-20221130192210418.png)  

**连接成功**

![image-20221130192310916-zoom: 33%;](assets/image-20221130192310916.png)  

