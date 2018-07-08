# CSS適用

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/apply-css/image.png)

CSSを適用するレシピ

```
[{"id":"76087eec.5388b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/css","method":"get","upload":false,"swaggerDoc":"","x":100,"y":60,"wires":[["541e041d.c9ac2c"]]},{"id":"a5ece4f7.299288","type":"http response","z":"4faf54ca.3a4afc","name":"response","statusCode":"","headers":{},"x":540,"y":60,"wires":[]},{"id":"a64130f9.8b0a4","type":"template","z":"4faf54ca.3a4afc","name":"HTML","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"<style type=\"text/css\">{{{payload.css}}}</style>\n<h1>Hello, Node-RED</h1>\n<input class=\"raised\" type=\"button\" value=\"Click Me\">","output":"str","x":390,"y":60,"wires":[["a5ece4f7.299288"]]},{"id":"541e041d.c9ac2c","type":"template","z":"4faf54ca.3a4afc","name":"CSS","field":"payload.css","fieldType":"msg","format":"css","syntax":"mustache","template":"h1{\nposition: relative;\npadding: 0.5em;\nbackground: #a6d3c8;\ncolor: white;\n}\n\nh1::before {\nposition: absolute;\ncontent: '';\ntop: 100%;\nleft: 0;\nborder: none;\nborder-bottom: solid 15px transparent;\nborder-right: solid 20px rgb(149, 158, 155);\n}\n\n.raised{\n  display: inline-block;\n  background-color: #26a69b;\n  color: #FFF;\n  font-size: 1em;\n  line-height: 1;\n  text-decoration: none;\n  letter-spacing: 0.05em;\n  padding: 0.2em 1em;\n  border-radius: 3px;\n    cursor: pointer;\n  box-shadow: 0 2px 2px 0 rgba(0,0,0,0.14), 0 1px 5px 0 rgba(0,0,0,0.12), 0 3px 1px -2px rgba(0,0,0,0.2);/*影*/\n  -webkit-tap-highlight-color: transparent;\n  transition: .3s ease-out;\n}\n\n.raised:hover{\n    box-shadow: 0 3px 3px 0 rgba(0,0,0,0.14), 0 1px 7px 0 rgba(0,0,0,0.12), 0 3px 1px -1px rgba(0,0,0,0.2);/*浮き上がるように*/\n}\n\ninput[type=\"button\"]:focus {\n  outline: 0;\n}\n","output":"str","x":250,"y":60,"wires":[["a64130f9.8b0a4"]]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/css
