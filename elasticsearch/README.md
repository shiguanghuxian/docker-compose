# ElasticSearch + Kibana + head

es搜索引擎和web ui

## 备注
head 请求es搜索接口_search 406 (Not Acceptable)

```
docker-compose exec head /bin/sh
cd _site
vi vendor.js
# 按ESC输入:6886跳转到6886行
# 将6886行 contentType: "application/x-www-form-urlencoded" 改为 contentType: "application/json"
```
