### Examination: Unit 5 - Functions

#### Category 1: Function Fundamentals

1.  What is the primary purpose of writing a **function prototype**? What problem does it solve for the C compiler?
2.  Explain the flow of control when a function is called from `main()`. What happens to `main()`'s execution, and when does it resume?
3.  What is the difference between a **library function** (like `printf`) and a **user-defined function**?
4.  Can a function be defined inside another function in C? Why or why not?
5.  What is the purpose of the `return` statement? Can a function that is declared as `void` have a `return` statement?

#### Category 2: Parameter Passing (`Call by Value` vs. `Call by Reference`)

6.  Explain the core difference between **Call by Value** and **Call by Reference**. Use an analogy to make your explanation clear.
7.  You write a function `void swap(int x, int y)` to swap two numbers. Why does this function fail to change the original values in `main()`?
8.  How do you **achieve** Call by Reference in C? What two operators are essential for this?
9.  When you pass an **array** to a function, is it effectively passed by value or by reference? Explain the consequence of this behavior.
10. A function can only `return` one value. Describe a technique using pointers that allows a function to effectively "return" multiple results to the caller.

#### Category 3: Pointers and Memory

11. What is a pointer? What does it store, and what is the difference between the value *of* a pointer and the value it *points to*?
12. What do the `&` (address-of) and `*` (dereference) operators do? Given `int x = 10; int *p = &x;`, what are the values of `x`, `p`, and `*p`?
13. What is a `NULL` pointer, and why is it important to use it?
14. Explain what "pointer arithmetic" is. If `p` is an integer pointer holding address `2000` and you execute `p++`, what will the new value of `p` be (assuming an `int` is 4 bytes)?
15. What is a "dangling pointer"? How might one be created?

#### Category 4: Pre-processor and Macros

16. What is the C Pre-processor, and at what stage of the compilation process does it run?
17. Explain the difference between including a header file with angle brackets (`#include <stdio.h>`) versus double quotes (`#include "myheader.h"`).
18. You define a macro `#define SQUARE(x) x * x`. What is the potential problem with `SQUARE(a + b)`? How should the macro be correctly defined to avoid this issue?
19. What is the purpose of an "include guard" (`#ifndef`, `#define`, `#endif`) in a header file?
20. What is the difference between a function-like macro and a true function? Give one advantage of using a macro and one advantage of using a function.

#### Category 5: Practical Application and Recursion

21. What is **recursion**? What are the two essential components that every recursive function must have to avoid an infinite loop?
22. You need to write a function that calculates the factorial of a number. Would you choose an iterative (loop-based) solution or a recursive solution? Justify your choice by giving one pro and one con for each approach.
23. Describe how you would create and use your own custom header file (`my_math.h`) that contains the prototype for a function you wrote called `add()`.
24. You are given a function `void process_data(int *data)`. Inside this function, what is the difference between `data++` and `(*data)++`?
25. After completing this course, what do you believe is the single most important reason for structuring programs using functions?

---
