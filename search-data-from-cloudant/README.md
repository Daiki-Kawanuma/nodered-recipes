# Cloudantのデータを検索

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/search-data-from-cloudant/image.png)

Cloudantのデータを検索するレシピ

```
[{"id":"a8567955.7b2218","type":"http in","z":"36d10e5c.529692","name":"request","url":"/search","method":"get","upload":false,"swaggerDoc":"","x":90,"y":60,"wires":[["c428d7b6.a03ec8"]]},{"id":"5eba10d5.5271a","type":"http response","z":"36d10e5c.529692","name":"response","statusCode":"","headers":{},"x":560,"y":60,"wires":[]},{"id":"a5fdb673.f8e3f8","type":"cloudant in","z":"36d10e5c.529692","name":"","cloudant":"26bf61ce.481e1e","database":"person","service":"_ext_","search":"_idx_","design":"Index","index":"age-index","x":390,"y":60,"wires":[["5eba10d5.5271a"]]},{"id":"c428d7b6.a03ec8","type":"function","z":"36d10e5c.529692","name":"","func":"msg.payload = {\n  \"query\": \"age: [\" + msg.req.query.greater + \" TO \" + msg.payload.less + \"]\",\n  \"limit\": 200\n}\nreturn msg;","outputs":1,"noerr":0,"x":240,"y":60,"wires":[["a5fdb673.f8e3f8"]]},{"id":"26bf61ce.481e1e","type":"cloudant","z":"","host":"843940a3-ff48-4dd8-825d-c9af03bee780-bluemix.cloudant.com","name":""}]
```

Cloudant 資格情報（例）
```
{
  "username": "843940a3-ff48-4dd8-825d-c9af03bee780-bluemix",
  "password": "7152100f4b2e76fd853fcbb3f14046f6ad6d142c51451054a5fc4ae5dafb4b5c",
  "host": "843940a3-ff48-4dd8-825d-c9af03bee780-bluemix.cloudant.com",
  "port": 443,
  "url": "https://843940a3-ff48-4dd8-825d-c9af03bee780-bluemix:7152100f4b2e76fd853fcbb3f14046f6ad6d142c51451054a5fc4ae5dafb4b5c@843940a3-ff48-4dd8-825d-c9af03bee780-bluemix.cloudant.com"
}
```