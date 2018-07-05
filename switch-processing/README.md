# 分岐処理を行う

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/switch-processing/image.png)

分岐処理を行うレシピ

```
[{"id":"eae209ed.d33be8","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/switch","method":"get","upload":false,"swaggerDoc":"","x":110,"y":140,"wires":[["82d7693f.f3c4b8"]]},{"id":"34b3a10.1e5a66","type":"switch","z":"4faf54ca.3a4afc","name":"","property":"payload","propertyType":"msg","rules":[{"t":"gte","v":"10","vt":"num"},{"t":"lt","v":"10","vt":"num"}],"checkall":"true","repair":false,"outputs":2,"x":350,"y":220,"wires":[["8a9aa319.6ad81"],["da14df0a.a2866"]]},{"id":"8a9aa319.6ad81","type":"template","z":"4faf54ca.3a4afc","name":"HTML","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"10以上です: {{payload}}","output":"str","x":510,"y":180,"wires":[["7e349b4.461e664"]]},{"id":"da14df0a.a2866","type":"template","z":"4faf54ca.3a4afc","name":"HTML","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"10以下です: {{payload}}","output":"str","x":510,"y":260,"wires":[["7e349b4.461e664"]]},{"id":"7e349b4.461e664","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":660,"y":220,"wires":[]},{"id":"82d7693f.f3c4b8","type":"change","z":"4faf54ca.3a4afc","name":"set query parameter","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.value","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":320,"y":140,"wires":[["34b3a10.1e5a66"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/switch?value=20
