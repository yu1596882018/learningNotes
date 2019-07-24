## 内容概念
   + 文档(Document)：就是指HTML或者XML文件
   + 节点(Node)：HTML文档中的所有内容都可以称之为节点，常见的节点有元素节点 属性节点 文本节点 注释节点
   + 元素(Element)：HTML文档中的标签可以称为元素

## 获取元素
   + getElementById
   + getElementsByTagName

## 类名属性
+ dom.className

## 样式属性
   + dom.style
   + style属性是对象，style对象的属性是字符串
   + style只能获取和设置行内样式

## 内部文本属性
   + innerHTML
   + innerText
   + textContent
   + 兼容案例：
        ```$xslt
            if (typeof element.innerText === "string") {
                element.innnerText
            } else {
                element.textContent
            }
        ```
   
## 常用表单属性
   + 常见的表单元素属性有： type、value、checked、selected、disabled
       + type可以设置input元素的类型
       + value可以设置input元素的值
       + checked可以设置input元素是否选中
       + selected 可以设置下拉列表select中的option是否被选中
       + disabled 可以设置input元素是否被禁用

## 自定义属性
   + getAttribute() 获取
   + setAttribute() 设置
   + removeAttribute() 移除

## 节点类型
   + node.nodeType
       + 值：1表示元素节点 2表示属性节点 3表示文本节点
   + 所有获取节点相关属性都没有兼容性问题
       + childNodes 	//子节点 
       + children		//子元素 虽然不是早期DOM标准中的方法，但是所有浏览器都支持
       + 
       + nextSibling //下一个兄弟节点
       + nextElementSibling //下一个兄弟元素 有兼容性问题
       + previousSibling//上一个兄弟节点
       + previousElementSibling //上一个兄弟元素 有兼容性问题
       + 
       + firstChild //第一个节点
       + firstElementChild //第一个子元素 有兼容性问题
       + lastChild //最后一个子节点
       + lastElementChild //最后一个子元素 有兼容性问题
       + 
       + parentNode //父节点 （一定是元素节点，所以无需处理）
   + 案例：
       ```$xslt
           //封装
           function getFirstElement(element) {
               if (element.firstElementChild) {
                   return element.firstElementChild;
               } else {
                   //子节点所有浏览器都支持
                   var el = element.firstChild;//假设这个是我们要的
                   while (el && 1 !== el.nodeType) {
                       el = el.nextSibling;//找el的下一个兄弟节点 直到找到元素节点
                   }
                   return el;
               }
           }
       ```

## 动态创建元素
   + 插入和移除节点
       + 在父元素中的最后追加子元素
            + father.appendChild(要追加的元素);
       + 在父元素中的某个子元素前面插入子元素
            + father.insertBefore(要插入的元素,插到这个元素的前面);
       + 从父元素中移除子元素
            + father.removeChild(要移除的子元素);
   + 动态创建结构
       + 方式一：直接在文档中书写
            + document.write(“内容”)
       + 方式二：改变元素对象内部的HTML
            + innerHTML=”内容”
       + 方式三：创建或克隆节点并追加
            + createElement()
            + cloneNode()
       + 通过这两种方法创建出来的元素只是保存在内存中，必须放到页面上才行!

## offset系列
   + offsetWidth 返回一个元素的布局宽度
   + offsetHeight 返回一个元素的布局高度
   + offsetLeft 距离上一个offsetParent的左边距
   + offsetTop 距离上一个offsetParent的上边距
   + offsetParent
        + 返回一个指向最近的（closest，指包含层级上的最近）包含该元素的定位元素。
        + 如果没有定位的元素，则 offsetParent 为最近的 table, table cell 或根元素（标准模式下为 html；quirks 模式下为 body）。
        + 当元素的 style.display 设置为 "none" 时，offsetParent 返回 null。
        
## scroll系列
   + 对象内部实际内容的高度/宽度：
   + scrollHeight
   + scrollWidth
   + 被卷去部分的 顶部/左侧 到可视区域 顶部/左侧 的距离：
   + scrollTop  
   + scrollLeft
   + 页面滚动座标兼容写法
        + `var scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop || 0;`

## client系列
   + 元素可视区宽高
   + clientWidth
   + clientHeight
   + 元素占位不可视距离，如果有滚动条会包含滚动条的宽度
   + clientTop
   + clientLeft
   + 网页可视区宽高的兼容写法
        + var clientWidth = window.innerWidth|| document.documentElement.clientWidth|| document.body.clientWidth|| 0;

## 获取计算后的样式属性值
   + getComputedStyle 兼容ie9以上
   + currentStyle 兼容ie6以上
   + 兼容案例：
   ```
        function getStyle(obj, attr) {
           if (window.getComputedStyle) {
               return window.getComputedStyle(obj, null)[attr];
           } else {
               return obj.currentStyle[attr];
           }
       }
   ```
   + getBoundingClientRect 有兼容问题
   
## 事件对象
   + event参数，支持ie9以上
   + 事件对象的兼容性写法 `var event = event || window.event;`
   + 三个重要座标
        + clientX  clientY
        + 当前窗口的左上角为基准点
        + pageX    pageY
        + 以当前文档的左上角为基准点
        + IE678不支持pageX和pageY 但是我们可以采取另一种方式 client和documentElement.scroll在IE678中都支持
        ```$xslt
            var pageY = event.pageY || event.clientY + document.documentElement.scrollTop;
            var pageX = event.pageX || event.clientX + document.documentElement.scrollLeft;
        ```
        + screenX  screenY
        + 当前屏幕的左上角为基准点
        
## 注册事件的两种方式
   + addEventListener
   + 用法：element.addEventListener(“事件类型”,”事件处理函数”,”是否使用捕获”)
   + removeEventListener
   + attachEvent 兼容ie写法
   
## 事件的三个阶段
   + 捕获阶段
   + 目标阶段 执行当前对象的事件处理程序
       + 获取当前对象id`var targetId =  event.target ?  event.target.id : event.srcElement.id;`
   + 冒泡阶段
       + 阻止冒泡
       ```$xslt
        function stopPropagation(event) {
                if (event.stopPropagation) {
                    event.stopPropagation();
                } else {
                    event.cancelBubble = true;
                }
        }
       ```

## 文本操作
   + 清空选中内容
        + `window.getSelection ? window.getSelection().removeAllRanges() : document.selection.empty();`
        + 正常浏览器支持：window.getSelection() 
        + IE678以下支持：document.selection
   + 获取选中内容
        + `var txt = window.getSelection ? window.getSelection().toString() : document.selection.createRange().text;`

## window对象
   + onload（在文档装载完成后会触发  load 事件。此时，在文档中的所有对象都在DOM中，所有图片，脚本，链接以及子框都完成了装载。）
   + open（用于打开新的网页，可设置当前窗口还是新窗口）
   + setTimeout（延时器）
   + setInterval（定时器）
   + location（集合url链接相关参数与方法的对象）
        + reload()
   + navigator（用于请求运行当前代码的应用程序的相关信息，浏览器信息）
        + userAgent
   + history（提供操作浏览器会话历史）
   + screen 获取浏览器窗口的信息的对象

## 全屏
   + document.加前缀cancelFullScreen()关闭全屏
   + document.加前缀isFullscreen是否全屏  是一个属性
