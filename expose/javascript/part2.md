# Part 2

## Question 1
`3` — The variable `i` is declared with `var` in the for loop, which gives it function scope. After the loop finishes iterating through all 3 elements, `i` becomes `3` (the value that fails the `i < prices.length` condition). Since `var` is function-scoped, `i` is still accessible outside the loop on line 12.