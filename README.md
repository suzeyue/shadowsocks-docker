# shadowsocks

shadowsocks server端

参考[Shadowsocks 使用说明](https://github.com/shadowsocks/shadowsocks/wiki/Shadowsocks-%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)

通过环境变量的方式来修改ssserver的启动参数。

- SERVER_PORT ssserver服务端口号，默认**32000**
- PASSWORD ssserver密码，默认**helloWorld**
- METHOD 加密方法，默认**rc4-md5**

## 启动

#### 一般方式：

`docker run -d -p 32000:32000 suzeyue/shadowsocks`

这里将容器中32000端口映射到本地，客户端在配置服务器时设置默认的端口、密码和加密方式。

#### 修改参数：

`docker run -d -e SERVER_PORT=port -e PASSWORD=passwd -e METHOD=method -p localport:port suzeyue/shadowsocks`

这里port、passwd、method替换成你自己的，localport为映射到本地的端口，客户端在配置服务器时端口应设为localport。
