# GTAO Discord Server Levels
Calculate server levelling information, including the number of messages required to reach a certain level.


### Examples
```js
const { levelToMessageCount } = require("./index.js")

/**
usage: levelToMessageCount(level, isPrestige?)
where `isPrestige?` refers to if you have Prestige 1 or not.
Prestige 1 will boost XP earned by 20%. Default value is false
*/

let messagesNeeded = levelToMessageCount(100, false)
console.log(messagesNeeded) // 20592
```

```js
const { messageCountToLevel } = require("./index.js")

/**
usage: messageCountToLevel(level, isPrestige?)
where `isPrestige?` refers to if you have Prestige 1 or not.
Prestige 1 will mean User A will need 20% less messages to reach 
the same level as User B, who has no prestige
*/

let level = messageCountToLevel(38500, false)
console.log(level) // 136
```
