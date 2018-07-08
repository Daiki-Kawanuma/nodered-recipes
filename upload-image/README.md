# 画像アップロード

![flow](https://github.com/Daiki-Kawanuma/nodered-recipes/blob/master/upload-image/image.png)

画像をアップロードするレシピ

```
[{"id":"cfe5184a.b9b8b8","type":"template","z":"7cc27111.df64e","name":"画像アップロード","field":"payload","fieldType":"msg","format":"html","syntax":"mustache","template":"<html>\n<head><title>Image upload</title></head>\n<body>\n<h1>Image upload</h1>\n<h2>Select an image file</h2>\n<form  action=\"/image\" method=\"post\" enctype=\"multipart/form-data\">\n    <input type=\"file\" name=\"imagedata\" accept=\"image/*\"  />\n    <input type=\"submit\" value=\"Upload\"/>\n</form>\n</body>\n</html>","x":350,"y":40,"wires":[["127bb0b8.48d13f"]]},{"id":"c42acfae.4abb3","type":"http in","z":"7cc27111.df64e","name":"[GET] /upload_image","url":"/upload_image","method":"get","upload":false,"swaggerDoc":"","x":110,"y":40,"wires":[["cfe5184a.b9b8b8"]]},{"id":"127bb0b8.48d13f","type":"http response","z":"7cc27111.df64e","name":"response","statusCode":"","headers":{},"x":560,"y":40,"wires":[]}]
```

要求例: https://nodered-recipes-sample.mybluemix.net/upload_image
