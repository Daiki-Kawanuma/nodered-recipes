# チャットボットを使う

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/use-chatbot/image.png)

チャットボットを使うレシピ

```
[{"id":"491c5046.51c11","type":"watson-conversation-v1","z":"4faf54ca.3a4afc","name":"","workspaceid":"10bdda4c-0414-4749-8233-a7af30074d1d","multiuser":false,"context":true,"empty-payload":false,"default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/assistant/api","timeout":"","optout-learning":false,"x":320,"y":260,"wires":[["996b9388.8f777"]]},{"id":"ffcb2afc.f7fea8","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/assistant","method":"get","upload":false,"swaggerDoc":"","x":120,"y":200,"wires":[["44299b02.01c434"]]},{"id":"44299b02.01c434","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":320,"y":200,"wires":[["491c5046.51c11"]]},{"id":"9f041c44.0593d","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":680,"y":260,"wires":[]},{"id":"996b9388.8f777","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.output.text[0]","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":500,"y":260,"wires":[["9f041c44.0593d"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/assistant?text=hello
