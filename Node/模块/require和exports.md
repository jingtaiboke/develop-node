作用:

1加载文件模块并执行里面的代码

2.拿到被加载文件模块导出的接口对象

每个文件模块中都提供了一个对象:exports

exports默认为一个空对象

如果一个 模块需要直接导出某个成员，而非挂载的方式

这是需要使用下面这种方式

```
function add(x,y)  {

​	return x+y
}
module.exports = {
	add(x,y) 
​		return x+y
	},
	str: 'hello'
}
```

exports = module.exports

最后return 的是 module.exports所以，给exports赋值不管用



导出多个成员

exports.xx= xx

module.exports = {

​	

}

导出单个成员

module.exports