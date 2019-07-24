## 实现局部刷新的方式2  Ajax 异步发送请求
实现异步发送请求的4个步骤
1. 创建发送请求的对象 xhr 有兼容性问题 了解即可
  //谷歌
  var xhr = new XMLHttpRequest();
  //IE6
  var xhr = new ActiveXObject("Microsoft.XMLHTTP");
2. 准备发送 调用open方法 
    第一个参数的请求的方式 get 或者post  第二个参数是请求的url get方式的话直接在后面跟参数 第三个参数的是是否开启异步 true开启 false不开启 默认true开启异步
    xhr.open('get','page8-ajax.php?username='+username+'&password='+password,true);
3. 执行发送动作
  xhr.send();
4. 监视发送后的响应状态的改变
  xhr.addEventListener('readystatechange',function () {
    得到返回的数据 
    var result = xhr.responseText;
  });

如果是POST请求
1. 创建发送请求的对象 xhr 有兼容性问题 了解即可
  //谷歌
  var xhr = new XMLHttpRequest();
  //IE6
  var xhr = new ActiveXObject("Microsoft.XMLHTTP");
2. 准备发送 调用open方法 
    第一个参数的请求的方式 get 或者post  第二个参数是请求的url post方式只要写url不需要带参数  第三个参数的是是否开启异步 true开启 false不开启 默认true开启异步
    xhr.open('get','page8-ajax.php',true);
3. 设置请求头
   xhr.serRequestHeader('Content-Type','application/x-www-form-urlencoded');
4. 执行发送动作  
  post的参数通过 通过在send方法里面传入 直接把参数拼接好传入进去
  xhr.send(username='+username+'&password='+password);
5. 监视发送后的响应状态的改变
  xhr.addEventListener('readystatechange',function () {
    得到返回的数据 
    var result = xhr.responseText;
  });

get 和 post的区别 
就是get 请求参数通过url传递
post通过send传递 而且必须设置请求头

## 请求的状态码

xhr.readyState属性的值
0  表示 xhr对象创建成果
1  表示 已经发送了请求
2  表示 浏览器已经收到了服务器响应的数据 (还没解析)
3  表示 浏览器正在解析数据
4  表示 数据已经解释完成  

HTTP 创建状态码
xhr.status 
200 表示成功
404 表示没有找到
500 服务器错误


## get 和  post 请求的方式

get 和 post的作用都是为了实现前后端的数据传输 
前端把数据传给后端

get 的方式是使用url地址栏来传输 get有大小限制比较小 get相对不安全 get一般用来作为查询条件获取数据 
post 是通过formData里面传参 post也有限制但是比较大 post相对安全 
post一般用来提交数据

## ajax中 的get请求方式和post的区别
get的方式是参数写在url后面 
同时参数还需要编码 encodeURI()

xhr.open('get','url'+pramas,true);
//兼容IE
xhr.send(null);

post的方式 url只要写url不需要带参数
post请求在form Data
post请求要需要设置请求头
xhr.setRequestHeader("Content-Type","application/x-www-form-urlencoded");
xhr.open('post','url',true)
键=值&键=值
xhr.send(参数)
