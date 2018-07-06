# HTML表示

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/show-html/image.png)

HTML を表示するレシピ

```
[{"id":"ee87b430.6cbf48","type":"http in","z":"7cc27111.df64e","name":"request","url":"/html","method":"get","upload":false,"swaggerDoc":"","x":90,"y":40,"wires":[["7c045c18.045524"]]},{"id":"6f9b0848.cdeb88","type":"http response","z":"7cc27111.df64e","name":"response","statusCode":"","headers":{},"x":560,"y":40,"wires":[]},{"id":"7c045c18.045524","type":"template","z":"7cc27111.df64e","name":"HTML","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"<h1>Hello, Node-RED</h1>","output":"str","x":320,"y":40,"wires":[["6f9b0848.cdeb88"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/html
