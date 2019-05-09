**Code analysis and possible refactor** - [Back to all questions](toc.md)

# The challenge
**_Best suited for:_** Senior | Expert **Stage:** Round 2 | Round 3 | Onsite

The sales team wants to have a small program that helps them remove any duplicates from a batch of tickets. Tickets batches are usually between **1,000** to **10,000** unfiltered items. The following solutions have been submitted by 3 developers in your team.

**Developer 1**
```javascript
if( !Array.prototype.uniq ) {
    Array.prototype.uniq = function() {
        let _singles = [];
        const arr = this;
        for ( let i = 0; i < arr.length; i++ ) {
            if(_singles.indexOf(arr[i]) === -1 ) {
                _singles.push( arr[i] );
            }
        }
        return _singles;
    }
}
```

**Developer 2**
```javascript
if(!Array.prototype.uniq) {
    Array.prototype.uniq = function() {
        return this.reduce( (arr, val) => {
            if (!arr.includes(val)) arr.push(val);
            return arr;
        }, [] );
    }
}
```

**Developer 3**
```javascript
if(!Array.prototype.uniq) {
   Array.prototype.uniq = function() {
       return new Set([...this]);
   }
}
```

Two tests files are provided [**onekTickets.js**](https://gist.github.com/adyngom/748873da9cb37828765216a36e7b7ec2) and [**tenkTickets.js.**](https://gist.github.com/adyngom/62c25502eed121e9092c97fd9041afa0)

Only one solution can be pushed to production. Which, if any, would you pick based on readability and performance?

Can any of the proposed solutions be even more optimized to get to a better one?
What would be the PR message you will leave for each of the developers regarding their solution and why it was or was not chosen?

# The context
In a normal development environment, you will be expected to read, evaluate and eventually critique other people's code.

The PR reviews are a critical step in making sure quality code is being pushed to the main repo.

Now each team or company can have their own take about how to define quality, but cannot walk away from clearly outlining standards, conventions and coding culture.

This type of question is both beneficial to the employer but to the candidate as well. Your main interaction with the team will be through similar exercises on a daily basis.

As an interviewer, my expectation will be for the candidate to reference some benchmarking tools to help determine which block of code is the fastest.

I surely will be impressed if she could eyeball it and clearly explain why, but since we are talking about giving feedback, it will be always easier to show rather than just tell.

**console.time** and **console.timeEnd** might kick off the conversation in the right direction, [jsperf.com](jsperf.com) is also one the industry's favorite, but ultimately looking for, suggesting, doing a basic setup and running a quick benchmark would be a clear winner.

Finally, I would like to have an open discussion about readability, and maybe why sometimes it might be beneficial to sacrifice a little speed in spite of it.

[Back to all questions](toc.md)
