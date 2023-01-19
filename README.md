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

What about Insert select accunets ?
here is : 
```js
app.get("/insert", async (req,res) => {
    const fmyc  = new myc({timename: "Fin", timeEnergie: 100});
    try{
        await fmyc.save();
        res.send("my Collection Inserted!");
    }catch(err) {
        console.log(err);
        res.send("This User Is here ADD other one");
    }
})

app.post("/acc", async (req,res) => {
    const user = req.body.user;
    const pwd = req.body.pwd;
    

    const acc =  new Accunets({username: user , password: pwd});
    try{
        await acc.save();
        res.send("New Accunet Inserted");
    }catch(err) {
        console.log(err);
        res.send("This Accunet A ready exist");
    }

})



app.post("/readacc" , (req,res) => {

    const user1 = req.body.user1;
    const pwd1 = req.body.pwd1;
    console.log(req.body);
    Accunets.find({"username": user1, "password": pwd1}, (err,result) => {
        if (err) {
            res.send(err);
        }
        else res.send(result);
    })
})
```
# Thanks 🌹 . . . 
dont forget to add start ⭐
#
