FROM jc21/nginx-proxy-manager

# 复制配置文件到容器中
COPY http_top.conf server_proxy.conf /data/nginx/custom/
COPY geoip2.conf /etc/nginx/modules/

# 设置Python包的镜像源，并安装zope和certbot-dns-dnspod
RUN source /opt/certbot/bin/activate && \
    pip install --no-cache-dir zope certbot-dns-dnspod && \
    pip config set global.index-url https://mirrors.tencentyun.com/pypi/simple && \
    deactivate

# 更改apt源为腾讯云源
RUN sed -i "s@http://deb.debian.org@https://mirrors.tencentyun.com@g" /etc/apt/sources.list.d/debian.sources
