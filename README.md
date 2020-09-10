# 利用 nodejs 创建web服务器
1. 本例利用nodejs的http、fs、path等模块实现了简单的web服务器功能。即开启服务后，将静态资源部署到相应目录下，可以通过开启的服务进行访问。类似于我们之前部署web服务到tomcat下便可以通过http访问。

2. 先开启服务：在项目根目录下执行```node 00service.js```，浏览器访问```localhost:8002```