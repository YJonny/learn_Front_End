由于作用域的关系，函数之间不能相互读取变量，父级作用域不能读取子级作用域的变量。这是闭包出现了。

## 闭包

闭包就是能够读取其他函数内部变量的函数。内部的函数被保存到外部的时候就会产生闭包。
在javascript语言中，只有函数内部的子函数才能读取局部变量，因此闭包也可理解成“定义在函数内部的函数”，本质上闭包就是一个桥梁，将函数内外部打通。

## 闭包用处

1. 外部函数读取内部函数变量
2. 让变量始终存在于内存中

``` js
function add() {
    var count = 0;

    function demo() {
        count++;
        console.log(count)
    }
    return demo;
}
var counter = add();
counter() //1
counter() //2
counter() //3 可以在外部读取，而且都去后变量没有被删除

// 定义普通函数 add
// 在 add 中定义普通函数 demo
// 在 add 中返回 demo
// 执行 add，并把 add 的返回结果赋值给变量 counter
// 执行 counter 

// 函数add内部的一个函数demo被函数add外部的一个变量counter引用，这就形成了一个闭包
```

闭包面试题： https://juejin.im/post/58f1fa6a44d904006cf25d22#heading-0
