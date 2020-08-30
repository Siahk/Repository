# HTTP和HTTP2对比

## HTTP

**超文本传输协议**

​	用于传输诸如HTML的超媒体文档的应用层协议

​	设计用于WEB浏览器和Web服务器之间的通信，也可以用于其他目的。

​	遵循经典的客户端-服务端模型，客户端打开一个连接以发出请求，然后等待它收到服务器端响应

​	无状态协议，服务器不会在两个请求之间保留任何数据（状态）

​	通常基于TCP / IP层，也可以在任何可靠的传输层上使用

## HTTPS

**HTTP Strict Transport Security**

​	安全功能，只能通过HTTPS访问当前资源，禁止HTTP方式



## SPDY（2012年）

过渡



![img](.\Pictures\SPDY.jpg)

## HTTP2

**基于SPDY设计**

- HTTP2.0 支持明文 HTTP 传输，而 SPDY 强制使用 HTTPS

- HTTP2.0 消息头的压缩算法采用 HPACK，而非 SPDY 采用的 DEFLATE

### 新特性

- **新的二进制格式（Binary Format）**
- **多路复用（MultiPlexing）**
- **header压缩**
-  **服务端推送（server push）**

