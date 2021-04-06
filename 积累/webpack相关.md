
## babel和polyfill

babel是针对浏览器进行的向下兼容操作，相当于将es next转化为es5的语法，解决的是语法层面的操作

polyfill是解决针对es next提供的API层面的兼容问题

polyfill常见类型：

* babel-polyfill: 向全局对象和内置对象的prototype是那个新增方法。缺点：容易造成全局污染，包过大
* babel-runtime: 按需引用。缺点：需要多处使用时，多次引用
* babel-plugin-transform-runtime: 自动根据新API去babel-runtime中获取API转换方法
