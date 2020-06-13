## javascript中的this

javascript中的this与java中的this有点不同。
ECMAScript规范中这样写：

* this 关键字执行为当前执行环境的 ThisBinding。

MDN上这样写：

* 在绝大多数情况下，函数的调用方式决定了this的值。

可以这样理解，在JavaScript中，this的指向是调用时决定的，而不是创建时决定的，这就会导致this的指向会让人迷惑，简单来说，this具有运行期绑定的特性。

## 一般情况下，谁调用，this就指向谁

执行上下文生命周期分为三阶段，创建、执行、回收上下文。

* 执行上下文的创建阶段，会分别生成变量对象，建立作用域链，确定this指向
* 执行上下文的执行阶段，会分别变量赋值，函数引用，执行其他代码

首先要明确一个非常重要的结论：this的指向是在函数被调用的时候确定的，也就是执行上下文创建时

``` js
  var a = 10;
  var obj = {
      a: 20
  }

  function fn() {
      console.log(this.a);
  }

  fn(); // 10
  fn.call(obj); // 20 call改变this指向到obj
```

### 全局this

有一个很好玩的情况：
```js
    var a = 10
    function prin() {
        var a = 30;
        console.log(this.a) 
    }
    prin() // 10 windows调用的函数，所以this指向windows a = 10
    console.log(a) // 10
```

```js
    var a = 10
    function prin() {
        a = 30;
        console.log(this.a) 
    }
    prin() // 30
    console.log(a) // 30
```