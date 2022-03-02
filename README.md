# v2ray benchmark

> 用于 v2ray 不完全测试的配置文件  

* HTTP1.x+TLS+WS+WEB 搭建脚本: https://github.com/IITII/AutoV2ray
* HTTP/2+TLS+H2C+WEB 搭建脚本：https://github.com/IITII/AutoV2ray2

* 如果想使用本配置文件，需要自行对配置文件进行修改

## speedtest_mini
* web server 的配置文件里面可以不配置 php 反代，但是需要安装 php

* `apt install -y php-fpm`
### NGINX

```bash
location ~ \.php$ {
    include snippets/fastcgi-php.conf;
    fastcgi_pass unix:/run/php/php-fpm.sock;
}
```

### Caddy

```
reverse_proxy unix//run/php-fpm.sock
```