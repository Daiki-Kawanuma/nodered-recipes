# テキストを音声に変換する

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/text-to-speech/image.png)

テキストを音声に変換するレシピ

```
[{"id":"b2668d43.d44fd","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":320,"y":160,"wires":[["c679c31.e74624"]]},{"id":"7f994e20.36e3b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/text2speech","method":"get","upload":false,"swaggerDoc":"","x":110,"y":160,"wires":[["b2668d43.d44fd"]]},{"id":"5fcce064.0d431","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":660,"y":220,"wires":[]},{"id":"90a64eec.c0702","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"speech","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":320,"y":220,"wires":[["9c2a018a.8485b"]]},{"id":"c679c31.e74624","type":"watson-text-to-speech","z":"4faf54ca.3a4afc","name":"","lang":"ja-JP","langhidden":"ja-JP","langcustom":"NoCustomisationSetting","langcustomhidden":"","voice":"ja-JP_EmiVoice","voicehidden":"","format":"audio/wav","password":"N2PRoJbcaHg6","apikey":"","payload-response":false,"default-endpoint":true,"service-endpoint":"https://stream.watsonplatform.net/text-to-speech/api","x":520,"y":160,"wires":[["90a64eec.c0702"]]},{"id":"9c2a018a.8485b","type":"function","z":"4faf54ca.3a4afc","name":"Header","func":"msg.headers = {\"Content-Type\":\"audio/wav\"};\nreturn msg;","outputs":1,"noerr":0,"x":500,"y":220,"wires":[["5fcce064.0d431"]]}]
```

要求例（要URLエンコード）: https://nodered-recipes-sample.mybluemix.net/text2speech?text=おはよう

応答例: 

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/text-to-speech/image2.png)
