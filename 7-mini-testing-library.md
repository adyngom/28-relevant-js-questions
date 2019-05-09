**Mini testing library** - [Back to all questions](toc.md)

# The challenge
**_Best suited for:_** Junior | Senior | Expert **Stage:** Round 3 | Onsite

The dev team is shyly making its debut to the TDD approach. They don't want to commit yet to a full-fledged library but want to write simple tests directly on the console to test their most important functions. They have dubbed the experiment project dotLog and have provided the initial structure below:

```javascript
var dotLog = ( function() {
 return {
    describe(desc = 'test description:', testSet = []) {
        console.groupCollapsed(`${desc}: 0 passed - 0 failed`);
            // console out each test
        console.groupEnd();
    }
 }
}());
```

The **describe** method takes in a test label string and an array of test objects. The test object uses the following model:
```javascript
var testOne = { rule: ( 3 < 4), label: " 3 is less than 4" };
var testTwo = { rule: (Math.max.apply(null,[3,4,1,2,0]) === 4), label: " should output 4" };
```

Now those can be added to a testSet and be passed to the **describe** method
```javascript
var testSet = [testOne, testTwo];
dotLog.describe("Basic Math tests:", testSet);
Given the following 'naïve' function
function sum (x, y) {
	return x + y;
}
```

Fix it and the describe method so the following output is displayed:
```javascript
sum(): 3 passed - 1 failed
    √ Should return 0 if no arguments
    √ Should add two numbers
    √ Should add up any amount of numbers
    x Should convert any non-digit to 0 and return the right amount
```

# The context
I have had my share of rejections but have also been very successful at landing the job. In all the interviews I have been through, only two companies have ever presented a challenge similar to this one.
 
The particularity of it was that I was actually seating with the entire development team, where would eventually be my work station and participated in the standup and was given half the day to solve for the problem. At the end of the four hours, I was taken to lunch and bid farewell.

Though I landed both of those, the interesting part was the process. I got to work directly in what would be my daily environment, the challenge was an actual user story in their backlog. 

I could not cheat on my soft skills if I wanted to be successful, I had to reach out to my "soon to be" teammates to find out more details, or a quick setup issue. I had to submit my changes via a PR. 

Word of advice, commit often and use descriptive messages about your changes.

In summary, I think companies can invest some time in accommodating this type of setup. Another approach might be to give it as an at home exercise with a time limit and have the candidate come and discuss her solution onsite with the team.

[Back to all questions](toc.md)
