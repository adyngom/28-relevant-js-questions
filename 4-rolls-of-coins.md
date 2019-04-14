# The Challenge

At the end of her shift, Amina’s tip jar is full of coins. She needs a little help in counting and stocking her hard earned loot. She wants to organize her coins in rolls so it is easy to bring back to the bank. 

Write a program that will help her quickly find out how many rolls she has for each coin denomination and the remainder on each. 

Below is a table of how many coins should be in each roll per denomination:


Coins | Coins per roll | Value
---------|----------|---------
 Penny   ==> 1 | 50 | $0.50
 Nickel  ==> 5 | 40 | $2.00
 Dime    ==> 10 | 50 | $5.00
 Quarter ==> 25 | 40 | $10.00

 Your program will accept an unsorted array of coins. You can assume that each coin will be either 1, 5, 10 or 25. It should print a message like the one below:

Pennies:10 rolls - 39 left
<br />Nickels:   25 rolls - 0 left
<br />Dimes:     12 rolls - 49 left
<br />Quarter:    2 rolls - 20 left
