# Discord Bot Language System 📢

[![GitHub issues](https://img.shields.io/github/issues/ryzenen/Discord-Bot-Language-System.svg)](https://github.com/ryzenen/Discord-Bot-Language-System/issues) [![GitHub forks](https://img.shields.io/github/forks/ryzenen/Discord-Bot-Language-System.svg)](https://github.com/ryzenen/Discord-Bot-Language-System/network) [![GitHub stars](https://img.shields.io/github/stars/ryzenen/Discord-Bot-Language-System.svg)](https://github.com/ryzenen/Discord-Bot-Language-System/stargazers)

Paste your main file:

```js
const config = require('./config.json');
const db = require('quick.db')
client.tr = require('./Language/Turkish.js')
client.en = require('./Language/English.js')
```

create config.json and paste code:
```json
{
 "lang": "en"  //Default Language
 }
 ```
 
Create `Language` directory, and create
 
`Turkish.js`:
```js
const tr = {
"hi": "Merhaba"
}
module.exports = tr;
```

`English.js`:
```js
const en = {
"hi": "Hi"
}
module.exports = en;
```

## Test Command
```js
const config = require('../../config.json') //Const config.json
const db = require("quick.db") //Const db
module.exports = {
    name: "hi",
    async execute(client, message) {  

let language = config.lang
if (message.guild) {
 if (db.has(`lang_${message.guild.id}`) === true ) {
   language = db.fetch(`lang_${message.guild.id}`)
 }}
 const lang = client[language]

message.channel.send(lang.hi) //Return: Hi 
}
}
```

## © Ryzenen. All rigths reserved
