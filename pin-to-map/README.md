# マップにピンを表示

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/pin-to-map/image.png)

マップにピンを表示するレシピ

```
[{"id":"ecde9b2d.4245b8","type":"worldmap","z":"4faf54ca.3a4afc","name":"","lat":"35.7090","lon":"139.7320","zoom":"","cluster":"","maxage":"","x":670,"y":100,"wires":[]},{"id":"23c36.a44763ca6","type":"template","z":"4faf54ca.3a4afc","name":"ピンを配置","field":"payload","fieldType":"msg","format":"handlebars","syntax":"mustache","template":"{\n    \"lat\": \"{{payload.lat}}\", \n    \"lon\": \"{{payload.lon}}\",\n    \"name\": \"{{payload.name}}\", \n    \"icon\": \"globe\",\n    \"iconColor\": \"orange\"\n}","output":"json","x":470,"y":60,"wires":[["ecde9b2d.4245b8"]]},{"id":"4378820c.5e58fc","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/map","method":"get","upload":false,"swaggerDoc":"","x":100,"y":140,"wires":[["5ce24aec.d27124"]]},{"id":"5ce24aec.d27124","type":"function","z":"4faf54ca.3a4afc","name":"パラメータ","func":"msg.payload.lat = msg.req.query.lat;\nmsg.payload.lon = msg.req.query.lon;\nmsg.payload.name = msg.req.query.name;\nreturn msg;","outputs":1,"noerr":0,"x":270,"y":140,"wires":[["23c36.a44763ca6","d9a7a1ec.250c8","8772fc81.9bacc"]]},{"id":"d9a7a1ec.250c8","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":460,"y":220,"wires":[]},{"id":"8772fc81.9bacc","type":"template","z":"4faf54ca.3a4afc","name":"移動とズーム","field":"payload","fieldType":"msg","format":"handlebars","syntax":"mustache","template":"{\n    \"command\": {\n        \"layer\": \"Esri Terrain\",\n        \"lat\": \"{{payload.lat}}\", \n        \"lon\": \"{{payload.lon}}\",\n        \"zoom\": \"10\"\n\n    }\n}","output":"json","x":480,"y":140,"wires":[["ecde9b2d.4245b8"]]}]
```


