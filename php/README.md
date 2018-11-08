# docker nginx php grpc

php的快速开发环境，添加了grpc扩展支持

## 备注

由于国内有墙使用pecl install xxx 安装依赖时会导致安装错误

解决方案1

    可以通过手动下载依赖，使用本地安装方式

解决方案2

    使用代理，通过 `RUN pear config-set http_proxy http://x.x.x.x:xxxx` 设置容器内http代理

    代理软件可以使用ShadowsocksX
