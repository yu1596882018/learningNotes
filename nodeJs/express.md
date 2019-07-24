## 创建一个HelloWorld程序
   + ```
        var express = require('express');
        var app = express();
        app.use(function (req, res) {
            res.send('Hello World')
        });
        app.listen(3000, function () {
            console.log('server is listening at port 3000')
        });
        ```

## 静态资源处理
   + app.use(express.static('./static'));
   + 支持多个
   + 假如同时指定的二个静态资源文件夹里面有同一个名字的文件，会先找第一个。

## request对象
   + url 请求链接
   + method 请求类型
   + query 参数
   
## 路由
   + express.Router()
   + 实例
        ```
            var express = require('express');
            var router = express.Router();
            router.route('/').get(function (req, res) {
                res.send('请求的路径是/，请求的方法是GET');
            }).post(function (req, res) {
                res.send('请求的路径是/，请求的方法POST');
            })
        ```
        
## 重定向
   + node原生`res.writeHead(302,{'Location'});`
   + express提供方法：res.redirect(302, 'http:/baidu.com');
    
## 中间件
   + 语法形式：`app.use(中间件)`
   + ```
        function uselessMiddleware(req, res, next) {
            next();
        }
        ```
