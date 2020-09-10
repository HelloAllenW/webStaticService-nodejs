# 利用 nodejs 创建静态web服务器
> 就是创建了一个可以通过 localhost:xxxx/xxx.html 访问本地静态页面的功能
1. 本例利用nodejs的http、fs、path等模块实现了简单的web服务器功能。即开启服务后，将静态资源部署到相应目录下，可以通过开启的服务进行访问。类似于我们之前部署web服务到tomcat下便可以通过http访问。

2. 先开启服务：在项目根目录下执行```node 00service.js```，浏览器访问```localhost:8002```

# nodejs 相关知识点

## nodejs中包括核心模块、第三方模块、自定义模块
### 核心模块 - fs模块
```
fs.stat 检测是文件还是目录 
fs.mkdir 创建目录
fs.writeFile 创建并写入文件
fs.appendFile 追加文件
fs.readFile 读取文件
fs.readdir 读取目录
fs.rename 重命名 移动文件
fs.rmdir 删除目录
fs.unlink 删除文件

fs.createReadStream 需要读取比较大的文件时，可以使用流读取
fs.createWriteStream 流写入
```

### 第三方模块
```
npm install xx --save
// 加上 --save 的话，会在package.json中的dependencies中生成此包的记录
```

### 自定义模块
```
var db = require('db')
// nodejs默认会找node_modules对应模块里面的index.js，如果没有又不想让报错的话可通过配置文件解决：
// 在对应文件夹下 npm init --yes 生成package.json里面定义了入口文件
```

## Nodejs的非阻塞I/O、异步、事件驱动
> 解决了获取异步方法的数据问题（大家都知道，直接获取异步方法数据会返回undefined）；
除了下面的事件驱动方法解决，还可以采用回调方法解决：
```
var events=require('events')
var EventEmitter = new events.EventEmitter()
EventEmitter.on('data', function(mime){  }) // 监听广播
EventEmitter.emit('on', data) // 触发广播 
```

## 其他
1. supervisor实现热加载
2. commonjs 是JavaScript的标准库，就是模块化的标准，nodejs是commonjs（模块化）的实现
3. silly-datetime可用来格式化日期，详细使用在npm官网中查找
4. 路由 指的是针对不同的请求URL，处理相对应的业务逻辑