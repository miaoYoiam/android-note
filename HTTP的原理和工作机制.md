## HTTP的原理和工作机制

- ###  Http -- HyperText Transfer Protocol 超文本传输协议

  超文本：在电脑中显示的、汉语可以指向其他文本的链接的文本

- ###  Http的工作方式

  在浏览器和服务器直接 进行 发送请求、响应的交互

  

  ### URL -> HTTP报文

  #### URL

  ​	1、协议类型：http://

  ​	2、服务器地址：baidu.com

  ​	3、路径path：参数

  

  #### 报文格式

  ##### 请求行  GET  /users  HTTP/1.1

  ###### 	method : Get / Post

  ​		Get ：获取资源 没有body

  ​		Post ：增加或修改资源，有body

  ​		Put ：修改资源，有body

  ​		Delete ：删除资源，没有body

  ​		Head ：获取资源 没有body  几乎和Get是一样的，区别是服务器返回内容的时候不返回body 

  ###### 	path : users

  ###### 	Http version : HTTP/1.1

  

  ##### 状态行  HTTP/1.1   200   OK

  

  ##### Status Code

  ###### 	1xx ：临时性消息 101-支持Http2.0

  ###### 	2xx ：成功

  ###### 	3xx ：重定向   302-暂时 301-永久

  ###### 	4xx ：客户端错误 404 401 400

  ###### 	5xx ：服务器错误 

  

  ##### Headers 

  ​	作用：HTTP消息的元数据 metadata 数据的属性

  ###### 	Host : 服务器主机地址

  ###### 	Content-Type ：

  ​			text/html ：一个html文本，用于浏览器页面响应

  ​			application/x-www-form-urlencoded：提交的是一个普通表单，encoded url 格式 ，服务器接受后会																		去查看body

  ​			multipart/form-data：多部分形式，一般用于传输包含二进制内容的多项内容，带文件的表单

  ​												boundary-表示是一个分界线，header和body，以及body内的各属性

  ​			application/json ：json形式，用于Web Api的响应或 POST/PUT请求

  ​			image/jpeg/application/zip ：直接提交文件，用于Web Api的响应或 POST/PUT请求 图片上传用base64

  ###### 	Content-Length ：内容的长度（字节）

  ###### 	Transfer-Encoding ： chunked，表示Body 长度无法确定，Content-Length 不能使用

  ###### 	Location ：重定向的目标 URL

  ###### 	User-Agent ：用户代理

  ######     Range/Accept-Range ：制定Body的内容范围  支持分段下载

  ###### 	Accept ：客户端能够接受的数据类型 如text/html

  ###### 	Accept-Charset ：客户端接受的字符集 如UTF-8

  ###### 	Accept-Encoding ：客户端接受的压缩编码类型 如gzip

  ###### 	Content-Encoding ：压缩类型 如 gzip

  ​	

  ###### 	Cache 和 Buffer的区别

  ​	cache 是缓存，用过的东西可能还会用，是为了速度 可能会重用

  ​	buffer 是缓冲，针对工作流，有生产的上游 和 消费的下游，过段时间可能会用，首先加载

  

  ###### 	Cache-Control ：

  ​	no-cache ：可以缓存 需要再次使用资源的时候，需要询问

  ​	no-store ：没有缓存

  ​	max-age ：缓存有一个失效日期，有效期前都可以使用

  ​	private ：不可以缓存

  ​	public：可以缓存

  

  ###### 	Last-Modified：最后的修改日期

  ###### 	Etag：相当于一个hash，相当于一个标签 if-none-match

  ​	

  ###### 	REST：RESTful HTTP -----> 正确的使用HTTP

  ​    对HTTP进行一些限制的架构风格 

  ​	Server-Client architecture

  ​	Statelessness 无状态，先后请求之前没有任何关联

  ​	Cacheability

  ​	Layeared system  分层

  ​	Code on demand 服务器在返回的信息里面，允许包括一些可执行代码 ，一些在本地执行的代码

  ​	Uniform interface

  

  ##### Body 要发送给服务器的内容

  

  ###### 

  

  

  

  





