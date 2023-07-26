# 安装 Yugabyte

#### 下载 

```
docker pull yugabytedb/yugabyte:2.17.1.0-b439
```


#### 创建一个容器

```
docker run -d --name yugabyte  -p7000:7000 -p9000:9000 -p5433:5433 -p9042:9042\
 yugabytedb/yugabyte:2.17.1.0-b439 bin/yugabyted start\
 --daemon=false
```

#### 启动容器

```
docker start yugabyte
```
