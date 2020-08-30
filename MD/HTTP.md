# HTTP协议入门

## 一、HTTP/0.9

基于 TCP/IP 协议的应用层协议，默认使用80端口，只有一个命令。

~~~http
GET /index.html # TCP 连接（connection）建立后，客户端向服务器请求（request）网页index.html
~~~

回应的格式

~~~html
<html>
  <body>Hello World</body>
</html>
~~~

服务器发送完毕，就关闭TCP连接。

## 二、HTTP/1.0

### 1.请求格式

~~~http
GET / HTTP/1.0
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_5)
Accept: */*
~~~

第一行是请求命令，必须在尾部添加协议版本（`HTTP/1.0`）。后面就是多行头信息，描述客户端的情况。

### 2.回应格式

**服务器回应**

~~~html

HTTP/1.0 200 OK 
Content-Type: text/plain
Content-Length: 137582
Expires: Thu, 05 Dec 1997 16:00:00 GMT
Last-Modified: Wed, 5 August 1996 15:55:28 GMT
Server: Apache 0.84

<html>
  <body>Hello World</body>
</html>
~~~

**回应的格式：**

头信息 + 一个空行（`\r\n`） + 数据

第一行是"协议版本 + 状态码（status code） + 状态描述"。

### 3.Content-Type 字段

头信息必须是**ASCII码**

**常见Content-Type字段的值：**

~~~
text/plain
text/html
text/css
image/jpeg
image/png
image/svg+xml
audio/mp4
video/mp4
application/javascript
application/pdf
application/zip
application/atom+xml
~~~

这些数据类型总称为`MIME type`，每个值包括一级类型和二级类型，之间用斜杠分隔

## 三、HTTP/1.1

## 四、SPDY

## 五、HTTP/2

1.二进制协议

2.多工

3.数据流

4.头信息压缩

5.服务器推送

