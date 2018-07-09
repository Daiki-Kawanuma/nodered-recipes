# 性格分析する

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/personality-insights/image.png)

性格分析するレシピ

```
[{"id":"b2668d43.d44fd","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"payload.text","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":280,"y":160,"wires":[["e2d0afa.746855"]]},{"id":"7f994e20.36e3b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/insights","method":"get","upload":false,"swaggerDoc":"","x":110,"y":160,"wires":[["b2668d43.d44fd"]]},{"id":"5fcce064.0d431","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":660,"y":220,"wires":[]},{"id":"90a64eec.c0702","type":"change","z":"4faf54ca.3a4afc","name":"","rules":[{"t":"set","p":"payload","pt":"msg","to":"insights","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":480,"y":220,"wires":[["5fcce064.0d431"]]},{"id":"e2d0afa.746855","type":"watson-personality-insights-v3","z":"4faf54ca.3a4afc","name":"","inputlang":"en","outputlang":"en","rawscores":false,"consumption":false,"default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/personality-insights/api","x":490,"y":160,"wires":[["90a64eec.c0702"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/insights?text=wine%20arrow%20branch%20taxi%20grape%20snake%20statue%20brush%20palace%20London%20zoo%20entrance%20gym%20tower%20Europe%20host%20dad%20elephant%20soup%20tie%20fox%20jeans%20jam%20suit%20ticket%20Canada%20fence%20England%20Asia%20hall%20forest%20mom%20engineer%20policeman%20toy%20umbrella%20frog%20bottle%20ink%20sofa%20bomb%20China%20desert%20Australia%20beach%20theater%20tent%20restaurant%20stranger%20driver%20enemy%20husband%20scientis%20bathroom%20runner%20artist%20visitor%20cousin%20sunset%20trade%20match%20death%20habit%20joy%20blood%20luck%20fishing%20presiden%20merchant%20barber%20army%20painter%20reporter%20God%20century%20goal%20training%20disease%20tour%20exam%20flight%20film%20mind%20pain%20crowdguide%20queen%20pal%20captain%20neighbor%20prince%20midnight%20play%20tear%20concert%20action%20festival%20pop%20thought%20promise%20great

応答例: 
```
{
    "word_count": 100,
    "word_count_message": "There were 100 words in the input. We need a minimum of 600, preferably 1,200 or more, to compute statistically significant estimates",
    "processed_language": "en",
    "personality": [
        {
            "trait_id": "big5_openness",
            "name": "Openness",
            "category": "personality",
            "percentile": 0.48485610373656135,
            "children": [
                {
                    "trait_id": "facet_adventurousness",
                    "name": "Adventurousness",
                    "category": "personality",
                    "percentile": 0.8787035862621034
                },
                {
                    "trait_id": "facet_artistic_interests",
                    "name": "Artistic interests",
                    "category": "personality",
                    "percentile": 0.6644880155827819
                },
                {
                    "trait_id": "facet_emotionality",
                    "name": "Emotionality",
                    "category": "personality",
                    "percentile": 0.4728588103146679
                },
                {
                    "trait_id": "facet_imagination",
                    "name": "Imagination",
                    "category": "personality",
                    "percentile": 0.6063354922100247
                },
                {
                    "trait_id": "facet_intellect",
                    "name": "Intellect",
                    "category": "personality",
                    "percentile": 0.8372042835979177
                },
                {
                    "trait_id": "facet_liberalism",
                    "name": "Authority-challenging",
                    "category": "personality",
                    "percentile": 0.9279390962782011
                }
            ]
        },
        {
            "trait_id": "big5_conscientiousness",
            "name": "Conscientiousness",
            "category": "personality",
            "percentile": 0.30119210535971375,
            "children": [
                {
                    "trait_id": "facet_achievement_striving",
                    "name": "Achievement striving",
                    "category": "personality",
                    "percentile": 0.3645845278578773
                },
                {
                    "trait_id": "facet_cautiousness",
                    "name": "Cautiousness",
                    "category": "personality",
                    "percentile": 0.564629579815605
                },
                {
                    "trait_id": "facet_dutifulness",
                    "name": "Dutifulness",
                    "category": "personality",
                    "percentile": 0.04692567733072578
                },
                {
                    "trait_id": "facet_orderliness",
                    "name": "Orderliness",
                    "category": "personality",
                    "percentile": 0.9777204552498692
                },
                {
                    "trait_id": "facet_self_discipline",
                    "name": "Self-discipline",
                    "category": "personality",
                    "percentile": 0.4363289460388946
                },
                {
                    "trait_id": "facet_self_efficacy",
                    "name": "Self-efficacy",
                    "category": "personality",
                    "percentile": 0.4309770995969169
                }
            ]
        },
        {
            "trait_id": "big5_extraversion",
            "name": "Extraversion",
            "category": "personality",
            "percentile": 0.7022333831684571,
            "children": [
                {
                    "trait_id": "facet_activity_level",
                    "name": "Activity level",
                    "category": "personality",
                    "percentile": 0.360262004258913
                },
                {
                    "trait_id": "facet_assertiveness",
                    "name": "Assertiveness",
                    "category": "personality",
                    "percentile": 0.2578911492641615
                },
                {
                    "trait_id": "facet_cheerfulness",
                    "name": "Cheerfulness",
                    "category": "personality",
                    "percentile": 0.31455484722190186
                },
                {
                    "trait_id": "facet_excitement_seeking",
                    "name": "Excitement-seeking",
                    "category": "personality",
                    "percentile": 0.8749642937561481
                },
                {
                    "trait_id": "facet_friendliness",
                    "name": "Outgoing",
                    "category": "personality",
                    "percentile": 0.3776713834198305
                },
                {
                    "trait_id": "facet_gregariousness",
                    "name": "Gregariousness",
                    "category": "personality",
                    "percentile": 0.29251842654333093
                }
            ]
        },
        {
            "trait_id": "big5_agreeableness",
            "name": "Agreeableness",
            "category": "personality",
            "percentile": 0.19647597666301514,
            "children": [
                {
                    "trait_id": "facet_altruism",
                    "name": "Altruism",
                    "category": "personality",
                    "percentile": 0.22970073072191377
                },
                {
                    "trait_id": "facet_cooperation",
                    "name": "Cooperation",
                    "category": "personality",
                    "percentile": 0.6649205040682532
                },
                {
                    "trait_id": "facet_modesty",
                    "name": "Modesty",
                    "category": "personality",
                    "percentile": 0.4802864155630628
                },
                {
                    "trait_id": "facet_morality",
                    "name": "Uncompromising",
                    "category": "personality",
                    "percentile": 0.3667658853396018
                },
                {
                    "trait_id": "facet_sympathy",
                    "name": "Sympathy",
                    "category": "personality",
                    "percentile": 0.6995943255022419
                },
                {
                    "trait_id": "facet_trust",
                    "name": "Trust",
                    "category": "personality",
                    "percentile": 0.7362201866122572
                }
            ]
        },
        {
            "trait_id": "big5_neuroticism",
            "name": "Emotional range",
            "category": "personality",
            "percentile": 0.5223345958584424,
            "children": [
                {
                    "trait_id": "facet_anger",
                    "name": "Fiery",
                    "category": "personality",
                    "percentile": 0.2536184865442446
                },
                {
                    "trait_id": "facet_anxiety",
                    "name": "Prone to worry",
                    "category": "personality",
                    "percentile": 0.5036849889378207
                },
                {
                    "trait_id": "facet_depression",
                    "name": "Melancholy",
                    "category": "personality",
                    "percentile": 0.5946617544018551
                },
                {
                    "trait_id": "facet_immoderation",
                    "name": "Immoderation",
                    "category": "personality",
                    "percentile": 0.48935001335120426
                },
                {
                    "trait_id": "facet_self_consciousness",
                    "name": "Self-consciousness",
                    "category": "personality",
                    "percentile": 0.44644852346321034
                },
                {
                    "trait_id": "facet_vulnerability",
                    "name": "Susceptible to stress",
                    "category": "personality",
                    "percentile": 0.26208775929876726
                }
            ]
        }
    ],
    "needs": [
        {
            "trait_id": "need_challenge",
            "name": "Challenge",
            "category": "needs",
            "percentile": 0.07475510237799737
        },
        {
            "trait_id": "need_closeness",
            "name": "Closeness",
            "category": "needs",
            "percentile": 0.07080670243137788
        },
        {
            "trait_id": "need_curiosity",
            "name": "Curiosity",
            "category": "needs",
            "percentile": 0.008487677782176517
        },
        {
            "trait_id": "need_excitement",
            "name": "Excitement",
            "category": "needs",
            "percentile": 0.2651055715057321
        },
        {
            "trait_id": "need_harmony",
            "name": "Harmony",
            "category": "needs",
            "percentile": 0.3468359380331614
        },
        {
            "trait_id": "need_ideal",
            "name": "Ideal",
            "category": "needs",
            "percentile": 0.10132585557400087
        },
        {
            "trait_id": "need_liberty",
            "name": "Liberty",
            "category": "needs",
            "percentile": 0.09102597359707632
        },
        {
            "trait_id": "need_love",
            "name": "Love",
            "category": "needs",
            "percentile": 0.4845450456662292
        },
        {
            "trait_id": "need_practicality",
            "name": "Practicality",
            "category": "needs",
            "percentile": 0.4006548400729645
        },
        {
            "trait_id": "need_self_expression",
            "name": "Self-expression",
            "category": "needs",
            "percentile": 0.22016884639761491
        },
        {
            "trait_id": "need_stability",
            "name": "Stability",
            "category": "needs",
            "percentile": 0.1245552918146342
        },
        {
            "trait_id": "need_structure",
            "name": "Structure",
            "category": "needs",
            "percentile": 0.06392746686145095
        }
    ],
    "values": [
        {
            "trait_id": "value_conservation",
            "name": "Conservation",
            "category": "values",
            "percentile": 0.1862611379732888
        },
        {
            "trait_id": "value_openness_to_change",
            "name": "Openness to change",
            "category": "values",
            "percentile": 0.4156653686108567
        },
        {
            "trait_id": "value_hedonism",
            "name": "Hedonism",
            "category": "values",
            "percentile": 0.31980247423299535
        },
        {
            "trait_id": "value_self_enhancement",
            "name": "Self-enhancement",
            "category": "values",
            "percentile": 0.04188942860799577
        },
        {
            "trait_id": "value_self_transcendence",
            "name": "Self-transcendence",
            "category": "values",
            "percentile": 0.04794943049014583
        }
    ],
    "warnings": [
        {
            "warning_id": "WORD_COUNT_MESSAGE",
            "message": "There were 100 words in the input. We need a minimum of 600, preferably 1,200 or more, to compute statistically significant estimates"
        }
    ]
}
```
