### Examination: Unit 3 - Control Statements

#### Category 1: Decision-Making (`if` vs. `switch`)

1.  In what specific situations would a `switch` statement be a better choice than an `if-else if` ladder? And when is an `if-else if` ladder the *only* option?
2.  What is "fall-through" in a `switch` statement, and what is the purpose of the `break` keyword in this context?
3.  A common beginner mistake is writing `if (x = 5)` instead of `if (x == 5)`. Explain what each of these statements does in C and why the first one is a logical bug.
4.  Can you use a floating-point variable (like a `float` or `double`) in a `switch` expression? Why or why not?
5.  Explain the "dangling else" problem. If you have a nested `if` without an `else`, how does the compiler know which `if` an `else` keyword belongs to?

#### Category 2: Iteration & Loops (`for`, `while`, `do-while`)

6.  Compare the `while` loop and the `do-while` loop. Give a practical programming example where a `do-while` loop is the more logical choice.
7.  A `for` loop is often called a "determinate" loop. What does this mean, and when is it more suitable than a `while` loop?
8.  What are the three components within the parentheses of a `for` loop? What happens if you omit the update/increment component?
9.  Consider a nested loop where the outer loop runs 5 times and the inner loop runs `i` times (where `i` is the outer loop's counter). How many total iterations will the inner loop's body execute?
10. Can you write a `for` loop that never executes its body? Provide an example.

#### Category 3: Jump Statements (`break`, `continue`, `goto`)

11. Explain the fundamental difference in behavior between the `break` and `continue` statements when used inside a loop.
12. If you use a `break` statement inside the *inner* loop of a nested loop structure, which loop does it exit? The inner loop, the outer loop, or both?
13. You are writing a program to process a list of 100 numbers, but you need to ignore any negative numbers. Which jump statement would be most appropriate for this task, and how would you use it?
14. Modern programming standards strongly discourage the use of `goto`. Why is this? What problems can it introduce into your code?
15. What are the two distinct contexts in which the `break` statement can be used in C?

#### Category 4: Practical Problem-Solving & Logic

16. Imagine you are writing a program for an ATM. The program must ask the user for their PIN and keep asking until they enter the correct one. Which type of loop is best suited for this and why?
17. Verbally walk me through the logic of an `if-else` structure to determine if a given year is a leap year. (A year is a leap year if it is divisible by 4, unless it is divisible by 100 but not by 400).
18. You need to create a program that finds the sum of the first `N` natural numbers. Can this be solved with all three loop types (`for`, `while`, `do-while`)? Which one would be the most straightforward and why?
19. How would you structure a simple menu-driven program that asks the user to choose an operation (e.g., 1 for Addition, 2 for Subtraction)? Which control statement is the most efficient and readable for handling the user's choice?
20. What is an "infinite loop"? Write a simple `for` loop that would run forever.

#### Category 5: Syntax and Common Errors

21. Is it syntactically mandatory to use curly braces `{}` to define the body of an `if` statement or a `for` loop? Explain the rule and the potential risk of not using them.
22. What is the output of `printf("%d", 5 > 3);`? Why?
23. In a `while` loop, what happens if the variable being tested in the condition is never updated within the loop's body?
24. Can the initialization, condition, and update parts of a `for` loop be left empty, like `for(;;)`? If so, what is the result of such a statement?
25. Consider a `while` loop where you use a `continue` statement. Why is the placement of the loop variable's update expression (e.g., `i++`) so critical in this scenario?

---
