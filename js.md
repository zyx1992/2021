一、原型链

函数都是由Function创造的，对象都是由Object创造的。

```js
function F() {}
F.__proto__ == Function.prototype   
F.prototype.__proto__ == Object.prototype  // 函数F的原型是个对象，所以要指向对象的原型对象
F.__proto__.__proto__ == Object.prototype
```
