**Part 1**

## Question 1
Line 9 would print`values added: 20`

## Question 2
Line 13 would still print `final result: 20`

## Question 3
We shouldn't use `var` because it is function scope instead of block scope, which can then lead to bugs and unpredictable behavior. `let` and `const` use block scope, which is more predictable as a variable declared inside a block stays inside that block.

## Question 4
Line 9 would still print `values added: 20`

## Question 5
This throws a `ReferenceError: result is not defined`. Unlike `var`, `let` has block scope, so `result` only exists inside the if block (lines 3–11). Line 13 is outside that block, so `result` doesn't exist.

## Question 6
There will be a `TypeError: Assignment to constant variable`. On line 5, `result` is declared with `const` and set to `0`. Then nn line 7, the code tries to reassign `result` to `num1 + num2`, but `const` prevents reassignment. This error causes line 9 to never run.

## Question 7
This never runs either. The code already crashed at line 7 with the `TypeError` from question 6, so execution stops before reaching line 13.