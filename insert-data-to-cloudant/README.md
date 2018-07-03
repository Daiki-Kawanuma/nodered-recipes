# Cloudantにデータを挿入

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/insert-data-to-cloudant/image.png)

Cloudantにデータを挿入するレシピ

```
[{"id":"b0a8c852.1f8528","type":"cloudant out","z":"36d10e5c.529692","name":"DBに挿入","cloudant":"26bf61ce.481e1e","database":"person","service":"_ext_","payonly":true,"operation":"insert","x":540,"y":260,"wires":[]},{"id":"9328e905.7a0ab8","type":"http in","z":"36d10e5c.529692","name":"request","url":"/insert","method":"get","upload":false,"swaggerDoc":"","x":90,"y":200,"wires":[["390256d.c9f0faa"]]},{"id":"eef5cf00.fa75f","type":"http response","z":"36d10e5c.529692","name":"response","statusCode":"","headers":{},"x":540,"y":200,"wires":[]},{"id":"390256d.c9f0faa","type":"function","z":"36d10e5c.529692","name":"get query parameters","func":"msg.payload = {NAME: msg.req.query.name, AGE: msg.req.query.age};\nreturn msg;","outputs":1,"noerr":0,"x":300,"y":200,"wires":[["eef5cf00.fa75f","b0a8c852.1f8528"]]},{"id":"26bf61ce.481e1e","type":"cloudant","z":"","host":"843940a3-ff48-4dd8-825d-c9af03bee780-bluemix.cloudant.com","name":""}]
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