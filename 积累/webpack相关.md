
## babel和polyfill

babel是针对浏览器进行的向下兼容操作，相当于将es next转化为es5的语法，解决的是语法层面的操作

polyfill是解决针对es next提供的API层面的兼容问题

polyfill常见类型：

* babel-polyfill: 向全局对象和内置对象的prototype是那个新增方法。缺点：容易造成全局污染，包过大
* babel-runtime: 按需引用。缺点：需要多处使用时，多次引用
* babel-plugin-transform-runtime: 自动根据新API去babel-runtime中获取API转换方法

## compiler和compliation

compiler: 属于webpack的全局单例，上面会有webpack构建上的所有事件

compliation: 每次构建和热更新都会由compiler生成一个新的compliation对象，服务输出档次构建的上下文信息

## sourcemap如何查询

names: ['i', 'am', 'chrise']

mappings: "AAAb, SHSHHS, JJSDJS"

相当于mapping中针对每个names进行位置映射，【输出文件列位置】|【引用文件索引】|【输入文件行索引】【输入文件列索引】|【数据索引】，其中每个位置为了优化字节，想要省略“|”，但是原来的数字位置无法合并，所以通过base64的转码生成字符的位置编码


