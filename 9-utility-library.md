**Utility Library** - [Back to all questions](toc.md)

# The challenge
**_Best suited for:_** Senior | Expert **Stage:** Round 2 | Onsite

As a team you have decided to keep your code base as DRY as possible. You want to put in place a utility library of small frequently used functionality. The voted name is **Nodash** ;)
Since array manipulation is one of the most frequent task encountered by the team, you are tasked to start the project with these four methods as a base.

1. **chunk** : takes an array and a number as arguments. It will group elements of the array in smaller groups of the size passed in. The last group might contain the remaining items if it has enough to form a group.
```javascript
const array = [1,2,3,4,5,6,7,8,9];
const groupByThree = Nodash.chunk(array, 3);
const groupByFour  = Nodash.chunk(array, 4);
console.log(groupByThree);
// [[1,2,3],[4,5,6],[7,8,9]]
console.log(groupByFour);
// [[1,2,3,4],[5,6,7,8],[9]]
```
   
