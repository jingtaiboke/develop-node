以下占用了几个空间	

```
var a = 3
var obj = {} 答案: 3 1.var a  = 3, 2.var  obj 3.{}
```

1.内存生命周期

* 分配小内存空间，得到使用权
* 存储数据，可以反复进行操作
* 释放小内存空间

2.释放内存

* 局部变量:函数执行完自动释放
* 对象: 成为垃圾对象==>垃圾回收器回收