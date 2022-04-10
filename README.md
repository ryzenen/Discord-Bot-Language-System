# Discord Bot Language System 

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
