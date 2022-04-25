# 计时器
## 相关函数
### setTimeout
#### setTimeout基础
- 简介：设置一个计时器，在指定时间之后执行一个函数或代码块
- 语法：setTimeout(func|code, [delay, arg1, arg2, ...])
    - 参数说明：
      - delay以毫秒为单位，默认值为0。注意这里的delay代表的是最小延迟，实际的延迟时间要长一些。
      - delay是number类型，如果传入的值不是number，会被强制转换为number。
- 返回值：一个正整数，这个正整数可以传递给clearTimeout()用来取消这个计时器。

```javascript
const sayBye = (name) => console.log(`bye~  ${name}`);
const sayHi = (name) => console.log(`hi!  ${name}`);

setTimeout(sayBye, 5000, "lululu");
sayHi("lululu");
//hi!  lululu
//bye~  lululu
```

#### 理解setTimeout
setTimout()是一个异步函数(asynchronous function)，意思就是计时器函数不会暂停call stack中其它函数的执行。用上面的例子来说就是：我定义了一个计时器，5s之后执行一个sayBye函数，call stack中位于我计时器后面的sayHi函数并不会暂停5s等我执行完sayBye之后再执行，它会立即执行。而我的sayBye在浏览器计时5s之后会推入callback queue中，event loop在检测到call stack为空的时候才会将sayBye推入call stack中继续执行。

即使不设置delay，setTimeout()中传入的函数也不会立即执行，它会被立即推入到callback queue中，当call stack中函数执行完之后才会被event loop重新推入call stack中。

### setInterval
#### setInterval基础
- 简介：设置一个计时器，以指定的时间间隔来周期性执行一个函数
- 语法：setInterval(func|code, [delay, arg1, arg2, ...])


### clearTimeout
传入setTimeout返回的值用做参数来取消计时器。
### clearInterval
传入setInterval返回的值用做参数来取消计时器。

