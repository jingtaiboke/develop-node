<h1>Object.getOwnPropertyDescriptor（对象,属性）</h1>

Object.defineProperty(obj,prop,descriptor)定义新属性或修改原有的属性

obj: 必需。目标对象

prop:必需,需定义或修改的属性的名字

descriptor: 必需，目标属性所拥有的特性

​	说明: 以对象形式{}书写

value: 设置属性的值，默认为undefined

writeable:值是否可以重写，true | false 默认为false

enumerable: 目标是否可以被枚举.true | false 默认为false

configurable: 目标属性是否可以被删除是否可以再次修改特性 true | false 默认为false

```js
var obj = {
            name: 'tarrowtmo',
            price: 1999
        }
        Object.defineProperty(obj,'name', {
            value: '严宇'
        })
        console.log(obj)
```

```js
不允许修改 
	Object.defineProperty(obj,'price', {
            writable: false
        })
        obj.price = 909
        console.log(obj)
```

```js
不允许被遍历
		Object.defineProperty(obj,'car', {
            value: '严宇',
            enumerable: false
        })
        console.log(Object.keys(obj))
```

```
不允许被删除且不能重新修改其特性
Object.defineProperty(obj,'car', {
            value: '严宇'
        })
        delete obj.car
        console.log(obj)
```

