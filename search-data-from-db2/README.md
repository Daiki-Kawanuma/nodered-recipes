# Db2のデータを検索

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/search-data-from-db2/image.png)

Db2のデータを検索するレシピ

```
[{"id":"a8567955.7b2218","type":"http in","z":"36d10e5c.529692","name":"request","url":"/search","method":"get","upload":false,"swaggerDoc":"","x":90,"y":60,"wires":[["5ee9acaa.e575c4"]]},{"id":"5ee9acaa.e575c4","type":"dashDB in","z":"36d10e5c.529692","dashDB":"92138d8e.f09af","service":"_ext_","query":"SELECT * FROM PERSON WHERE NAME = ?;","params":"msg.req.query.name","name":"DBを検索","x":260,"y":60,"wires":[["5eba10d5.5271a"]]},{"id":"5eba10d5.5271a","type":"http response","z":"36d10e5c.529692","name":"response","statusCode":"","headers":{},"x":420,"y":60,"wires":[]},{"id":"92138d8e.f09af","type":"dashDB","z":"","hostname":"dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net","db":"BLUDB","port":"50000","name":""}]
```