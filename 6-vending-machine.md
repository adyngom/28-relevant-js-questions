**Vending machine** - [Back to all questions](toc.md)

# The challenge
**Best suited for:** Junior | Senior | Expert **Stage:** Round 2 | Round 3 | Onsite

Bob runs a successful Vending Machine business. He wants to add an interface that makes them a bit user-friendly and make it easy to add and track inventory. Below is the typical inventory model for the machines:
```javascript
const drinks = {
    1: { name: "Mango Juice", stock: 2 },
    2: { name: "Banana Smoothies", stock: 2 },
    3: { name: "Guava Mix", stock: 1 },
    4: { name: "Citrus Blend", stock: 3 }
  };
```
Write a program that creates an instance of the Vending Machine (VM) with the following specifications:

The VM needs to be passed an inventory object in order to create an instance
If the object is not passed, the program should throw a descriptive error:
```javascript
const vm = new VM(drinks); // instance get created
// but
const emptyVM = new VM(); // throws a no inventory error
```

VM should assign the newly passed inventory to a private drinks variable that is not modifiable from the instance
```javascript
vm.drinks; // should output undefined
```

VM should have a callable sale method that takes the drink id as an input and return a success message if in stock or a failed message if out of stock
VM will always deduct one (1) from the product id stock after a successful sale
```javascript
vm.sale(1);
// output: 1 Mango Juice - Thank you, come again!!
vm.sale(1);
// output: 1 Mango Juice - Thank you, come again!!"
vm.sale(1);
// output: Mango Juice is out of stock :( Come back tomorrow
vm.sale(4);
// output: 1 Citrus Blend - Thank you, come again!!
```

Finally VM should also have a callable stock method. It does not take any parameters and should display the total count of available drinks. 

The drinks object given as an example has a total of 8 drinks. After buying 2 mango juice, the output of the stock method should 6. it should also output 'Out of stock' if empty.
```javascript
vm.stock(); // should output total of all drinks left or Out of stock
```

# The context
Function with a constructor, new ES6 class, or Object create?? There are so many ways to approach this that I hope that the interviewer should be as prepared as the candidate.

A solid understanding of closures is going to help tremendously. It will be interesting also to see how the candidate approach scope and private variable and see if any design patterns are implicitly or explicitly used.

I think that no matter the level of the candidate, this type of exercise should allow touching on many key concepts of the JS language.

[Back to all questions](toc.md)
