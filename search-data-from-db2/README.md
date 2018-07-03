# Db2のデータを検索

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/search-data-from-db2/image.png)

Db2のデータを検索するレシピ

```
[{"id":"a8567955.7b2218","type":"http in","z":"36d10e5c.529692","name":"request","url":"/search","method":"get","upload":false,"swaggerDoc":"","x":90,"y":60,"wires":[["5ee9acaa.e575c4"]]},{"id":"5ee9acaa.e575c4","type":"dashDB in","z":"36d10e5c.529692","dashDB":"92138d8e.f09af","service":"_ext_","query":"SELECT * FROM PERSON WHERE NAME = ?;","params":"msg.req.query.name","name":"DBを検索","x":260,"y":60,"wires":[["5eba10d5.5271a"]]},{"id":"5eba10d5.5271a","type":"http response","z":"36d10e5c.529692","name":"response","statusCode":"","headers":{},"x":420,"y":60,"wires":[]},{"id":"92138d8e.f09af","type":"dashDB","z":"","hostname":"dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net","db":"BLUDB","port":"50000","name":""}]
```

Db2 資格情報（例）
```
{
  "hostname": "dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net",
  "password": "4cw0c22nq7r0j-76",
  "https_url": "https://dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net",
  "port": 50000,
  "ssldsn": "DATABASE=BLUDB;HOSTNAME=dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net;PORT=50001;PROTOCOL=TCPIP;UID=pjk00128;PWD=4cw0c22nq7r0j-76;Security=SSL;",
  "host": "dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net",
  "jdbcurl": "jdbc:db2://dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net:50000/BLUDB",
  "uri": "db2://pjk00128:4cw0c22nq7r0j-76@dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net:50000/BLUDB",
  "db": "BLUDB",
  "dsn": "DATABASE=BLUDB;HOSTNAME=dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net;PORT=50000;PROTOCOL=TCPIP;UID=pjk00128;PWD=4cw0c22nq7r0j-76;",
  "username": "pjk00128",
  "ssljdbcurl": "jdbc:db2://dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net:50001/BLUDB:sslConnection=true;"
}
```