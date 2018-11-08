FROM nanoninja/php-fpm:7.1

# 安装grpc不使用代理方式
COPY ./ext/grpc-1.16.0.tgz /var/www/html/
COPY ./ext/protobuf-3.6.1.tgz /var/www/html/
RUN pecl -vvv install grpc-1.16.0.tgz \
    && pecl install protobuf-3.6.1.tgz \
    && docker-php-ext-enable grpc

# 使用代理方式，需要填写正确的http代理地址，建议使用 ShadowsocksX
# RUN pear config-set http_proxy http://172.16.31.236:1087
# RUN pecl -vvv install grpc \
#     && pecl install protobuf \
#     && docker-php-ext-enable grpc

RUN apt-get update && apt-get install -y curl telnet lsof unzip wget git vim \
    && apt-get autoremove -y --purge \
    && apt-get clean \
    && rm -Rf /tmp/* \
    && rm -rf grpc-1.16.0.tgz \
    && rm -rf protobuf-3.6.1.tgz

EXPOSE 9000
