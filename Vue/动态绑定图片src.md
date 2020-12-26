1.在script中使用require引入图片地址并const 一个变量接收

2.在data中定义一个参数接收(1)中的变量

3.如果要加修饰，如下使用:class进行绑定

```html
<img :src="innerItem.img1" :class="{pic:isActive === 1}" />
```

