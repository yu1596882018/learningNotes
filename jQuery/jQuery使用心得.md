+ jquery中的event和event.stopPropagation已经完成兼容性处理，无需在考虑兼容性。
+ toggle方法如果控制的元素没有宽高，会一直show不会hdie
+ jQuery方法
    + /*通过width 只获取到了 内容的宽度*/
    +/* innerWidth() 内容+内边距*/
    + /* outerWidth() 内容+内边距+边框*/
    + /* outerWidth(true) 内容+内边距+边框+外边距*/jQuery方法
+ js原生属性
    + offsetWidth  内容+内边距+边框
    + clientWidth  内容+内边距
    + scrollWidth  
+ $(str,dom）表示在dom元素下找符合str的元素
