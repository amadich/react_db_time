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
