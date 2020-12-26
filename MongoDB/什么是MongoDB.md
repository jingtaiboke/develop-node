# MongoDB

**关系型数据库和非关系型数据库**

表就是关系

或者说表与表之间的关系

​	所有的关系型数据库都需要通过 sql 语言来操作

​	所有的关系型数据库在操作之前都需要设计表结构

​	而且数据表还支持约束

非关系型数据库非常灵活

有的非关系型数据库就是 Key --- value 键值对

在MongoDB是长的最像 关系型数据库的非关系型数据库

​	数据库 ---> 数据库

​	数据表 -->集合[数组]

​	表记录 --> (文档对象)

MongoDB不需要设计表结构



# 启动和关闭数据库

启动: 

```
# mongodb默认使用执行mongod 命令所处盘符跟目录下的 /data/db作为自己的数据存储目录
#所以在第一次执行该命令之前先手动创建一个/data/db
mongod
```

如果想要修改默认的数据存储目录，可以:

```
mongod --dbpath=数据存储目录路径
```

停止:

```
ctrl + c
```

连接

```
默认连接本机的MongoDB服务
mongo
```

退出

```
exit
```

# 基本命令

`show dbs`

​	查看显示所有数据库

`db`

​	查看当前操作的数据库

`use` 数据库名称

​	切换到指定的数据库(如果没有会新建)

具体使用

​	![MongoDB](什么是MongoDB.assets/MongoDB.png)

```js
创建数据表
const mongoose = require('mongoose');

// 连接 MongoDB数据库
mongoose.connect('mongodb://localhost:27017/test', { useNewUrlParser: true, useUnifiedTopology: true });

// 创建一个模型
// 就是在设计数据库
// MongDB是动态的非常灵活,只需要在代码中设计数据库就可以了
const Cat = mongoose.model('Cat', { name: String });

// // 实例化一个cat
// const kitty = new Cat({ name: 'Zildjian' });

// // 持久化保存Kitty实例
// kitty.save().then(() => console.log('meow'));
for(var i = 0;i < 100; i++) {
    const kitty = new Cat({ name: 'tarrowtmo' + i })
    kitty.save().then(() => console.log('meow'))
}
```



# 使用第三方mongoose来操作MongoDB数据库

​	第三方包: MongoDB基于官方的mongodb包再一次做了封装

​	网址: www.mongoosejs.com

## 	基本概念

​		可以有多个数据库

​		一个数据库中可以有多个集合(表)

​		一个集合当中可以有多个文档(表记录)

```
	{
		qq: {
			users: [
				{ 
					name: '张三' ,
					age: 15
				},
				{ 
					name: '李四' ,
					age: 18
				},
				{ 
					name: '张三' ,
					age: 15
				},
				{ 
					name: '张三' ,
					age: 15
				}
				...
			],
			product: [
			
			],
			...
		},
		taobao: {
		
		},
		baidu: {
		
		}
	}
```

## 指南

#### 设计Schema发布model

```js
const mongoose = require('mongoose')
var Schema = mongoose.Schema
/*
    1.连接数据库
    指定连接的数据库不需要存在，当插入第一条数据之后就会被自动创建出来
*/
mongoose.connect('mongodb://localhost:27017/itcast', {useNewUrlParser: true})

// 2.设计集合结构(表结构)
// 字段名称就是表结构中的名称
// 值
var userSchema = new Schema({
    username: {
        type: String,
        required: true
    },
    password: {
        type:String,
        required: true
    },
    email: {
        type: String
    }
})
// 3.将文档结构发布为模型
// mongoose.model方法就是用来将一个架构发布为model
// 第一个参数传入一个大写名词单数字符串表示你的数据库名称
//  mongoose会自动将大写名词的字符串生成 小写复数 的集合名称
// 例如 User 会变成 users 集合名称
// 第二个参数: 架构 Schema
// 返回值:模型构造函数
var User = mongoose.model('User', userSchema);
```

#### 增加数据

```JS
var admin = new User({
        username: 'admin',
        password: '123456',
        email: 'admin@admin.com'
    })
    admin.save(function(err,ret) {
        if(err) {
            console.log('保存失败')
        } else{
            console.log('保存成功')
            console.log(ret)
        }
    })
```

#### 查询数据

```
按条件查询findOne()
全部查询 find()
User.findOne({
    username: '张三'
},function(err,ret){
        if(err) {
            console.log('保存失败')
        } else{
            console.log('保存成功')
            console.log(ret)
        }
    })
```

#### 删除数据

```js
删除一个 :
User.deleteOne({ username: '张三' }, function (err) {
    if (err) {
        console.log('保存失败')
    }
    else {
        console.log('删除成功')
    }
});

删除多个 :
	Character.deleteMany({ name: /Stark/, age: { $gte: 18 } }, function (err) {});

```

#### 更新数据

```
User.findByIdAndUpdate('5ebf47b03851f72704292978', {
    password: '123'
}, function (err, ret) {
    if (err) {
        console.log('更新失败')
    } else {
        console.log('更新成功')
        console.log(ret)
    }
})
```

具体API请查询

https://mongoosejs.com/docs/api/model.html#model_Model.findOneAndDelete