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
