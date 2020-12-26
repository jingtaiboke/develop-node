# 使用Node操作MySQL数据库

安装:

```
cnpm install --save mysql
```

```
var mysql      = require('mysql');
// 创建数据库
var connection = mysql.createConnection({
  host     : 'localhost',
  user     : 'root',
  password : 'phoenixyu80yy',
  database : 'tarrow'
});
 
// 连接数据库
connection.connect();
 
// 执行数据操作
connection.query('SELECT * FROM `students`', function (error, results, fields) {
  if (error) throw error;
  console.log('The solution is: ', results);
});
 
// connection.query(`INSERT INTO students VALUES(NULL,"admin","123456")`, function (error, results, fields) {
//     if (error) throw error;
//     console.log('The solution is: ', results);
//   });
// 关闭链接
connection.end();
```

