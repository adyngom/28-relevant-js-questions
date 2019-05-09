**Input autocomplete** - [Back to all questions](toc.md)

# The challenge
**_Best suited for:_** Senior | Expert **Stage:** At home | Round 2 | Onsite

The UX team has insisted that the country search input form needed to be more user-friendly.
 
They have their mind made on a "simple" autocomplete search box. What's not so simple and not obvious to the UX team, is that you have a huge dataset of possible results that would not be feasible to store on the client side. 

Your task is to create a program that listens to user input events and fetches a list of possible matches. The UX team is not a big fan of dirty matching and wants the list to only show the country names that start with the search term entered by the user - oh and they want matches to be highlighted by the way on the list results

# The context
I have had similar tests provided and with usually a 48 to 72 hours to submit it back. I strongly advise that you use all the time allocated to come up with the most refined solution available.
 
This has the advantage to mimic to a certain extent what an actual user story might be and you are given time to execute. 

And please, please don't just go blindly copy and paste a solution that you do not have a full grasp on. 

You will be expected to come on site or online to talk about your solution, your reasoning and more than often a 'feature creep' will happen during evaluation to see how you will handle it. 

For this particular problem, the async nature of the search and filter is going to be the first hurdle, but I would not personally start there. I would probably start with a small set of local data and focus on making the autocomplete and highlight as solid as possible.

As an interviewer I would love to see the candidate talk about and integrate all or most of the concepts below:

- Throttle [link](https://css-tricks.com/debouncing-throttling-explained-examples/)
- Debounce [link](https://davidwalsh.name/javascript-debounce-function)
- Caching
- Memoization [link](https://medium.freecodecamp.org/understanding-memoize-in-javascript-51d07d19430e)
- Error Handling 

Take-homes are more challenging than they might seem at first. Usually, enough is given to get you started, but a lot is expected on your delivery.

[Back to all questions](toc.md)
