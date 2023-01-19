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
![image](https://user-images.githubusercontent.com/74735976/213485565-08c92a63-4462-4565-bb0e-18aa3cb78f16.png)


dont forget porting your server 
```js
app.listen(3001, () => {console.log("We are connected with port 3001 ...");})
```
# Connect With DataBase Mongodb (mongoose)
```js
mongoose.connect("Url" , {useNewUrlParser: true} );
```

what about react script ?
here is => 
```js
 const [user, setUser] = useState("");
        const [pwd , setPwd] = useState("");

        const [user1, setUser1] = useState("");
        const [pwd1 , setPwd1] = useState("");

      

        // login
           const loginacc = () => {
                Axios.post("http://localhost:3001/readacc", {user1: user1,pwd1:pwd1}).then(() => {console.log("Success")})
                setTimeout(() => {
                    Axios.post("http://localhost:3001/readacc").then((response) => {console.log(response.data)})
                }, 1000);
           }

        // rejister
        const rejme = () => {
            Axios.post("http://localhost:3001/acc", {user: user,pwd:pwd}).then(() => {console.log("Success")})
        }
```

![image](https://user-images.githubusercontent.com/74735976/213483887-fff7d9f0-932c-44e5-80cf-c5ed73b3f0cf.png)

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
