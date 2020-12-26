导航组件navigator

  块级元素，默认换行 可以直接加入宽度和高度

  url要跳转的页面路径 绝对路径 相对路径

  target 要跳转到当前的小程序还是其他的小程序的页面

  self 默认自己

  miniProgram 其他的小程序的页面



  open-type 跳转的方式

  navigate 默认值 保留当前页面 跳转到应用内的某个页面,但是不能跳转到tabbar页面

  redirect 关闭当前页面 跳转到应用内的某个页面,但是不能跳转到tabbar页面

  switchTab 跳转到 tabBar页面 并关闭其他所有非tabBar页面

  reLaunch 关闭所有页面并打开应用内的某个页面





url传参

```
url="/pages/goods_list/index?cid={{item2.cat_id}}"
```

如何获取

​	在跳转到的页面处的js文件里

```
Page({
  data: {

  },
  onLoad: function (options) {
    console.log(options);
  },
})
```

