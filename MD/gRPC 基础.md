# 一、gRPC 结构

![image-20200809081157443](Siahk\Repository\Pictures\image-20200809081157443.png)

# 二、设计步骤

![image-20200809081421271](.\Pictures\image-20200809081421271.png)



# 三、生命周期

![image-20200809081506275](.\Pictures\image-20200809081506275.png)

# 四、身份认证

机制：

* 不采取任何措施的连接，也就是不安全的连接。
* TLS/SSL 连接。
* 基于 Google Token 的身份认证。
* 自定义的身份认证服务商。

# 五、消息传输类型

* 一元的消息，就是简单的“请求-响应”。
* Server Streaming（流）， server会把数据 streaming 回给 Client。
* Client Streaming， 也就是 Client 会把数据 streaming 给Server。
* 双向 Streaming。

## 1.一元消息

rpc 方法名(请求类型) returns(响应类型)

![image-20200809082739637](.\Pictures\image-20200809082739637.png)

## 2.Server Streaming

rpc 方法名(请求类型) returns(stream 响应类型)

![image-20200809082931953](.\Pictures\image-20200809082931953.png)

## 3.Client Streaming

rpc 方法名(stream 请求类型) returns(响应类型)

![image-20200809083047525](.\Picturess\image-20200809083047525.png)

## 4.双向 Streaming

rpc 方法名(stream 请求类型) returns(stream 响应类型)

![image-20200809083224282](.\Pictures\image-20200809083224282.png)

# 六 消息类型

## 1.Service 关键字

```protobuf
protobuf service Employee {
}
```

```protobuf
protobuf service Employee {
	rpc GeByName (Request) returns (Response)
}
```
