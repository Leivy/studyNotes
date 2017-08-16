# ES6

### let和const命令

1. let--->
   1. 声明变量,只在let命令所在的代码块内有效;
   2. 不存在变量提升;只要块级作用域内存在`let`命令，它所声明的变量就“绑定”（binding）这个区域，不再受外部的影响。
   3. 暂时性死区...
   4. `let`不允许在相同作用域内，重复声明同一个变量。--->`function func(arg) {  let arg; // 报错}`
2. `const`声明一个只读的常量。一旦声明，常量的值就不能改变,const保存的指针不变
3. 从ES6开始，全局变量将逐步与顶层对象的属性脱钩。
4. 顶层对象:
   1. 浏览器里面，顶层对象是`window`，但 Node 和 Web Worker 没有`window`。
   2. 浏览器和 Web Worker 里面，`self`也指向顶层对象，但是 Node 没有`self`。
   3. Node 里面，顶层对象是`global`，但其他环境都不支持。
   4. 全局环境中，`this`会返回顶层对象。但是，Node 模块和 ES6 模块中，`this`返回的是当前模块。
   5. 函数里面的`this`，如果函数不是作为对象的方法运行，而是单纯作为函数运行，`this`会指向顶层对象。但是，严格模式下，这时`this`会返回`undefined`。
   6. 不管是严格模式，还是普通模式，`new Function('return this')()`，总是会返回全局对象。但是，如果浏览器用了CSP（Content Security Policy，内容安全政策），那么`eval`、`new Function`这些方法都可能无法使用。

###变量解构赋值

1. 数组结构赋值-->`let [a, b, c] = [1, 2, 3];`如果等号的右边不是数组（或者严格地说，不是可遍历的结构，参见《Iterator》一章），那么将会报错。
   1. 解构赋值允许指定默认值。`let [foo = true] = [];`
2. ES6 内部使用严格相等运算符（`===`），判断一个位置是否有值
3. 对象的解构赋值-->`let { foo, bar } = { foo: "aaa", bar: "bbb" };` 或者`let { foo: foo, bar: bar } = { foo: "aaa", bar: "bbb" };`
4. 对象解构分清楚模式和变量;
5. `let { log, sin, cos } = Math;`上面代码将`Math`对象的对数、正弦、余弦三个方法，赋值到对应的变量上，使用起来就会方便很多。
6. ​









```javascript

//构造函数
function Point(x, y) {
  this.x = x;
  this.y = y;
}

Point.prototype.toString = function () {
  return '(' + this.x + ', ' + this.y + ')';
};

var p = new Point(1, 2);

//es6写法如下:

//定义类
class Point {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }

  toString() {
    return '(' + this.x + ', ' + this.y + ')';
  }
}
```

### 补充

NodeJS有三大核心： 

- **CallBack回调** 
- **Event事件** 
- **Stream流**
- ​