# etcd v3.3

本项目包括etcd v3.3版本的单机服务和一个etcd管理界面，方便开发，拿来即用。

管理界面来自：[https://github.com/shiguanghuxian/etcd-manage](https://github.com/shiguanghuxian/etcd-manage)

## 备注

国内用户可以将etcd镜像地址换成 quay.azk8s.cn/coreos/etcd:v3.3 

配置文件 [bin/config/cfg.toml](bin/config/cfg.toml)

```
# debug模式
debug = true
# 日志文件路径
log_path = ""

# http 监听端口
[http]
# 监听地址
address = "0.0.0.0"
# 监听端口
port = 10280

## 一下每一个server为一个etcd服务 ##
[[server]]
# 显示名称
title = "测试环境"
# 标识名
name = "qa"
# etcd连接地址 如果为集群请填写全部地址
address = ["127.0.0.1:2379"]
# 查看的key前缀
key_prefix = "root"
# 简述信息
desc = "环境etcd"
# 可访问服务器角色列表 - 不写则为所有用户可访问
roles = ["admin"]

[[server]]
title = "本机"
name = "local"
address = ["127.0.0.1:2379"]
key_prefix = "root"
desc = "本机环境"
roles = ["admin","dev"]

## 以下为用户列表 ##
[[user]]
username = "admin"
password = "123456"
role = "admin"

[[user]]
username = "dev_user"
password = "123456"
role = "dev"

```