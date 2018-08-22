# ngrok

自建的内网穿透工具 Ngrok，方便调试微信网页，支付等, 服务地址: ngrok.zhulogic.com

> 一分钟实现内网穿透（ngrok服务器搭建） https://blog.csdn.net/zhangguo5/article/details/77848658

## Quick Start

```
$ ./ngrok -config ngrok.cfg start wx
Tunnel Status                 online
Version                       1.7/1.7
Forwarding                    http://wx.ngrok.zhulogic.com:9999 -> localhost:8080
Web Interface                 127.0.0.1:4040
# Conn                        0
Avg Conn Time                 0.00ms
```

**9999 端口可以忽略，http://wx.ngrok.zhulogic.com 也同样转发到 localhost:8080**

## File List

- `ngrok` macOS client
- `ngrok.exe` windows x64 client
- `ngrokd` linux x64 server
- `ngrok.cfg` ngrok config

## Sample Config

```
# ngrok 服务地址
server_addr: "ngrok.zhulogic.com:4443"

# 隧道列表
tunnels:
  # 隧道名称
  wx:
    # 子域名
    subdomain: wx
    # 协议
    proto:
      # http 协议
      http: localhost:8080
  ssh:
    # 子域名
    subdomain: wx
    # 协议
    proto:
      # tcp 协议
      tcp: localhost:22
```
