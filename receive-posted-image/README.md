# アップロードされた画像を表示

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/receive-posted-image/image.png)

アップロードされた画像を表示するレシピ

```
[{"id":"c7c4ecb3.60d93","type":"http in","z":"7cc27111.df64e","name":"[POST] /image","url":"/image","method":"post","upload":true,"swaggerDoc":"","x":120,"y":60,"wires":[["4ebe5386.5eddac"]]},{"id":"d1727926.f6a0f8","type":"function","z":"7cc27111.df64e","name":"画像抽出","func":"if (msg.req.files[0].mimetype.includes('image')) {\n    msg.payload = msg.payload.toString('base64');\n} else {\n    msg.payload = msg.payload.toString();\n}\n\nreturn msg;","outputs":1,"noerr":0,"x":240,"y":140,"wires":[["2da40bb0.28e084"]]},{"id":"2da40bb0.28e084","type":"template","z":"7cc27111.df64e","name":"HTML","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"<html>\n<head><title>Display image</title></head>\n<body>\n<h1>Display image</h1>\n<img src=\"data:image/jpeg;base64,{{{payload}}}\"/>\n</body>\n</html>","output":"str","x":410,"y":140,"wires":[["bf57cec7.8170c"]]},{"id":"bf57cec7.8170c","type":"http response","z":"7cc27111.df64e","name":"response","statusCode":"","headers":{},"x":580,"y":140,"wires":[]},{"id":"4ebe5386.5eddac","type":"change","z":"7cc27111.df64e","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"req.files[0].buffer","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":320,"y":60,"wires":[["d1727926.f6a0f8"]]}]
```
