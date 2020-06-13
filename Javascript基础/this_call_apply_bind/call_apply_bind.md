call、apply和bind都可以改变this的指向

## 例子
```js
    var person = {
        name: "axuebin",
        age: 25
    };
    function say(job){
        console.log(this.name+":"+this.age+" "+job);
    }
    say('FE') // :undefined FE
    say.call(person,"FE"); // axuebin:25 FE
    say.apply(person,["FE"]); // axuebin:25 FE
    var sayPerson = say.bind(person,"FE");
    sayPerson(); // axuebin:25 FE
```
如上面例子三种方法都可以改变函数被调用时this的指向
1. call和apply可直接使用，属于函数的方法，而bind是返回一个绑定函数可稍后执行
2. 三者的第一个参数都是this的指向对象
3. call给定参数需要全部列出， apply的参数以数组形式存在

