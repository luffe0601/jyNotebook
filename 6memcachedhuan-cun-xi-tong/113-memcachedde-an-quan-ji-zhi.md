# 113 memcached的安全机制

memccached 的操作不需要任何用户名和密码，只需要知道'memcached'服务器的ip地址和端口号即可。因此'memcached'使用的时候尤其注意它的安全性。这里听两种安全的解决方法。

1. 使用'-l'参数设置为只有本地可以连接:这种方式，就只能通过本机才能连接，别的机器都不能访问，可以达到最好的安全性
2. 使用防火墙，关闭'11211'端口，外面也不能访问

```text
ufw enable # 开启防火墙
ufw disable # 关闭防火漆
ufw default deny:防火墙以禁止的方式打开，默认是关闭哪些没有开启的端口
ufw deny 端口号 # 关闭某个端口
ufw allow 端口号 # 开启某个端口
查看端口状态:ufw status
```
