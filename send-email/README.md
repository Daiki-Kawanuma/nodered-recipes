# メールを送る

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/send-email/image.png)

メールを送るレシピ

```
[{"id":"7f994e20.36e3b","type":"http in","z":"4faf54ca.3a4afc","name":"","url":"/mail","method":"get","upload":false,"swaggerDoc":"","x":100,"y":160,"wires":[["69751fa.76062e"]]},{"id":"69751fa.76062e","type":"function","z":"4faf54ca.3a4afc","name":"メール設定","func":"msg.payload = msg.req.query.content;\nmsg.topic = msg.req.query.topic;\nmsg.to = msg.req.query.to;\nreturn msg;","outputs":1,"noerr":0,"x":270,"y":160,"wires":[["94e522ac.ccb09","98f6f23b.f13ac"]]},{"id":"98f6f23b.f13ac","type":"http response","z":"4faf54ca.3a4afc","name":"","statusCode":"","headers":{},"x":430,"y":160,"wires":[]},{"id":"94e522ac.ccb09","type":"e-mail","z":"4faf54ca.3a4afc","server":"smtp.gmail.com","port":"465","secure":true,"name":"","dname":"","x":430,"y":220,"wires":[]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/mail?to=test@example.com&&topic=hello&content=world

*Gmail を SMTP に使う準備*
https://myaccount.google.com/lesssecureapps
![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/send-email/image2.png)
