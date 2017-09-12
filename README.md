##  1、目录结构

1. `models`: 存放操作数据库的文件
2. `public`: 存放静态文件，如样式、图片等
3. `routes`: 存放路由文件
4. `views`: 存放模板文件
5. `index.js`: 程序主文件
6. `package.json`: 存储项目名、描述、作者、依赖等等信息

##  2、功能与路由设计

在开发博客之前，我们首先需要明确博客要实现哪些功能。由于本教程面向初学者，所以只实现了博客最基本的功能，其余的功能（如归档、标签、分页等等）读者可自行实现。

功能及路由设计如下：

1. 注册

    1. 注册页：`GET /signup`
    2. 注册（包含上传头像）：`POST /signup`
2. 登录
    1. 登录页：`GET /signin`
    2. 登录：`POST /signin`
3. 登出：`GET /signout`
4. 查看文章
    1. 主页：`GET /posts`
    2. 个人主页：`GET /posts?author=xxx`
    3. 查看一篇文章（包含留言）：`GET /posts/:postId`
5. 发表文章
    1. 发表文章页：`GET /posts/create`
    2. 发表文章：`POST /posts`
6. 修改文章
    1. 修改文章页：`GET /posts/:postId/edit`
    2. 修改文章：`POST /posts/:postId/edit`
7. 删除文章：`GET /posts/:postId/remove`
8. 留言
    1. 创建留言：`POST /posts/:postId/comment`
    2. 删除留言：`GET /posts/:postId/comment/:commentId/remove`

由于我们博客页面是后端渲染的，所以只通过简单的 `<a>(GET)` 和 `<form>(POST)` 与后端进行交互，如果使用 jQuery 或者其他前端框架（如 angular、vue、react 等等）可通过 Ajax 与后端交互，则 api 的设计应尽量遵循 restful 风格。
