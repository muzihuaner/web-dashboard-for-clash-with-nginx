# CLash Linux 网络管理面板
Clash : [click me](https://github.com/Dreamacro/clash)

## 如何部署

1. 在你的主机上部署nginx，我这里使用的是ubuntu

```bash
sudo apt-get install nginx
```

2. Clone 本项目到你的WEB目录下
3. 添加下面两个配置到你的nginx配置

clash.conf

```nginx
server {
        server_name             localhost;
        listen                  30000;
    
        access_log              /var/log/nginx/clash.log;
        error_log               /var/log/nginx/clash.err;
    
        root                    /path/to/yourwebsite/;
        index                   index.html;
}
```

clash_font.conf

```nginx
server {
        server_name             localhost;
        listen                  30001;

        access_log              /var/log/nginx/clash_font.log;
        error_log               /var/log/nginx/clash_font.err;

        root                    /path/to/yourwebsite/at.alicdn.com;
        index                   index.html;
}
```

4. 重新启动nginx并访问 http://localhost:30000

![](img/rendering.png)