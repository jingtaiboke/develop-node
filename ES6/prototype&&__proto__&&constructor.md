<h1>原型对象</h1>

构造函数身上的原型对象,引用类型的数据挂在上面可节省栈空间

公共属性定义在构造函数当中

公共方法定义在原型对象上

<h1>对象原型</h1>

<strong>指向构造函数的原型对象，使用对象实例可以访问到原型对象的方法</strong>

```
function Star(uanme.age){
	this.uname = uname
	this.age = age
}
Star.prototype.sing = function(){
	console.log('唱歌')
}
var ldh = new Star('ldh',20)
console.log(ldh.__proto__ === Star.prototype)(true)
```

<h1>构造函数</h1>

对象原型( \__proto__)和构造函数的原型对象(prototype)里面都有一个属性 constructor属性,constructor我们称为构造函数,<strong>因为它指回构造函数本身</strong>

<strong>constructor主要用于记录该对象引用于哪个构造函数,它可以让原型对象重新指向原来的构造函数</strong>