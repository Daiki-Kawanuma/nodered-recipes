# テキストを分析する

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/natural-language-understanding/image.png)

テキストを分析するレシピ

```
[{"id":"b2668d43.d44fd","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":280,"y":160,"wires":[["9c726ebc.add89"]]},{"id":"7f994e20.36e3b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/nlu","method":"get","upload":false,"swaggerDoc":"","x":100,"y":160,"wires":[["b2668d43.d44fd"]]},{"id":"5fcce064.0d431","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":660,"y":220,"wires":[]},{"id":"90a64eec.c0702","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"features","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":480,"y":220,"wires":[["5fcce064.0d431"]]},{"id":"9c726ebc.add89","type":"natural-language-understanding","z":"4faf54ca.3a4afc","name":"","categories":true,"concepts":true,"maxconcepts":"10","doc-emotion":false,"doc-emotion-target":"","doc-sentiment":false,"doc-sentiment-target":"","entity":false,"entity-emotion":false,"entity-sentiment":false,"maxentities":"50","keyword":false,"keyword-emotion":false,"keyword-sentiment":false,"maxkeywords":"50","metadata":false,"relation":false,"semantic":false,"semantic-entities":false,"semantic-keywords":false,"maxsemantics":"50","default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/natural-language-understanding/api","x":540,"y":160,"wires":[["90a64eec.c0702"]]}]
```

要求例（要URLエンコード）: https://nodered-recipes-sample.mybluemix.net/nlu?text=記録的な豪雨に伴う土砂災害の被害が出た被災地では９日も懸命の救助活動が続いている。「なんとか無事でいてほしい」。知人や親族らは安否不明者の無事を祈るが、大量の土砂やがれきで重機を入れることが困難な場所も多く、警察や消防、自衛隊などの捜索活動は思うように進まず、難航している。
応答例: 
```
{
    "usage": {
        "text_units": 1,
        "text_characters": 137,
        "features": 2
    },
    "language": "ja",
    "concepts": [
        {
            "text": "集中豪雨",
            "relevance": 0.92629,
            "dbpedia_resource": "http://ja.dbpedia.org/resource/集中豪雨"
        },
        {
            "text": "災害",
            "relevance": 0.892189,
            "dbpedia_resource": "http://ja.dbpedia.org/resource/災害"
        },
        {
            "text": "捜索救難",
            "relevance": 0.885256,
            "dbpedia_resource": "http://ja.dbpedia.org/resource/捜索救難"
        }
    ],
    "categories": [
        {
            "score": 0.276832,
            "label": "/science/weather/meteorological disaster/hurricane"
        },
        {
            "score": 0.182437,
            "label": "/science/weather/meteorological disaster/flood"
        },
        {
            "score": 0.136096,
            "label": "/business and industrial/agriculture and forestry/crops and seed"
        }
    ]
}
```
