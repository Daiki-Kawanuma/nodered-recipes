# クエリパラメータ取得（複数）

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/get-query-parameters/image.png)

複数のクエリパラメータを取得するレシピ
```
[{"id":"2f5f3eef.fa99d2","type":"http in","z":"7cc27111.df64e","name":"request","url":"/params","method":"get","upload":false,"swaggerDoc":"","x":100,"y":60,"wires":[["e619173e.076fd8"]]},{"id":"b3ce2161.b46cd","type":"http response","z":"7cc27111.df64e","name":"response","statusCode":"","headers":{},"x":570,"y":60,"wires":[]},{"id":"e619173e.076fd8","type":"function","z":"7cc27111.df64e","name":"get query parameters","func":"msg.payload.name = msg.req.query.name;\nmsg.payload.password = msg.req.query.password;\nreturn msg;","outputs":1,"noerr":0,"x":340,"y":60,"wires":[["b3ce2161.b46cd"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/params?name=admin&password=qwer
