# docker-compose
一些基础服务的docker-compose配置文件，方便在一台新电脑上快速开始工作

不必输入一长串docker命令来启动对应服务，并且可以做到持久化。



## 列表

| 名称 | 备注 |
|:----| :----|
| [consul](consul) | consul是google开源的一个使用go语言开发的服务发现、配置管理中心服务 |
| [etcd33](etcd33) | etcd是一个开源的、分布式的键值对数据存储系统，提供共享配置、服务的注册和发现 |
| [kong](kong) | Kong是一个可扩展的开源API层(也称为API网关或API中间件)。它运行在任何RESTful API之前，并可通过官网提供的插件进行扩展，也可自定义插件进行用户定制的功能扩展。通过插件，可使其提供超出核心平台之外的功能和服务，譬如使用统计，用户身份验证，API授权等。 |
| [mysql](mysql) | MySQL是一个关系型数据库管理系统，由瑞典MySQL AB 公司开发，目前属于 Oracle 旗下产品 |
| [redis](redis) | Redis是一个开源的使用ANSI C语言编写、支持网络、可基于内存亦可持久化的日志型、Key-Value数据库，并提供多种语言的API。 |
| [mongo](mongo) | MongoDB 是一个基于分布式文件存储的数据库。由 C++ 语言编写。旨在为 WEB 应用提供可扩展的高性能数据存储解决方案。 |
| [postgres](postgres) | PostgreSQL 是一个功能强大的开源对象关系数据库管理系统（ORDBMS）, 用于安全的存 储数据，允许在处理请求时检索它们，是跨平台的，可以在日常的大部分操作系统运行。 |
| [rabbitmq](rabbitmq) | RabbitMQ是一个在AMQP基础上完成的，可复用的企业消息系统。他遵循Mozilla Public License开源协议。 |



## 备注

### docker-compose常用命令

1.编译docker镜像

```
docker build -t name .
```

2.使用docker-compose 执行新建容器组

```
docker-compose up

docker-compose up --force-recreate // 强制新建
```

3.启动容器组

```
docker-compose start
```

4.停止容器组

```
docker-compose stop
```

5.查询容器组所有容器状态

```
docker-compose ps
```

6.删除容器组

```
docker-compose down
```

