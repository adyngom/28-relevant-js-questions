**FizzBuzz** - [Back to all questions](toc.md)

# The challenge
**Best suited for:** Junior | Senior **Stage:** Round 1 | All rounds

Write a program that prints the numbers from 1 to 100. But for multiples of three print Fizz instead of the number and for the multiples of five print Buzz. For numbers which are multiples of both three and five print FizzBuzz

## The context

The FizzBuzz challenge is not specific to JavaScript and has been part of the coding interview process in almost every programing language. It is usually a quick check to assess the candidate basic programing instincts, but can also be turned in an assessment for in depth knowledge if the interviewer decides to do so.
It is usually part of a light weight first technical interview done while screen sharing. It is also a favorite from a non JavaScript programmer to ask and quickly gauge your technical knowledge and approach.

In a Javascript context familiarity with some or all the following concepts are expected to be demonstrated:
* Logical operators
* Looping
* Falsy values
* Ternary operator
* Type coercion

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
Wait a minute, the above solution works and is readable ( kudos for that), but let's look into a quick refactor. We can make this a bit more JavaScripty and since we are to show our Javascript skills, this gets us to my favorite section... refactoring.

### The refactor

We could of course get to a fancy one liner here for this particular challenge, but I'm not a particular fan of doing stuff for the sake of fancy or pretty. 

So let's flip the switch what I'm going to do this time is I will show you my final solution and I will walk you through how did I get to it. 

This can turn into a handy skill if you are to read and understand other people's code or if you are to explain it to someone else. Through the years I have provided many solutions for this challenge, but the one below is by far my favorite.

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

The solution uses the ternary operator syntax to set the conditions and takes advantage of something that might not very obvious at first for the untrained eye - JavaScript falsy values.

Let's start with falsy values JavaScript, what in the heck are we talking about. A great definition is provided by the [Mozilla Developer Network (MDN )](https://developer.mozilla.org/en-US/docs/Glossary/Falsy):

> A falsy value is a value that is considered false when encountered in a Boolean context.
JavaScript uses Type Conversion to coerce any value to a Boolean in contexts that require it, such as conditionals and loops.

For our particular context the important keywords are **"Boolean context"** and **"conditionals"** since they are relevant to our solution. Before looking at how it applies, here is the list of the most common falsy values in Javascript:
* The boolean **false** not the same as the string **_'false'_**
* The number **0** - once again this is different from the string **_'0'_**
* The **null** object
* The primitive type **undefined** assigned to non initialized variable
* Any representation of an empty string **''**, **""**, **``** (single quotes, double quotes or back-ticks)

### The rewrite

Let's focus on one segment of our fizzBuzz function

```javascript
if( (i % 3) === 0 ) {
    output = 'Fizz';
}
// this could be refactored as
if( !(i % 3) ) output = 'Fizz';
```
Breaking down the refactored line gives us this picture
* if (...)  ==> **conditional construct outside - boolean context inside**
* !         ==> **is false**
* (i % 3)   ==> **type coercion - will check if value is falsy or truthy**

Replace **i** by a few numbers to better understand it
```javascript
if (!( 1 % 3) ...) /*becomes*/ if (!( 3 ) ...) /*3 is not false or falsy so check fails*/
if (!( 2 % 3) ...) /*becomes*/ if (!( 6 ) ...) /*6 is not false or falsy so check fails*/
if (!( 3 % 3) ...) /*becomes*/ if (!( 0 ) ...) /*0 is not false but is falsy so check passes*/
```
I can rewrite now my entire function using the logic above

```javascript
function fizzBuzz( start = 1, end = 100) {
    for( let i = start; i <= end; i++) {
        let output = i;
        if( !(i % 3) ) output = 'Fizz';
        if( !(i % 5) ) output = 'Buzz';
        if( !(i % 3) && !(i % 5) ) output = 'FizzBuzz';
        console.log(output);
    }
}
```
I was quite ecstatic when I got to this solution, but it did not too long unfortunately. The last line seemed redundant to me and honestly was bugging me. How could I combine the checks of 3 and 5 in one pass. 

And then it hit me, what if I could start with an empty string, attach to it the word 'Fizz' if it passes the 3 condition and attach the word 'Buzz' if it passes the 5 condition too. I drew this on a piece of paper

* i = 1 ==> no Fizz '' ==> no Buzz '' ==> output is 1
* i = 3 ==> yes 'Fizz' ==> no Buzz '' ==> output is 'Fizz'
* i = 5 ==> no Fizz '' ==> yes 'Buzz' ==> output is 'Buzz'
* i = 15 => yes 'Fizz' ==> yes 'Buzz' ==> output is 'FizzBuzz'

The ternary operator will allow to assign a value if condition checks and an alternate value if it fails in a very terse manner. 

Something else became obvious, we are outputting either a string or a number while we cycling through the values of **i** and as we saw in a previous section an empty string is a falsy value. So how do we translate all that intelligence into working code. 

The essential piece to achieve that was that the value of **output** was either going to be one of the possible strings 'Fizz', 'Buzz', 'FizzBuzz' or be falsy. In the falsy case **i** will just be passed as is. 

So the final rewrite with more comments

```javascript
function fizzBuzz( start = 1, end = 100) {
    for( let i = start; i <= end; i++) {
        let output =  ( (i % 3) ? '' : 'Fizz' ); // output is assigned a value or empty
	    output += ( (i % 5) ? '' : 'Buzz') ; // output concatenates the next value
	    console.log(output || i); // || or operator if output is falsy will show i value
    }
}
fizzBuzz(1,15);
```
[Back to all questions](toc.md)
