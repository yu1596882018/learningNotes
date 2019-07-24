## npm常见命令
   + npm init 用来初始化生成一个新的package.json文件，它会向用户提问一系列问题，如果你觉得不用修改默认配置，一路回车就可以了，如果你使用了-y(代表yes),则跳过提问阶段，直接生成一个新的package.json文件
   + npm install --save 包名 将安装的包添加到盘package.json的依赖中，(使用了--save的参数之后，会自动修改package.json文件) 
   + npm install --save 包名@4.2.1 --> 安装某个具体版本的npm包 简写：npm install -S
   + npm install --save 包名@latest --> 安装最新的包
   + 如果是安装多个包，可以执行npm install --save A包名 B包名
   + npm install -g 包名 全局安装一个命令行工具 
   + npm list 查看当前目录下安装的所有的包
   + npm list -g 查看全局包的安装路径下的所有的包
   + npm uninstall 包名 卸载当前目录下某个包
   + npm uninstall -g 包名 卸载全局路径下的某个包
   + npm doc 包名 自动打开浏览器，查看当前的包的文档

## npm发包流程
   + 注册npm账号
        + https://www.npmjs.com/signup
   + 初始化npm项目
        + npm init
        + main：程序的入口文件，默认是index.js.
        + devDependencies:你要发的包，所依赖的开发环境下的包。
        + repository:代码存放地址（一般是git地址）。
        + license：
        + keywords：便于搜索npm 包。
        + dependencies：你要发的包，所依赖的线上环境下的包。
   + 在你将要发包的目录下，执行：
        + `npm adduser`
        + `npm publish`
   + 包权限管理
        + 查看模块拥有者 
            + `npm owner ls <package_name>`
        + 添加一个发布者 
            + `npm owner add <user> <package_name>`
        + 删除一个发布者 
            + `npm owner rm <user> <package_name>`
   
## 加载注意点
   + 如果在当前node_modules找不到 --> 返回上一级目录里面去找【重点】
