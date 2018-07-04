# 配列の要素を取得

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/get-array-value/image.png)

配列の要素を取得するレシピ

```
[{"id":"f4beb0c8.26ec3","type":"http in","z":"36d10e5c.529692","name":"","url":"/array","method":"post","upload":false,"swaggerDoc":"","x":100,"y":60,"wires":[["940214dc.ba63d8"]]},{"id":"940214dc.ba63d8","type":"function","z":"36d10e5c.529692","name":"配列の2番目を取得","func":"msg.payload = msg.payload[1];\nreturn msg;","outputs":1,"noerr":0,"x":310,"y":60,"wires":[["3f96054f.80691a"]]},{"id":"3f96054f.80691a","type":"http response","z":"36d10e5c.529692","name":"response","statusCode":"","headers":{},"x":520,"y":60,"wires":[]}]
```


要求例: POST/array [{"name": "foo", "age": 20}, {"name": "bar","age": 30}]

応答例: {"name": "bar","age": 30}
