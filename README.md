# GTAO Discord Server Levels
Calculate server levelling information, including the number of messages required to reach a certain level.


### Examples
```js
const { levelToMessageCount } = require("./index.js")

/**
usage: levelToMessageCount(level, isPrestige?)
where `isPrestige?` refers to if you have Prestige 1 or not.
Prestige 1 will boost XP earned by 20%
*/

let messagesNeeded = levelToMessageCount(100, false)
console.log(messagesNeeded) // 20592
```
Returns: `20592`
