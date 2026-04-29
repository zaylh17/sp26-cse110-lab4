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

## Question 12
A. `student.name`
B. `student['Grad Year']`
C. `student.greeting()`
D. `student['Favorite Teacher'].name`
E. `student.courseLoad[0]`

## Question 13 — Arithmetic

A. `'32'` — `+` with a string concatenates, so `2` becomes `'2'` and the result is `'32'`.
B. `1` — `-` only works with numbers, so `'3'` becomes `3`, and `3 - 2 = 1`.
C. `3` — `null` converts to `0`, so `3 + 0 = 3`.
D. `'3null'` — `+` with a string concatenates, so `null` becomes `'null'`, giving `'3null'`.
E. `4` — `true` converts to `1`, so `1 + 3 = 4`.
F. `0` — `false` converts to `0`, `null` converts to `0`, so `0 + 0 = 0`.
G. `'3undefined'` — `+` with a string concatenates, so `undefined` becomes `'undefined'`, giving `'3undefined'`.
H. `NaN` — `-` converts both to numbers. `'3'` becomes `3`, `undefined` becomes `NaN`. Any arithmetic with `NaN` gives `NaN`.

## Question 14 — Comparison

A. `true` — `'2'` is converted to the number `2`, and `2 > 1` is `true`.
B. `false` — Both are strings, so they're compared character by character. `'2'` (char code 50) is greater than `'1'` (char code 49), so `'2' < '12'` is `false`.
C. `true` — `==` does type conversion, so `'2'` becomes `2`, and `2 == 2` is `true`.
D. `false` — `===` does no type conversion. `2` is a number and `'2'` is a string, so they're not strictly equal.
E. `false` — `==` converts `true` to `1`, and `1 == 2` is `false`.
F. `true` — `Boolean(2)` is `true`, and `true === true` is `true` (same type, same value).

## Question 15

`==` (loose equality) compares values after performing type conversion, so `'3' == 3` is `true` because the string is converted to a number before comparing. `===` (strict equality) compares both value AND type with no conversion, so `'3' === 3` is `false` because one is a string and the other is a number. You should generally use `===` to avoid unexpected type coercion bugs.

## Question 17
The result is `[2, 4, 6]`. The function `modifyArray` loops through each element of the array and calls the `callback` function (which is `doSomething`) on each one. `doSomething` multiplies the number by 2. So: `1 * 2 = 2`, `2 * 2 = 4`, `3 * 2 = 6`. Each result is pushed to `newArr`, which is returned as `[2, 4, 6]`.

## Question 19
The output is:
1
4
3
2

Line 2 prints `1` immediately. Line 3 schedules `2` to print after 1000ms. Line 4 schedules `3` to print after 0ms. Line 5 prints `4` immediately. After the synchronous code finishes, `setTimeout` callbacks run — `3` prints first (0ms delay), then `2` prints last (1000ms delay). Even a 0ms `setTimeout` waits until all synchronous code is done before executing.