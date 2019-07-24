## 选择器
   + 属性选择器
        + E[attr] 表示存在attr属性即可；
        + E[attr=val] 表示属性值完全等于val；
        + E[attr*=val] 表示的属性值里包含val字符并且在“任意”位置；
        + E[attr^=val] 表示的属性值里包含val字符并且在“开始”位置；
        + E[attr$=val] 表示的属性值里包含val字符并且在“结束”位置；
   + 伪类选择器
        + 结构伪类
            + E:first-child第一个子元素
            + E:last-child最后一个子元素
            + E:nth-child(n) 第n个子元素，计算方法是E元素的全部兄弟元素；
            + E:nth-last-child(n) 同E:nth-child(n) 相似，只是倒着计算；
            + E:empty 选中没有任何子节点的E元素；（使用不是非常广泛）
        + 目标伪类
            + E:target 结合锚点进行使用，处于当前锚点的元素会被选中；
        + 伪元素选择器
            E::first-letter文本的第一个单词或字（如中文、日文、韩文等）；
            E::first-line 文本第一行；
            E::selection 可改变选中文本的样式；
            E:after
            E:before
        + ":" 与 "::" 区别在于区分伪类和伪元素
        + 结构性伪类选择器
            + E:first-of-type匹配同类型中的第一个元素E。
            + E:last-of-type匹配同类型中的最后一个元素E。
            + E:nth-of-type(n) 匹配同类型中的第n个元素E。
    + 结构选择器
        + 相邻选择符 (E+F)
            + 语法：E+F{ }
            + 说明：选择紧贴在E元素之后F元素。 
        + 兄弟选择符 (E~F)
            + 语法：E+F{ }
            + 说明：选择紧贴在E元素之后F元素。 

## 文本
   + text-shadow 文本阴影，可分别设置偏移量、模糊度、颜色（可设透明度）。
        + 水平偏移量 正值向右 负值向左；
        + 垂直偏移量 正值向下 负值向上；
        + 模糊度是不能为负值；
        
## 边框
   + 边框圆角 border-radius
   + 边框阴影 box-shadow
        + 水平偏移量 正值向右 负值向左；
        + 垂直偏移量 正值向下 负值向上；
        + 模糊度是不能为负值；
        + inset可以设置内阴影；
   + 边框图片 border-image
   
## 盒模型
   + 设置box-sizing值，指定盒模型
        + box-sizing: border-box  计算方式为content = width – border - padding
        + box-sizing: content-box  计算方式为content = width
        
## 背景
   + background-size设置背景图片的尺寸
        + cover 填充满背景区域
        + contain 完整显示
   + background-origin设置背景定位的原点
        + border-box以边框做为参考原点；
        + padding-box以内边距做为参考原点；
        + content-box以内容区做为参考点；
   + background-clip设置背景区域裁切
        + border-box裁切边框以内为背景区域；
        + padding-box裁切内边距以内为背景区域；
        + content-box裁切内容区做为背景区域；
   + 以逗号分隔可以设置多背景，可用于自适应局
        
## 渐变
   + linear-gradient线性渐变指沿着某条直线朝一个方向产生渐变效果。
        + 方向
        + 起始颜色
        + 终止色
        + ```$xslt
            background-image: linear-gradient(
                    90deg,
                    yellow 25%,
                    green 25%,
                    green 50%,
                    blue 50%,
                    blue 75%,
                    pink 75%,
                    pink 100%
                );
            ```
   + radial-gradient径向渐变指从一个中心点开始沿着四周产生渐变效果
        + 辐射范围即圆半径 
        + 中心点 即圆的中心
        + 渐变起始色
        + 渐变终止色
        + `background-image: radial-gradient(150px at 80px 80px, yellow, green);`
        
## 过渡transition


## 2D转换
   + 移动 translate(x, y) 可以改变元素的位置，x、y可为负值；
   + 缩放 scale(x, y) 可以对元素进行水平和垂直方向的缩放，x、y的取值可为小数，不可为负值；
   + 旋转 rotate(deg) 可以对元素进行旋转，正值为顺时针，负值为逆时针；
   + 倾斜 skew(deg, deg) 可以使元素按一定的角度进行倾斜
   
## 3D转换
   + 3D坐标轴
   + 左手坐标系
   + 左手法则
   
## 动画
   + 必要元素：
        + 通过@keyframes指定动画序列；
        + 通过百分比将动画序列分割成多个节点；
        + 在各节点中分别定义各属性
        + 通过animation将动画应用于相应元素；
        
   + 关键属性：
        + animation-name设置动画序列名称
        + animation-duration动画持续时间
        + animation-delay动画延时时间
        + animation-timing-function动画执行速度，linear、ease等
        + animation-play-state动画播放状态，play、paused等
        + animation-direction动画逆播，alternate等
        + animation-fill-mode动画执行完毕后状态，forwards、backwards等
        + animation-iteration-count动画执行次数，inifinate等
        
## 伸缩布局
   + 简介：
        + 主轴：Flex容器的主轴主要用来配置Flex项目，默认是水平方向
        + 侧轴：与主轴垂直的轴称作侧轴，默认是垂直方向的
        + 方向：默认主轴从左向右，侧轴默认从上到下
        + 主轴和侧轴并不是固定不变的，通过flex-direction可以互换。
        
   + 必要元素：
        + 指定一个盒子为伸缩盒子 display: flex
        + 设置属性来调整此盒的子元素的布局方式 例如 flex-direction
        + 明确主侧轴及方向
        + 可互换主侧轴，也可改变方向
        
   + 各属性详解：
        + flex-direction调整主轴方向（默认为水平方向）
        + justify-content调整主轴对齐
        + align-items调整侧轴对齐
        + flex-wrap控制是否换行
        + align-content堆栈（由flex-wrap产生的独立行）对齐
        + flex-flow是flex-direction、flex-wrap的简写形式
        + flex控制子项目的缩放比例
        + order控制子项目的排列顺序
        
   + 多列布局
   
## web字体
   + 字体格式
        + TureTpe(.ttf)格式
        + OpenType(.otf)格式
        + Web Open Font Format(.woff)格式
        + Embedded Open Type(.eot)格式
        + SVG(.svg)格式
   + 案例：
        ```$xslt
            @font-face {font-family: "webfont";
              src: url('webfont.eot'); /* IE9*/
              src: url('webfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
              url('webfont.woff') format('woff'), /* chrome、firefox */
              url('webfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
              url('webfont.svg#webfont') format('svg'); /* iOS 4.1- */
            }
            
            .web-font {
              font-family:"webfont" !important;
              font-size:16px;
              font-style:normal;
              -webkit-font-smoothing: antialiased;
              -webkit-text-stroke-width: 0.2px;
              -moz-osx-font-smoothing: grayscale;
            }
        ```
   + 推荐http://www.zhaozi.cn/、http://www.youziku.com/ 查找更多中文字体
   + 字体图标，如：Font Awesome
