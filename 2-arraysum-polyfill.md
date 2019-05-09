**Array sum polyfill** - [Back to all questions](toc.md)

# The challenge
**Best suited for:** Junior | Senior **Stage:** Round 2 | Onsite 

You might have to add all items in an array of numbers. You have been keeping up to date with new stuff in JS but are not sure that **sum()** is part of the Array prototype methods. 

Write a small program that will add all the items in an array of numbers and return the total using the Array **sum** function if it exists or using your custom function.

```javascript
 // should output 21
[1,2,3,4,5,6].sum();
// should be chainable and also output 21
[1,2,3].concat([4,5,6]).sum();
```

# The context
Extending native objects is usually frowned upon in JS circles. This should stir a ‘healthy’ debate on the pros and cons of doing so. Ultimately, it should highlight the candidate awareness of safeguarding against potential existing and future functionality override. 

I believe it’s a good question for a code screening or the first question on an onsite interview.

[Back to all questions](toc.md)
