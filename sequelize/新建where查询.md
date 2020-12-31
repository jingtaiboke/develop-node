```
const invtDetailsWhere = {
    $or: [],
  };
  transitions.forEach((tr) => {
    invtDetailsWhere.$or.push({
      asn_no: tr.asn_no,
      prdt_item_no: tr.prdt_item_no,
    });
  });
  const invtDetails = yield CwmSasblGoodsDetailDao.findAll({
    raw: true,
    attributes: [
      'sgd_dec_price', 'sgd_currency', 'sgd_g_qty', 'asn_no', 'prdt_item_no',
    ],
    where: invtDetailsWhere,
  });
```

