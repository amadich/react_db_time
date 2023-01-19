# React Database Login Page (MongoDB) 🍃

Start Create Folder Server 
```cmd
mkdir server
mv server.js server/
```
Push Your connection requeste
```cmd
nano server/server.js
```
#
```js
const express = require("express");
const app = express();
const mongoose = require("mongoose");
const cors = require("cors");
const myc = require('./models/myc');
const Accunets = require("./models/accunets");

app.use(cors());
app.use(express.json());
```
![image](https://user-images.githubusercontent.com/74735976/213483887-fff7d9f0-932c-44e5-80cf-c5ed73b3f0cf.png)

dont forget porting your server 
```js
app.listen(3001, () => {console.log("We are connected with port 3001 ...");})
```
# Connect With DataBase Mongodb (mongoose)
```js
mongoose.connect("Url" , {useNewUrlParser: true} );
```
