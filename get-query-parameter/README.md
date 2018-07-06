# クエリパラメータ取得（単一）

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/get-query-parameter/image.png)

単一のクエリパラメータを取得するレシピ

```
[{"id":"8d2af8c.0027308","type":"http in","z":"158d324c.16b52e","name":"request","url":"/param","method":"get","upload":false,"swaggerDoc":"","x":70,"y":40,"wires":[["1852837f.1434bd"]]},{"id":"e124337f.c0fd","type":"http response","z":"158d324c.16b52e","name":"response","statusCode":"","headers":{},"x":540,"y":40,"wires":[]},{"id":"1852837f.1434bd","type":"change","z":"158d324c.16b52e","name":"set query parameter","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.value","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":290,"y":40,"wires":[["e124337f.c0fd"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/param?value=XXX
