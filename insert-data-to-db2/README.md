# Db2にデータを挿入

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/insert-data-to-db2/image.png)

Db2にデータを挿入するレシピ

```
[{"id":"a8567955.7b2218","type":"http in","z":"36d10e5c.529692","name":"request","url":"/insert","method":"get","upload":false,"swaggerDoc":"","x":90,"y":220,"wires":[["fe6cce29.3afb"]]},{"id":"ba7f2a4f.31a1c8","type":"http response","z":"36d10e5c.529692","name":"response","statusCode":"","headers":{},"x":600,"y":220,"wires":[]},{"id":"fe6cce29.3afb","type":"function","z":"36d10e5c.529692","name":"get query parameters","func":"msg.payload = {NAME: msg.req.query.name, AGE: Number(msg.req.query.age)};\nreturn msg;","outputs":1,"noerr":0,"x":340,"y":220,"wires":[["ba7f2a4f.31a1c8","c596daf8.0f9fb8"]]},{"id":"c596daf8.0f9fb8","type":"dashDB out","z":"36d10e5c.529692","dashDB":"92138d8e.f09af","service":"_ext_","table":"PERSON","name":"insert data","x":600,"y":280,"wires":[]},{"id":"92138d8e.f09af","type":"dashDB","z":"","hostname":"dashdb-txn-sbox-yp-dal09-03.services.dal.bluemix.net","db":"BLUDB","port":"50000","name":""}]
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
