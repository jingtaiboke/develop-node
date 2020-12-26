```
通过navigateTo进行页面跳转
uni.navigateTo({
					url: '../detail-comments/detail-comments?id='+ this.formData._id
				})
onLoad(query) {
			console.log(query);
		},
通过onLoad里的query接收
```

