# Connection: keep-alive

## 含义

### 前提

http 协议采用**请求-应答**模式，当使用普通模式（非 keep-alive）时，每个**请求-应答**都需要客户端和服务端新建一个连接，完成之后立即断开连接（HTTP 协议是*无连接*协议）

### 解决方案

使用 keep-alive 模式，会使客户端到服务器端的连接持久有效，后续对该服务器的请求，避免了建立或者重新简历连接

## 客户端如何开启

### 1.0

默认是关闭，需要在 http 请求头中加入 `Connection: keep-alive`

### 1.1

默认开启，需要设置 `Connection: close` 才会关闭

大部分浏览器都是 1.1 版本，是否能完成完整的 keep-alive 连接就看服务器的设置情况