**Part 2**

## Question 1
`3` — The variable `i` is declared with `var` in the for loop, which gives it function scope. After the loop finishes iterating through all 3 elements, `i` becomes `3` (the value that fails the `i < prices.length` condition). Since `var` is function-scoped, `i` is still accessible outside the loop on line 12.

## Question 2
As the loop runs 3 iterations, and on the last iteration `discountedPrice` is set to `300 * 0.5 = 150`. Since it's declared with `var` (function scope), the value persists outside the loop and line 13 prints `150`.

## Question 3
`finalPrice` is declared with `var` on line 4, giving it function scope. After the loop's last iteration, `finalPrice` is set to `Math.round(150 * 100) / 100 = 150`. Since `var` is function-scoped, it's accessible on line 14 and prints `150`.

## Question 4
The function returns `[50, 100, 150]`. The loop applies the 50% discount to each price, rounds it, and pushes it to the `discounted` array. Line 16 returns that array.

## Question 5
`ReferenceError: i is not defined` error will appear as `i` is declared with `let` in the for loop, giving it block scope. It only exists inside the loop block (lines 6–10). Line 12 is outside that block, so `i` is not accessible.

## Question 6
`ReferenceError: discountedPrice is not defined` error will appear as `discountedPrice` is declared with `let` inside the for loop block on line 7, giving it block scope. It only exists inside the loop (lines 6–10). Line 13 is outside that block, so it's not accessible.

## Question 7
`finalPrice` is declared with `let` on line 4 at the function level, not inside the loop block. So it's accessible throughout the function. After the loop's last iteration, its value is `150`, and line 14 prints it.

## Question 8
The function returns `[50, 100, 150]`. Same result as question 4. `discounted` and `finalPrice` are declared with `let` at the function level, so they're accessible throughout the function. The loop applies the 50% discount to each price, rounds it, and pushes it to the array.

## Question 9
`ReferenceError: i is not defined` error will appear as `i` is declared with `let` in the for loop on line 6, giving it block scope. It only exists inside the loop (lines 6–9). Line 11 is outside that block, so `i` is not accessible.

## Question 10
`length` is declared with `const` on line 4 at the function level, so it's accessible throughout the function. Its value is `prices.length` which is `3`. `const` prevents reassignment but not reading.

## Question 11
The function returns `[50, 100, 150]`. `discounted` is declared with `const` as an empty array, but `const` only prevents reassignment — you can still modify the array's contents with `.push()`. The loop pushes each discounted price, and line 14 returns the array.