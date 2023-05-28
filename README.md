# Go Gin Example 

`gin` 的一个例子，实现了许多常见的特性。学习自煎鱼大佬  [[原项目地址]](https://github.com/eddycjy/go-gin-example)

## 安装
```
$ go get github.com/lixichongAAA/go-gin-example
```

## 如何运行

### 必需

- MySQL
- Redis

### 准备

创建一个 `blog` 的数据库，导入建表的 [SQL](https://github.com/lixichongAAA/go-gin-example/blob/master/sql/blog.sql)

### 配置

你应该修改 `conf/app.ini` 配置文件

```
[database]
Type = mysql
User = ...
Password = Your password
Host = 127.0.0.1:3306
Name = blog
TablePrefix = blog_

[redis]
Host = 127.0.0.1:6379
Password =
MaxIdle = 30
MaxActive = 30
IdleTimeout = 200
...
```
### 运行

```
$ cd 到你的项目根目录

$ go run main.go
```

项目的运行信息和已存在的 API's

```
[2023-05-28 16:54:41] [info] replacing callback `gorm:update_time_stamp` from /home/lxc/go-gin-example/models/models.go:40  

[2023-05-28 16:54:41] [info] replacing callback `gorm:update_time_stamp` from /home/lxc/go-gin-example/models/models.go:41  

[2023-05-28 16:54:41] [info] replacing callback `gorm:delete` from /home/lxc/go-gin-example/models/models.go:42  
[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:   export GIN_MODE=release
 - using code:  gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /export/*filepath         --> github.com/gin-gonic/gin.(*RouterGroup).createStaticHandler.func1 (3 handlers)
[GIN-debug] HEAD   /export/*filepath         --> github.com/gin-gonic/gin.(*RouterGroup).createStaticHandler.func1 (3 handlers)
[GIN-debug] GET    /upload/images/*filepath  --> github.com/gin-gonic/gin.(*RouterGroup).createStaticHandler.func1 (3 handlers)
[GIN-debug] HEAD   /upload/images/*filepath  --> github.com/gin-gonic/gin.(*RouterGroup).createStaticHandler.func1 (3 handlers)
[GIN-debug] GET    /qrcode/*filepath         --> github.com/gin-gonic/gin.(*RouterGroup).createStaticHandler.func1 (3 handlers)
[GIN-debug] HEAD   /qrcode/*filepath         --> github.com/gin-gonic/gin.(*RouterGroup).createStaticHandler.func1 (3 handlers)
[GIN-debug] GET    /auth                     --> github.com/lixichongAAA/go-gin-example/routers/api.GetAuth (3 handlers)
[GIN-debug] GET    /swagger/*any             --> github.com/swaggo/gin-swagger.CustomWrapHandler.func1 (3 handlers)
[GIN-debug] POST   /upload                   --> github.com/lixichongAAA/go-gin-example/routers/api.UploadImage (3 handlers)
[GIN-debug] GET    /api/v1/tags              --> github.com/lixichongAAA/go-gin-example/routers/api/v1.GetTags (4 handlers)
[GIN-debug] POST   /api/v1/tags              --> github.com/lixichongAAA/go-gin-example/routers/api/v1.AddTag (4 handlers)
[GIN-debug] PUT    /api/v1/tags/:id          --> github.com/lixichongAAA/go-gin-example/routers/api/v1.EditTag (4 handlers)
[GIN-debug] DELETE /api/v1/tags/:id          --> github.com/lixichongAAA/go-gin-example/routers/api/v1.DeleteTag (4 handlers)
[GIN-debug] POST   /tags/export              --> github.com/lixichongAAA/go-gin-example/routers/api/v1.ExportTag (3 handlers)
[GIN-debug] POST   /tags/import              --> github.com/lixichongAAA/go-gin-example/routers/api/v1.ImportTag (3 handlers)
[GIN-debug] GET    /api/v1/articles          --> github.com/lixichongAAA/go-gin-example/routers/api/v1.GetArticles (4 handlers)
[GIN-debug] GET    /api/v1/articles/:id      --> github.com/lixichongAAA/go-gin-example/routers/api/v1.GetArticle (4 handlers)
[GIN-debug] POST   /api/v1/articles          --> github.com/lixichongAAA/go-gin-example/routers/api/v1.AddArticle (4 handlers)
[GIN-debug] PUT    /api/v1/articles/:id      --> github.com/lixichongAAA/go-gin-example/routers/api/v1.EditArticle (4 handlers)
[GIN-debug] DELETE /api/v1/articles/:id      --> github.com/lixichongAAA/go-gin-example/routers/api/v1.DeleteArticle (4 handlers)
[GIN-debug] POST   /api/v1/articles/poster/generate --> github.com/lixichongAAA/go-gin-example/routers/api/v1.GenerateArticlePoster (4 handlers)
2023/05/28 16:54:41 [info] start http server listening :8000
```

Swagger 文档
见 swagger.png

## 特性

- RESTful API
- Gorm
- Swagger
- logging
- Jwt-go
- Gin
- Graceful restart or stop (fvbock/endless)
- App configurable
- Cron
- Redis



