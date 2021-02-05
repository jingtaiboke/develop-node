<h1>限制InputNumber输入框的内容</h1>

```
limitDecimals = (value) => {

  const reg = /^(\d+)\.(\d\d).*$/;

  return String(value).replace(reg, '$1.$2');

 }
 <InputNumber formatter={this.limitDecimals} parser={this.limitDecimals}/>
```

