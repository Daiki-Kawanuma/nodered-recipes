# 言語を翻訳する

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/translate-language/image.png)

言語を翻訳するレシピ

```
[{"id":"7dd12c73.6d8674","type":"watson-translator","z":"4faf54ca.3a4afc","name":"","action":"translate","basemodel":"en-tr","domain":"general","srclang":"en","destlang":"ja","password":"","apikey":"J6oN3G9lo08JasZ2apofnemMzE2ug9nDqwHlr44QKW-x","custom":"","domainhidden":"general","srclanghidden":"en","destlanghidden":"ja","basemodelhidden":"en-tr","customhidden":"","filetype":"forcedglossary","trainid":"","lgparams2":true,"neural":false,"default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/language-translator/api","x":470,"y":160,"wires":[["5fcce064.0d431"]]},{"id":"b2668d43.d44fd","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":260,"y":160,"wires":[["7dd12c73.6d8674"]]},{"id":"7f994e20.36e3b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/trans","method":"get","upload":false,"swaggerDoc":"","x":80,"y":160,"wires":[["b2668d43.d44fd"]]},{"id":"5fcce064.0d431","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":660,"y":160,"wires":[]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/trans?text=goodbye
