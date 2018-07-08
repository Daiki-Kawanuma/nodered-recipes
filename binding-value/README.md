# HTMLに値をバインディングする

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/binding-value/image.png)

HTMLに値をバインディングするレシピ

```
[{"id":"8abcc033.90f0e","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/html","method":"get","upload":true,"swaggerDoc":"","x":100,"y":60,"wires":[["d7746131.19c05"]]},{"id":"d7746131.19c05","type":"function","z":"4faf54ca.3a4afc","name":"パラメーター","func":"msg.payload.name = msg.req.query.name;\nmsg.payload.age = msg.req.query.age;\nmsg.payload.src = msg.req.query.src;\nreturn msg;","outputs":1,"noerr":0,"x":280,"y":60,"wires":[["2425d526.ffdbda"]]},{"id":"2425d526.ffdbda","type":"template","z":"4faf54ca.3a4afc","name":"HTML","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"<html>\n<body>\n    <p>{{payload.name}}</p>\n    <p>{{payload.age}}</p>\n    <img src=\"{{payload.src}}\"/>\n</body>\n</html>","output":"str","x":350,"y":120,"wires":[["386b7d9c.d3b832"]]},{"id":"386b7d9c.d3b832","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":500,"y":120,"wires":[]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/html?name=hoge&age=20&src=https://image_path
