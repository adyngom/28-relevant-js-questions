# The challenge

Write a program that prints the numbers from 1 to 100. But for multiples of three print Fizz instead of the number and for the multiples of five print Buzz. For numbers which are multiples of both three and five print FizzBuzz

## The context

The FizzBuzz challenge is not specific to JavaScript and has been part of the coding interview process in almost every programing language. It is usually a quick check to assess the candidate basic programing instincts, but can also be turned in an assessment for in depth knowledge if the interviewer decides to do so.
It is usually part of a light weight first technical interview done while screen sharing. It is also a favorite from a non JavaScript programmer to ask and quickly gauge your technical knowledge and approach.

## The approach

As of any problems that you might encounter, even those that seem familiar, a good read and break down to small pieces is a must. Be clear to the interviewer that you need 3 to 5 minutes to read it calmly and propose a rewrite of your understanding. If you are comfortable doing that part out loud, that's even better. For example this is how I might go for the rewrite:

* So log to the console numbers from 1 to 100 - I'm going to need a loop
* For multiple of 3 instead of the number output the string 'Fizz'
* Do the same for multiples of 5 with the output being 'Buzz'
* In the case the number is a multiple of both 3 and 5 then output 'FizzBuzz' - how to check if a is a multiple of b??
* If all the above cases fail then just output the number as is

I would probably ask to the interviewer if I should worry about edge cases or bad inputs. It is usually implied that the input will be correct and edge cases might not be necessary. The fact that you ask though, adds a touch of eloquence to your problem solving approach.

## The solution(s)

On thing that is key and is worthy of practice is walking the person through your steps as you are building the solution during the interview. Start with the obvious, you will probably need a function or class as your primary construct. Start there and always think of the K.I.A.S.S.A.P :) principle - Keep It As Stupid Simple As Possible

### First step

```javascript
// comments are me talking out loud
// let's build the function structure
function fizzBuzz( start = 1, end = 100) { // default parameters to set the default range
    // I need a loop - let's go with for
    for( let i = start; i <= end; i++) {
        // probably a variable for what will be outputted
        let output = i;

        // rest of the logic here

        // outputting the result
        console.log(output);
    }
}
// call the function
fizzBuzz(); // this prints out 1 to 100 - fancy ;)
```
The above satisfies my first goal on my rewritten challenge understanding

### Second step

Now if I follow the cadence of the challenge I will solve for two things: 

    1. Choosing the proper operator to find if a number is a multiple of another
    2. Apply it for the multiple of 3 condition and output 'Fizz'

The remainder operator - %, is the perfect tool here. If number a is a multiple of number b then

```javascript
( b % a) === 0; // will be true;
// 4 is a multiple of 2
( 4 % 2 ) === 0; // is true
```
Let's apply this in the body of our function

```javascript
// rest of the logic here
if( (i % 3) === 0 ) {
    output = 'Fizz';
}
// Knowing that 3,6 and 9 are multiple of 3 let's
// quickly test a small sequence by calling

fizzBuzz(1,10); 
// this should output
// 1, 2, 'Fizz', 4, 5, 'Fizz', 7, 8, 'Fizz', 10
```

### Final step

Since the Fizz condition ran perfect we can now apply the same logic  to the rest

```javascript
// multiple of 5
if( (i % 5) === 0 ) {
    output = 'Buzz';
}

// multiple of 3 and 5
if( (i % 3) === 0  && (i % 5 === 0)) {
    output = 'FizzBuzz';
}
```

Wowza!! this satisfies all the conditions and gives us this chef d'oeuvre of a solution once assembled 
and stripped out of all comments

```javascript
function fizzBuzz( start = 1, end = 100) { // default parameters to set the default range
    for( let i = start; i <= end; i++) {
        let output = i;
        if( (i % 3) === 0 ) {
            output = 'Fizz';
        }
        if( (i % 5) === 0 ) {
            output = 'Buzz';
        }
        if( (i % 3) === 0  && (i % 5) === 0) {
            output = 'FizzBuzz';
        }
        console.log(output);
    }
}
fizzBuzz();
```
Wait a minute, the above solution works and is readable ( kudos for that), but let's look into a quick refactor. We can make this a tad more performant and a bit more JavaScripty which gets us into the next section... refactoring. 


### The refactor

We could of course get to a fancy one liner here for this particular challenge, but I'm not a particular fan of doing stuff for the sake of fancy or pretty. 

As an interviewer, I spend more time making the candidate explain how it came down to that one liner and if we are to sacrifice readability what are the true gains in return. Short code might be great but does not necessarily means better solution.

```javascript
function fizzBuzz( start = 1, end = 100) {
    for( let i = start; i <= end; i++) {
        let output =  ( (i % 3) ? '' : 'Fizz' ); // if multiple of 3 is falsy
	    output += ( (i % 5) ? '' : 'Buzz') ; // if multiple of 5 is falsy
	    console.log(output || i); // output value or i if output is falsy
    }
}
fizzBuzz(1,15);
```