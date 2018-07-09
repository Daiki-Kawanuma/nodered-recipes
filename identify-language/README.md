# 言語を特定する

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/identify-language/image.png)

言語を特定するレシピ

```
[{"id":"b2668d43.d44fd","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":280,"y":160,"wires":[["17373e67.41f1b2"]]},{"id":"7f994e20.36e3b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/identify","method":"get","upload":false,"swaggerDoc":"","x":90,"y":160,"wires":[["b2668d43.d44fd"]]},{"id":"5fcce064.0d431","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":660,"y":220,"wires":[]},{"id":"17373e67.41f1b2","type":"watson-language-translator-identify","z":"4faf54ca.3a4afc","name":"","default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/language-translator/api","x":490,"y":160,"wires":[["90a64eec.c0702"]]},{"id":"90a64eec.c0702","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"lang","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":480,"y":220,"wires":[["5fcce064.0d431"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/identify?text=hello
