<<<<<<< HEAD
**<<2017年下半年软件评测师考试上午真题（专业解析+参考答案）>>**

------

![](D:\User\Desktop\me\pics\1.png)

<details>
<summary>展开查看答案和解析</summary>
<pre><code>
答案：B
解析：F1的值为38，不满足if条件，取表达式中最后一项，所以为输入错误。
</code></pre>
</details>

=======
## -

# JS 类型转换的应用

实现一个函数，运算结果可以满足如下预期结果：
```
add(1)(2) // 3
add(1, 2, 3)(10) // 16
add(1)(2)(3)(4)(5) // 15
```
---
参考答案
```

function add () {
var args = Array.prototype.slice.call(arguments);

var fn = function () {
    var arg_fn = Array.prototype.slice.call(arguments);
    return add.apply(null, args.concat(arg_fn));
}

fn.valueOf = function () {
    return args.reduce(function(a, b) {
        return a + b;
    })
}

return fn;
}
```
>>>>>>> 92bd739362d276014a3dfdb257ac62a22ff7e545
