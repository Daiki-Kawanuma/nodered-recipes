# 感情分析をする

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/tone-analyzer/image.png)

感情分析をするレシピ

```
[{"id":"15f5d896.1ab247","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/tone-analyzer","method":"get","upload":true,"swaggerDoc":"","x":130,"y":100,"wires":[["5c65968c.3c1608"]]},{"id":"5c65968c.3c1608","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":340,"y":100,"wires":[["97638f1b.8dab4"]]},{"id":"97638f1b.8dab4","type":"watson-tone-analyzer-v3","z":"4faf54ca.3a4afc","name":"","tones":"emotion","sentences":"true","contentType":"false","tone-method":"generalTone","interface-version":"2016-05-19","inputlang":"en","default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/tone-analyzer/api","x":220,"y":160,"wires":[["5297727a.61936c"]]},{"id":"d35fc97.1dade38","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":600,"y":160,"wires":[]},{"id":"5297727a.61936c","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"response","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":420,"y":160,"wires":[["d35fc97.1dade38"]]}]
```

要求例:  
http://nodered-recipes-sample.mybluemix.net/tone-analyzer?text=Hi%20Team,%20I%20know%20the%20times%20are%20difficult!%20Our%20sales%20have%20been%20disappointing%20for%20the%20past%20three%20quarters%20for%20our%20data%20analytics%20product%20suite.%20We%20have%20a%20competitive%20data%20analytics%20product%20suite%20in%20the%20industry.%20But%20we%20need%20to%20do%20our%20job%20selling%20it!

応答例:  
```
{
    "document_tone": {
        "tone_categories": [
            {
                "tones": [
                    {
                        "score": 0.069776,
                        "tone_id": "anger",
                        "tone_name": "Anger"
                    },
                    {
                        "score": 0.010281,
                        "tone_id": "disgust",
                        "tone_name": "Disgust"
                    },
                    {
                        "score": 0.238294,
                        "tone_id": "fear",
                        "tone_name": "Fear"
                    },
                    {
                        "score": 0.03581,
                        "tone_id": "joy",
                        "tone_name": "Joy"
                    },
                    {
                        "score": 0.448082,
                        "tone_id": "sadness",
                        "tone_name": "Sadness"
                    }
                ],
                "category_id": "emotion_tone",
                "category_name": "Emotion Tone"
            }
        ]
    },
    "sentences_tone": [
        {
            "sentence_id": 0,
            "text": "Hi Team, I know the times are difficult!",
            "input_from": 0,
            "input_to": 40,
            "tone_categories": [
                {
                    "tones": [
                        {
                            "score": 0.054119,
                            "tone_id": "anger",
                            "tone_name": "Anger"
                        },
                        {
                            "score": 0.050926,
                            "tone_id": "disgust",
                            "tone_name": "Disgust"
                        },
                        {
                            "score": 0.05164,
                            "tone_id": "fear",
                            "tone_name": "Fear"
                        },
                        {
                            "score": 0.057647,
                            "tone_id": "joy",
                            "tone_name": "Joy"
                        },
                        {
                            "score": 0.359699,
                            "tone_id": "sadness",
                            "tone_name": "Sadness"
                        }
                    ],
                    "category_id": "emotion_tone",
                    "category_name": "Emotion Tone"
                }
            ]
        },
        {
            "sentence_id": 1,
            "text": "Our sales have been disappointing for the past three quarters for our data analytics product suite.",
            "input_from": 41,
            "input_to": 140,
            "tone_categories": [
                {
                    "tones": [
                        {
                            "score": 0.085014,
                            "tone_id": "anger",
                            "tone_name": "Anger"
                        },
                        {
                            "score": 0.016675,
                            "tone_id": "disgust",
                            "tone_name": "Disgust"
                        },
                        {
                            "score": 0.133724,
                            "tone_id": "fear",
                            "tone_name": "Fear"
                        },
                        {
                            "score": 0.034614,
                            "tone_id": "joy",
                            "tone_name": "Joy"
                        },
                        {
                            "score": 0.658219,
                            "tone_id": "sadness",
                            "tone_name": "Sadness"
                        }
                    ],
                    "category_id": "emotion_tone",
                    "category_name": "Emotion Tone"
                }
            ]
        },
        {
            "sentence_id": 2,
            "text": "We have a competitive data analytics product suite in the industry.",
            "input_from": 141,
            "input_to": 208,
            "tone_categories": [
                {
                    "tones": [
                        {
                            "score": 0.046283,
                            "tone_id": "anger",
                            "tone_name": "Anger"
                        },
                        {
                            "score": 0.008302,
                            "tone_id": "disgust",
                            "tone_name": "Disgust"
                        },
                        {
                            "score": 0.038247,
                            "tone_id": "fear",
                            "tone_name": "Fear"
                        },
                        {
                            "score": 0.125108,
                            "tone_id": "joy",
                            "tone_name": "Joy"
                        },
                        {
                            "score": 0.126803,
                            "tone_id": "sadness",
                            "tone_name": "Sadness"
                        }
                    ],
                    "category_id": "emotion_tone",
                    "category_name": "Emotion Tone"
                }
            ]
        },
        {
            "sentence_id": 3,
            "text": "But we need to do our job selling it!",
            "input_from": 209,
            "input_to": 246,
            "tone_categories": [
                {
                    "tones": [
                        {
                            "score": 0.084884,
                            "tone_id": "anger",
                            "tone_name": "Anger"
                        },
                        {
                            "score": 0.076172,
                            "tone_id": "disgust",
                            "tone_name": "Disgust"
                        },
                        {
                            "score": 0.619702,
                            "tone_id": "fear",
                            "tone_name": "Fear"
                        },
                        {
                            "score": 0.032172,
                            "tone_id": "joy",
                            "tone_name": "Joy"
                        },
                        {
                            "score": 0.144564,
                            "tone_id": "sadness",
                            "tone_name": "Sadness"
                        }
                    ],
                    "category_id": "emotion_tone",
                    "category_name": "Emotion Tone"
                }
            ]
        }
    ]
}
```
