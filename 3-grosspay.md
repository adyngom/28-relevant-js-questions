**Calculate employee gross pay** - [Back to all questions](toc.md)

# The Challenge
**Best suited for:** Senior | Expert **Stage:** Round 2 | Round 3 | Onsite

As a new member of the Kora Inc. development your new hot assignment is to help the HR department quickly calculate employees gross pay. Below are the compensation models for each role:

```javascript
const associate = { roleId: 3, rate: 12.5,overtime: 18.75 };
const supervisor = { roleId: 2, rate: 15,overtime: 22.5 };
const admin = { roleId: 1, rate: 30,  overtime: 0 // salary no overtime };
```

Write a **base function** that takes a **role (object)**, **hours** (number) and **ovtHours** (number) as arguments and returns the employee gross pay. Using this base function, **create three partial functions** that respectively will calculate the associate, supervisor, admin gross pay when invoked.

# The context
From a first look, putting a function or program to calculate gross pay is very straightforward. Here, as I’m screening the candidate, I will pay close attention to her/him taking the time in reading about the specificity of the solution asked.

I will expect to have a lot of questions around the terms **base function** and the concept of **partial application**. I will also not push for in-depth knowledge of **functional programming** concepts such as **currying** but I will expect a general awareness of those.

[Back to all questions](toc.md)
