## The Challenge

As a new member of the Kora Inc. development your new hot assignment is to help the HR department quickly calculate employees gross pay. Below are the compensation models for each role:

```javascript
const associate = { roleId: 3, rate: 12.5,overtime: 18.75 };
const supervisor = { roleId: 2, rate: 15,overtime: 22.5 };
const admin = { roleId: 1, rate: 30,  overtime: 0 // salary no overtime };
```

Write a **base function** that takes a **role (object)**, **hours** (number) and **ovtHours** (number) as arguments and returns the employee gross pay. Using this base function, **create three partial functions** that respectively will calculate the associate, supervisor, admin gross pay when invoked.
