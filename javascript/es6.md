## es6新增关键字
   + let 
        + let不存在变量预解析
        + 不能重复使用let定义同一个变量
        + let会造成块级作用域
   + const （常量）
        + 和let相似
        + const一旦定义好了，如果重新赋值会报错
        
## 变量解构赋值
   + 用法示例：
        + `let [a,b,c] = [3,4,5];`
        + `let [a,b,c] = [2,,4]`
        + `let [a,[b],c] = [2,[3],4];`
        + `let [a,b=3,c] = [2,,4];`
        
## 对象的解构赋值
   + `let {name,hobby} = {name: 'zs', hobby: 'node '};`
   
## 字符串扩展
   + includes 检测是否包含指定支付串
   + startsWith 检测以指定字符串开头
   + endsWith 检测以指定字符串结尾
   + 模板字符串：``
        + 模板字符串里面还支持运算和函数：
        + ```
            let tepmp1 = `${parseInt(2.11)}`;
            let temp2 = `${100 + 200}`;
            let temp3 = `${ad(2,3)}`;
            ```

## 函数扩展
   + 参数的默认赋值：`function (a = 1) {}`
   + 参数的接收：`function (a,b,...rest) {}`
   + 箭头函数：`() => {}`
        + 注意事项：箭头函数不能做为构造函数
        
## 对象的简写
   + 如果属性值刚好和外面的变量名一样，则可以简写属性
   + 示例：`let foo = 'bar';let baz = {foo};`
   
## 类
   + 类等价于我们之前学过的构造函数，只不过语法不一样而已
   + 示例： 
   + ```
        class ${
            static isNull(data){//静态方法
                return Object.prototype.toString.call(data) === '[object Null]';
            }
        
            constructor(str){
                this.eles = document.querySelectorAll(str);
            }
        
            getLength(){
                return this.eles.length;
            }
        }
        new $('zs');
        ```
   + 继承 
        + 关键字 extends super
        + 示例：
        + ```
            class Person{
                constructor(name,age){
                    this.name = name;
                    this.age = age;
                }
                eat(){
                    console.log("吃饭");
                }
            }
            
            class Student extends Person{
                constructor(name,age,school){
                    super(name,age);//这一步是必须的，如果不写会报错
                    this.school = school;
                }
            }
            
            var xiaoMing = new Student("xiaoMing",18,'xuexiao');
            xiaoMing.eat();
            ```
            
## 模块化
   + 可以在任何变量或者函数前面加上export关键字，就可以把它导出
   + ```
        export const PI = Math.PI;
        export let func = () => {};
        ```
   + ```
        import {PI, func} form './test'
        ```
   + 默认导出
        + `export default () => console.log(默认导出);`
        + `import b from './b';`
