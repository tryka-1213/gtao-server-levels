# GTAO Discord Server Levels
Calculate server levelling information, including the number of messages required to reach a given level.  
Available in a hacked together GUI form @ [https://tryka-1213.github.io/gtao-server-levels-calculator/](https://tryka-1213.github.io/gtao-server-levels-calculator/)

## Functions
all results are approximated, because there's no way to accurately factor in message frequency or channel usage
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
## XP Per Message
30xp per message, limited to 30xp per 30 seconds.
Examples:
- 1 message sent in 1 minute => 30xp
- 3 messages sent in 1 minute => Max of 60xp
  
### Multipliers
#memes-and-shitposting == 0.5x / 50% less xp   
#serious-discussions == 1.5x / 50% more xp  
#lfg- == 0.2x / 80% less xp

### XP Needed Per Level
At every new level, the XP needed to reach the next level is increased  
by 240, and then multiplied by your current level, and then by 120.

Equation
```
xpRequiredForNextLevel = (currentLevel * 120) + 240
```
