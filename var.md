# var和let以及const

⼀个变量要在 JavaScript 中使用，需要 **声明** 和 初始化。

var是最早的JavaScript关键词之一,同时也存在一些**古早的奇妙特性**

```js
console.log(a);

var a = 5;
```

你会发现控制台会打印出**undefined**;

var无论声明在哪里，变量提升会把都会提升到该作⽤域的**最顶部**，你在任何地⽅都会访问的到

上面的代码的作用等同于下面

```js
var a = undefined;

console.log(a);

var a = 5;
```



```
function sayHi() {
  phrase = "Hello";

  alert(phrase);//Hello

  var phrase;
}
sayHi();

{
	var test = '独立在一个块的变量'
}
console.log(test);//独立在一个块的变量
```



这样子容易诱发各种问题,尤其你不知道var变量可能在那个地方就改变了

所以,后续就有了Let和Const

1. 具有**块级**作用域

2. 当遇到变量提升的情况，会有暂时性锁区。

3. 全局声明，**不可重复声明**，会报错

而其中 **Const** 和 **Let** 的最⼤区别是 **Const** 具有不可重新赋值的特性 



### ! ! ! Const 为引用类型(对象等)时,是可以重新赋值的

因为引用类型在栈空间保存的其实是引用地址，真正的值保持在堆空间



记一个比较特殊的var例子

```js
for(var i = 0 ; i < 5 ; ++i){
        setTimeout(()=>console.log(i),0)
    }  // 5 5 5 5 5
```

setTimeout的特性是执行完全部代码后,再执行里面的函数,所以答案是5个5