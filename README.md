<p align="center">
  <a href="https://ok.zhxu.cn/" target="_blank">
    <img width="128" src="https://images.gitee.com/uploads/images/2020/0511/091408_c26f1306_1393412.png" alt="logo">
  </a>
</p>
<p align="center">
    <a href="https://maven-badges.herokuapp.com/maven-central/com.ejlchina/okhttps/"><img src="https://maven-badges.herokuapp.com/maven-central/com.ejlchina/okhttps/badge.svg" alt="Maven Central"></a>
    <a href="https://gitee.com/troyzhxu/okhttps/blob/master/LICENSE"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License"></a>
    <a href="https://github.com/troyzhxu"><img src="https://img.shields.io/badge/%E4%BD%9C%E8%80%85-troyzhxu-orange.svg" alt="Troy.Zhou"></a>
</p>

## 文档

网址：https://ok.zhxu.cn

## 为什么用

　　OkHttps 是近期开源的对 OkHttp3 轻量封装的框架，它独创的异步预处理器，特色的标签，灵活的上传下载进度监听与过程控制功能，在轻松解决很多问题的同时，设计上也力求纯粹与优雅。

* 超级优雅的 API 设计，且链式调用，让你顺滑到底！
* BaseURL、URL占位符、HTTP 同步 异步、WebSocket，让你想干啥就干啥！ 
* JSON、Xml 等自动封装与解析，且支持与任意格式的数据解析框架集成，想用啥就用啥！
* 同步拦截器、异步预处理器、回调执行器、全局监听、回调阻断 等等，让你扩展无限功能！
* 文件上传下载（过程控制、进度监听），上传下载如此简单！
* 单方法回调，充分利用 Lambda 表达式，让你代码超级简洁！
* 超级轻量，但性能卓越！

## 如何使用

### 如艺术一般优雅，像 1、2、3 一样简单

```java
// 同步 HTTP
List<User> users = OkHttps.sync("/users") 
        .get()                          // GET请求
        .getBody()                      // 响应报文体
        .toList(User.class);            // 自动反序列化 List 

// 异步 HTTP
OkHttps.async("/users/1")
        .setOnResponse(res -> {
            // 自动反序列化 Bean 
            User user = res.getBody().toBean(User.class);
        })
        .get();                         // GET请求

// WebSocket
OkHttps.webSocket("/chat") 
        .setOnMessage((WebSocket ws, Message msg) -> {
            // 从服务器接收消息
            Chat chat = msg.toBean(Chat.class);
            // 向服务器发送消息
            ws.send(chat); 
        })
        .listen();                     // 启动监听
```

### 请求三部曲

#### 第一步、确定请求方式
    
* 同步 HTTP - `sync` 方法
* 异步 HTTP - `async` 方法
* WebSocket - `webSocket` 方法

#### 第二步、构建请求任务

* `addXxxPara` - 添加请求参数
* `setOnXxxx` - 设置回调函数
* `tag` - 添加标签
* ...

#### 第三步、调用请求方法

HTTP 请求方法：

* `get()` - GET 请求
* `post()` - POST 请求
* `put()` - PUT 请求
* `delete()` - DELETE 请求
* ...

Websocket 方法：

* `listen()` - 启动监听

#### 任意网络请求，都遵循请求三部曲！

## 相关项目

项目 | 最新版本 | 描述
-|-|-
[okhttps](https://gitee.com/ejlchina-zhxu/okhttps/tree/dev/okhttps) | 3.5.2 | OkHttps 核心模块
[okhttps-fastjson](https://gitee.com/ejlchina-zhxu/okhttps/tree/dev/okhttps-fastjson) | 3.5.2 | 与 fastjson 集成
[okhttps-gson](https://gitee.com/ejlchina-zhxu/okhttps/tree/dev/okhttps-gson) | 3.5.2 | 与 gson 集成
[okhttps-jackson](https://gitee.com/ejlchina-zhxu/okhttps/tree/dev/okhttps-jackson) | 3.5.2 | 与 jackson 集成
[okhttps-stomp](https://gitee.com/ejlchina-zhxu/okhttps/tree/dev/okhttps-stomp) | 3.5.2 | 超级轻量的 Stomp 客户端
[okhttps-xml](https://gitee.com/ejlchina-zhxu/okhttps/tree/dev/okhttps-xml) | 3.5.2 | XML 解析扩展

## 超详细教程，请查看：https://ok.zhxu.cn

## 联系方式

* 微信：<img src="https://images.gitee.com/uploads/images/2020/0718/142637_87d27a5c_1393412.png" width="700px">
* 由于近期交流群的二维码被爬，扫码入群方式已被关闭
库的使用上若有疑问，可先加微信【18556739726】（请备注 OkHttps）再入群交流

## 友情链接

[**[ Bean Searcher ]** 比 MyBatis 效率快 100 倍的条件检索引擎，天生支持联表，使一行代码实现复杂列表检索成为可能！](https://github.com/ejlchina/bean-searcher)

[**[ SA Token ]** 一个轻量级 Java 权限认证框架，让鉴权变得简单、优雅！](https://github.com/dromara/Sa-Token)

[**[ hrun4j ]** 接口自动化测试解决方案 --工具选得好，下班回家早；测试用得对，半夜安心睡 ](https://github.com/lematechvip/hrun4j)

[**[ Json Kit ]** 超轻量级 JSON 门面工具，用法简单，不依赖具体实现，让业务代码与 Jackson、Gson、Fastjson 等解耦！](https://gitee.com/ejlchina-zhxu/jsonkit)

## 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request

