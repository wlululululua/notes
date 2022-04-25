# 提升
## 简介
提升发生在执行上下文创建的第一个阶段，即Memory Creation Phase中。在JS代码开始执行之前，就已经在内存中为变量和函数分配了内存空间，所以，我们能够在代码执行到变量或者函数声明之前访问到它，这就是提升。

## 函数提升
函数提升使我们能够很方便的在程序中调用函数，可以随处调用函数，即使在该函数声明之前调用也是可以的。

原因：在执行上下文创建的第一个阶段Memory Creation Phase中，会为函数声明(function关键字声明)分配内存空间，存放该函数所有的代码。
```javascript
sayHi();//在函数声明之前调用函数不会报错，因为内存空间中已经有sayHi函数
function sayHi() {
    console.log("hi~");
}
```

## 变量提升
在执行上下文创建的第一个阶段Memory Creation Phase中，会为变量声明(var let const)分配内存空间，但它们各自又有一些不同。
### var
var声明的变量中存放的是一个特殊值：undefined
var声明的变量可以在声明之前访问，不会报错。
```javascript
console.log(name);//undefined
var name = "lululu";
console.log(name);//lululu 
```

### let & const
#### Temporal Dead Zone

## 类提升


## 参考
- [Namaste JavaScript 🙏 Ep.3+Ep.8](https://www.youtube.com/playlist?list=PLlasXeu85E9cQ32gLCvAvr9vNaUccPVNP)
- [MDN Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)