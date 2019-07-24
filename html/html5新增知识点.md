## 常用语义标签
   | 标签        | 语义    |
   | --------   | -----:   |
   | `<nav>`        | 导航      |
   | `<header>`        | 页眉      |
   | `<footer>`        | 页脚      |
   | `<section>`      | 区块      |
   | `<article>`        | 文章      |
   | `<aside>`        | 侧边栏      |
   | `<progress>`        | 进度条      |

## 新增表单输入类型
   | 类型        | 使用示例    |   含义   |
   | --------   | -----:   |  ----  |
   | email        | `<input type="email">` |   输入邮箱格式  |
   | Tel        | `<input type="tel">` |   输入手机号码格式  |
   | url        | `<input type="url">` |   输入url格式  |
   | number        | `<input type="number">` |   输入数字格式  |
   | search        | `<input type="search">` |   搜索框（体现语义化）  |
   | range        | `<input type="range">` |   自由拖动滑块  |
   | color        | `<input type="color">` |   拾色器  |
   | time        | `<input type="time">` |     |
   | date        | `<input type="date">` |     |
   | datetime        | `<input type="datetime">` |     |
   | month        | `<input type="month">` |     |
   | week        | `<input type="week">` |     |
   
## 新增表单元素
   | 元素 | 语义 |
   | ---- | --- |
   | `<datalist>` | 数据列表 |
   | `<keygen>` | 生成加密字符串 |
   | `<output>` | 输出结果 |
   | `<meter>` | 度量器 |
   
## 新增表单属性
   | 属性        | 用法    |   含义   |
   | --------   | -----:   |  ----  |
   | placeholder        | `<input type="text" placeholder="请输入用户名">` |   占位符  |
   | autofocus        | `<input type="text" autofocus>` |   自动获得焦点  |
   | multiple        | `<input type="file" multiple>` |   多文件上传  |
   | autocomplete        | `<input type="text" autocomplete="off">` |   自动完成  |
   | form        | `<input type="text" form="某表单ID">` |   所属表单id  |
   | novalidate        | `<form novalidate></form>` |   关闭验证  |
   | required        | `<input type="text" required>` |   必填项  |
   | novalidate        | `<form novalidate></form>` |   关闭验证  |
   | pattern        | `<input type="text" pattern="\d">` |   自定义验证  |
   
## 多媒体
   + 音频<audio>
        + `<audio src="./test.mp3"></audio>`
        + 兼容写法
            ```$xslt
            <audio controls>
                <source src="./test/map3">
                <source src="./test/wav">
                <source src="./test/ogg">
            </audio>
          ```
        + autoplay 自动播放
        + controls 是否显不默认播放控件
        + loop 循环播放
        
   + 视频<video>
        + `<video src="./test.mp4" controls></video>`
        + 兼容写法
            ```$xslt
            <video controls>
                <video src="./test/map4">
                <video src="./test/ogg">
            </audio>
          ```
        + autoplay 自动播放
        + controls 是否显示默认播放控件
        + loop 循环播放
        + width 设置播放窗口宽度
        + height 设置播放窗口的高度（查询浏览器支持情况）
