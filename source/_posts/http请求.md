---
title: http请求
date: 2019-02-24 22:06:07
categories: 学习笔记
tags: 
- HTTP
---

# 什么是HTTP

HTTP协议（HyperText Transfer Protocol，超文本传输协议）是用于从WWW服务器传输超文本到本地浏览器的传输协议。    

HTTP遵循请求(Request)/应答(Response)模型。Web浏览器向Web服务器发送请求，Web服务器处理请求并返回适当的应答。所有HTTP连接都被构造成一套请求和应答。

## HTTP请求

HTTP请求一般分为4个部分：
1. 请求方法 请求路径 协议/版本
2. 请求头
3. 空行
4. 要上传的数据

example:    

```http
GET /sample.jsp HTTP/1.1      //请求方法 请求路径  协议/版本
Accept:image/gif.image/jpeg,*/*   // 请求头
Accept-Language:zh-cn
Connection:Keep-Alive
Host:localhost
User-Agent:Mozila/4.0(compatible;MSIE5.01;Window NT5.0)
Accept-Encoding:gzip,deflate
                                    // 空行
username=jinqiao&password=1234      // 要上传的数据
```

其中 空行是用于区分请求头和要上传的数据, 要上传的数据可以为空。

### HTTP请求方法：
1. GET: 请求指定的页面信息，并返回实体主体
2. HEAD: 类似于get请求，只不过返回的响应中没有具体的内容，用于获取报头
3. POST: 向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST请求可能会导致新的资源的建立和/或已有资源的修改。
4. OPTIONS: 允许客户端查看服务器的性能。
5. PUT: 从客户端向服务器传送的数据取代指定的文档的内容。
6. DELETE: 请求服务器删除指定的页面。
7. TRACE: 回显服务器收到的请求，主要用于测试或诊断。
8. CONNECT: HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器。

## HTTP响应

HTTP应答与HTTP请求相似，HTTP响应也由4个部分构成：
1. 协议状态/版本 响应状态码
2. 请求头
3. 空行
4. 响应正文

explame:
```http
HTTP/1.1 200 OK                  //  协议状态/版本 响应短语
Server:Apache Tomcat/5.0.12      // 请求头
Date:Mon,6Oct2003 13:23:42 GMT
Content-Length:112
                                 // 空行
<html>                           // 响应正文
<head>....

```

### HTTP响应状态码
HTTP应答码由3位数字构成，其中首位数字定义了应答码的类型：

1. 1XX－信息类(Information),表示收到Web浏览器请求，正在进一步的处理中
2. 2XX－成功类（Successful）,表示用户请求被正确接收，理解和处理例如：200 OK
3. 3XX-重定向类(Redirection),表示请求没有成功，客户必须采取进一步的动作。
4. 4XX-客户端错误(Client Error)，表示客户端提交的请求有错误 例如：404 NOT Found，意味着请求中所引用的文档不存在。
5. 5XX-服务器错误(Server Error)表示服务器不能完成对请求的处理：如 500


## 如何用chrome查看HTTP响应/请求？

1. 打开 Network
2. 输入网址
3. 选中任意请求
4. 查看Request Headers/Response Headers，点击「view source」
5. 你会看到请求/响应的前两部分   
如果请求有第四部分点击FormData或Payload   
查看 Response 或者 Preview，你会看到响应的第 4 部分


## 如何使用curl

cURL是一个利用URL语法在命令行下工作的文件传输工具，它支持文件上传和下载，所以是综合传输工具。

curl语法： curl [option] [url]

curl常用参数

| 选项|描述
|-|:-: |
|-A/--user-agent  (string) | 设置用户代理发送给服务器和时间|
|-b/--cookie (name=string/file) | cookie字符串或文件读取位置|
|-c/--cookie-jar (file)          |          操作结束后把cookie写入到这个文件中 |
|-C/--continue-at (offset)       |    断点续转 |
|-D/--dump-header (file)        |      把header信息写入到该文件中|
|-e/--referer                      |            来源网址|
|-f/--fail                     |                     连接失败时不显示http错误
|-o/--output                     |             把输出写到该文件中
|-O/--remote-name              |        把输出写到该文件中，保留远程文件的文件名
|-r/--range (range)            |        检索来自HTTP/1.1或FTP服务器字节范围
|-s/--silent                   |                 静音模式。不输出任何东西
|-T/--upload-file (file)       |           上传文件
|-u/--user (user[:password])  |   设置服务器的用户和密码
|-w/--write-out [format]     |           什么输出完成后
|-x/--proxy (host[:port])     |       在给定的端口上使用HTTP代理|
|-#/--progress-bar         |               进度条显示当前的传送状态|

example:

1. 基本用法

```Bash
curl http://www.example.com
```
这样网站的HTML就会显示在终端了

2.  可以使用curl的内置option:-o(小写)保存网页:

```Bash
curl -o example.html http://www.example.com
```

3. 指定proxy服务器以及其端口:  
很多时候上网需要用到代理服务器(比如是使用代理服务器上网或者因为使用curl别人网站而被别人屏蔽IP地址的时候)，幸运的是curl通过使用内置option：-x来支持设置代理

```Bash
curl -x 192.168.100.100:1080 http://www.example.com
```

4. cookie

保存http的response里面的cookie信息。内置option:-c（小写）

```Bash
curl -c cookiec.txt  http://www.example.com
```
执行后cookie信息就被存到了cookiec.txt里面了   

保存http的response里面的header信息。内置option: -D
```Bash
curl -D cookied.txt http://www.example.com
```

执行后cookie信息就被存到了cookied.txt里面了

5. 模仿浏览器
有些网站需要使用特定的浏览器去访问他们，有些还需要使用某些特定的版本。curl内置option:-A可以让我们指定浏览器去访问网站

```Bash
curl -A "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 5.0)" http://www.example.com
```
这样服务器端就会认为是使用IE8.0去访问的


curl还有很多用法，这里只是举了几个简单的例子，有兴趣的同学可以自己查一下资料。