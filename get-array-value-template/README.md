# 配列の要素を取得（template編）

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/get-array-value-template/image.png)

配列の要素を取得するレシピ

```
[{"id":"15f5d896.1ab247","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/array","method":"post","upload":false,"swaggerDoc":"","x":110,"y":100,"wires":[["319486e7.1a49ca"]]},{"id":"d35fc97.1dade38","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":420,"y":100,"wires":[]},{"id":"319486e7.1a49ca","type":"template","z":"4faf54ca.3a4afc","name":"HTML","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"<html>\n<body>\n<p>{{payload.category_name}}</p>\n<p>{{payload.tones.0.tone_name}}</p>\n<p>{{payload.tones.0.score}}</p>\n<p>{{payload.tones.1.tone_name}}</p>\n<p>{{payload.tones.1.score}}</p>\n<p>{{payload.tones.2.tone_name}}</p>\n<p>{{payload.tones.2.score}}</p>\n</body>\n</html>","output":"str","x":270,"y":100,"wires":[["d35fc97.1dade38"]]}]
```


要求例:  
curl -H "Content-type: applicatio -X POST -d "{\"tones\":[{\"score\":0.069776,\"tone_id\":\"anger\",\"tone_name\":\"Anger\"},{\"score\":0.010281,\"tone_id\":\"disgust\",\"tone_name\":\"Disgust\"},{\"score\":0.238294,\"tone_id\":\"fear\",\"tone_name\":\"Fear\"}],\"category_id\":\"emotion_tone\",\"category_name\":\"EmotionTone\"}" --url http://nodered-recipes-sample.mybluemix.net/array

応答例:  
```
<html>
<body>
<p>EmotionTone</p>
<p>Anger</p>
<p>0.069776</p>
<p>Disgust</p>
<p>0.010281</p>
<p>Fear</p>
<p>0.238294</p>
</body>
</html>
```