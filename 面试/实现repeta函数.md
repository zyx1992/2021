## 题目：
定义这样一个函数 function repeat(func, times, wait) { }
参数分别是需要 repeat的函数， repeat的次数，每次repeat的间隔 使用方式如下 调用这个函数能返回一个新函数。
比如传入的是alert， 执行10次，间隔5秒 var repeatedFun = repeat(alert, 10, 5000);
调用返回的这个新函数，如:   repeatedFun("hellworld");
会alert十次 helloworld

## 解法

1. promise方式

```js
function repeat(func, times, wait) {
  return async (...args) => {
    for(let i = 0; i < times; i++) {
      await new Promise(() => {
        setTimeout(() => {
         func()
         resolve()
        }, wait)
      })
    }
  }
}
```

2. setInterval方式

```js 
function repeat(func, times, wait) {
  return (...args) => {
     let count = 0;
     let timeId = setInterval(() => {
        if(count === times) {clearInterval(timeId)}
        func(args)
        count++
     }, wait)
  }
}
```

3. setTimeout方式
```js
function repeat(func, times, wait) {
  return (...args) => {
    for(let i = 0; i < times; i++) {
      setTimeout(() => {
        func(args)
      }, wait * i)
    }
  }
}
```
