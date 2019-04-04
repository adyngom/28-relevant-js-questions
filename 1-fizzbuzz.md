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


