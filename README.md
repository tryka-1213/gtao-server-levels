# GTAO Discord Server Levels
Calculate server levelling information, including the number of messages required to reach a given level.


## Examples
### Level to message count
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
### Message count to level
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
### XP to level
```js
const { xpToLevel } = require("./index.js")

/**
usage: xpToLevel(xp)
*/

let level = xpToLevel(12313)
console.log(level) // 12
```
### Level to XP
```js
const { levelToXp } = require("./index.js")

/**
usage: levelToXp(level)
*/

let xp = levelToXp(300)
console.log(xp) // 5453760
```

## Levelling System Facts
### Multipliers
#memes-and-shitposting == 0.5x / 50% less xp   
#serious-discussions == 1.5x / 50% more xp

### XP Needed Per Level
Every new level, the XP needed to reach the next level is increased  
by 240, and then multiplied by 120.

Equation
```
var xpRequired = (currentLevel * 120) + 240
```
