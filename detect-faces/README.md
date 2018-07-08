# 顔認識を行う

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/detect-faces/image.png)

顔認識を行うレシピ

```
[{"id":"e79ed7c8.b142d8","type":"visual-recognition-v3","z":"4faf54ca.3a4afc","name":"","apikey":"__PWRD__","vr-service-endpoint":"https://gateway.watsonplatform.net/visual-recognition/api","image-feature":"detectFaces","lang":"en","x":270,"y":120,"wires":[["c84c647c.25cca8"]]},{"id":"908bd88.f24d528","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/vr/detect_faces","method":"get","upload":true,"swaggerDoc":"","x":140,"y":60,"wires":[["bf86a2ea.5395b"]]},{"id":"d7671118.b9868","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":660,"y":120,"wires":[]},{"id":"bf86a2ea.5395b","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.imageurl","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":380,"y":60,"wires":[["e79ed7c8.b142d8"]]},{"id":"c84c647c.25cca8","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"result.images","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":480,"y":120,"wires":[["d7671118.b9868"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/vr/detect_faces?imageurl=https://upload.wikimedia.org/wikipedia/en/7/7d/Lenna_%28test_image%29.png
