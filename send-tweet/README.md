# ツイートする

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/send-tweet/image.png)

ツイートするレシピ

```
[{"id":"98f6f23b.f13ac","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":460,"y":160,"wires":[]},{"id":"7f994e20.36e3b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/tweet","method":"get","upload":false,"swaggerDoc":"","x":100,"y":160,"wires":[["6bc503d.8654cfc"]]},{"id":"c356b89f.571168","type":"twitter out","z":"4faf54ca.3a4afc","twitter":"","name":"Tweet","x":450,"y":220,"wires":[]},{"id":"6bc503d.8654cfc","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":280,"y":160,"wires":[["98f6f23b.f13ac","c356b89f.571168"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/tweet?text=hello

**Twitter を使う準備**
https://apps.twitter.com/
