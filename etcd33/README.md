# etcd v3.3

本项目包括etcd v3.3版本的单机服务和一个etcd管理界面，方便开发，拿来即用。

管理界面来自：[https://github.com/shiguanghuxian/etcd-manage](https://github.com/shiguanghuxian/etcd-manage)

## 备注

配置文件 conf/config.default.ini

```
[app]
port=9090 // etcd管理界面运行端口
auth=false

[etcd]
root_key=root // key根前缀
dir_value=
addr=etcd:2379 // etcd地址
username=
password=
cert_file=
key_file=
ca_file=
```