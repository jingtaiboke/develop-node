使用find查询并返回满足条件的元素,可通过if() else {}实现filter来返回过滤后剩余数组元素的效果

实例代码:

```js
for(let i = 0;i < rows.length;i++) {
        const row = rows[i];
        const findField = findFields.find(fd => fd.ciqcode === row.ciqcode && fd.hscode === row.hscode);
        if (findField) {
          dbs.push(CmsParamHsCiqDao.update({ ciqname: row.ciqname }, {
            where: { id: findField.id },
          }))
        } else {
          unFoundFields.push(row);
        }
      }
```

