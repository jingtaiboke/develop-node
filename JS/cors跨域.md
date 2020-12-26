cors[跨域资源共享]   后端解决方案
npm install cors

在js文件中设置
const express = require('express');
const cors = require('cors');  //使用cors插件解决跨域问题
const app = express();
app.use(cors());