#### EcmaScript

​	1.没有DOM和BOM

####  核心模块

​	在Node中为JS提供了服务器级别的API，都被包装到了一个具名的核心模块中

​	例如文件操作的`fs`核心模块,http服务构建的`http`模块,`path`路径操作

​	如要使用必须require引入

```js
var fs = require('fs')
var http = require('http')
```

​	

