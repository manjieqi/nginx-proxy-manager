# 自定义 Nginx Proxy Manager
预安装zope和certbot-dns-dnspod，启用geoip2

**注意：**

Dockerfile文件中的镜像源仅腾讯云服务器内网可用

http_top文件中设置了仅中国IP可访问

compose文件中maxmindinc的ID和Key需自填

**运行方法：**

```
# 创建名为nginx的Docker网络
sudo docker network create nginx

# 构建镜像(可选，需修改compose文件中对应镜像)
sudo docker build -t nginx-proxy-manager ./build

# 启动Docker容器
sudo docker compose up -d
```