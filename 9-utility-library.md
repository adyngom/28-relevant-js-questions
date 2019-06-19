**Utility Library** - [Back to all questions](toc.md)

# The challenge
**_Best suited for:_** Senior | Expert **Stage:** At home | Round 2 | Onsite

As a team you have decided to keep your code base as DRY as possible. You want to put in place a utility library of small frequently used functionality. The voted name is **Nodash** ;)

Since array manipulation is one of the most frequent task encountered by the team, you are tasked to start the project with these four methods as a base:

### **Chunk**
This method takes an array and a number as arguments. It will group elements of the array in smaller chunks of the size passed in. 

The last group might contain the remaining items if it does not have enough to form a full size group.
```javascript
const array = [1,2,3,4,5,6,7,8,9];
const groupByThree = Nodash.chunk(array, 3);
const groupByFour  = Nodash.chunk(array, 4);
console.log(groupByThree);
// [[1,2,3],[4,5,6],[7,8,9]]
console.log(groupByFour);
// [[1,2,3,4],[5,6,7,8],[9]]
```

### **Compact**
This method takes an array as argument and returns a new array with all the falsy values removed.
```javascript
const array = [1,,2,false,3,-1,0,4,null];
console.log(Nodash.compact(array));
// [1,2,3,-1,4];
```

### **Difference**
This method takes in two arrays and returns one array that contains all the items unique to each
```javascript
const array  = [1,3,4,5,8,9];
const array2 = [1,2,4,5,9,3];
console.log(Nodash.compact(arrray, array2));
// [2,8]
```

### **Flatten**
Given an array with nested items, this method should return a flat array of all the items
```javascript
const array = [1,2,[3,4], 5,6,[7,8,[9,10]]];
console.log(Nodash.flatten(array));
// [1,2,3,4,5,6,7,8,9,10]
```
   
