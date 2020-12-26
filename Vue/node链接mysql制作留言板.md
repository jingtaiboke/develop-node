# 1.获取(POST)数据	

​				npm install -- save body-parser

![img](../Img/nodecrud.png)

   *	进行配置
          				*	app.use(bodyParser.urlencoded({ extended: false }))
               				*	app.use(bodyParser.json())