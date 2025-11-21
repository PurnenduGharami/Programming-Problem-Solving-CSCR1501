### UNIT 3: VIVA Answers Review

#### Category 1: Decision-Making (`if` vs. `switch`)

**1. `switch` vs. `if-else if`**
*   **Your Answer:** If we have to compare a single variable against different values, it is better to use a `switch` case. If we have to check multiple conditions with different variables, it is better to use `if-else`. Also, if we have the exact value of the variable, it is better to use `switch`, but if our value is not perfectly fixed (like a range) or is a `float` variable, `switch` case is not usable.
*   **Revised Answer:** A `switch` statement is better when you are comparing a **single integer or character variable against a series of discrete constant values**. It is often more readable and can be more efficient. An `if-else if` ladder is the only option when you need to evaluate **complex logical expressions, multiple variables, or check for ranges of values** (e.g., `if (score > 90)`). Additionally, `switch` cannot be used with `float` or `double` types.
*   **Review:** **Perfect.** Your answer is comprehensive and correct, covering all key distinctions.

**2. "Fall-through" and `break`**
*   **Your Answer:** `default` is the fall-through option for a `switch` statement; if no condition matches, it will be used. We use `break` to stop the code of other cases from executing. If we don't add `break`, all the other cases following the match will be executed.
*   **Revised Answer:** **"Fall-through"** is the behavior where, after a matching `case` is executed, the program continues executing the statements of all subsequent `case` blocks. The `break` statement is used to prevent this by immediately terminating the `switch` block and transferring control to the next statement after it. The `default` case is executed only if no other `case` label matches the expression.
*   **Review:** **Good, but a slight mix-up in terminology.** You correctly described fall-through, but `default` isn't the fall-through option itself; it's the catch-all case. The revised answer clarifies this distinction.

**3. `=` vs. `==` in `if` statements**
*   **Your Answer:** If we use a single `=`, it is an assignment operator, meaning it assigns a value to `x`. The other (`==`) is used to check/compare the value.
*   **Revised Answer:** The single equals (`=`) is the **assignment operator**. `if (x = 5)` first assigns the value `5` to `x`, and the expression itself evaluates to `5`. Since `5` is a non-zero value, the `if` condition becomes **always true**. The double equals (`==`) is the **equality operator**, which compares the value of `x` to `5` and evaluates to true (1) or false (0) without changing `x`.
*   **Review:** **Excellent.** Your explanation is correct. The revised version just adds the crucial detail about why `if (x = 5)` becomes a logical bug (it's always true).

**4. `float` in a `switch`?**
*   **Your Answer:** No, because in a `switch` case we need an exact value, but `float` and `double` can have different stored values based on precision.
*   **Revised Answer:** No. The C standard specifies that the controlling expression of a `switch` statement must evaluate to an **integer type** (`int`, `char`, etc.). Floating-point values are disallowed because their internal representation can have precision issues, making exact equality checks unreliable.
*   **Review:** **Perfect.** Your reasoning about precision is exactly right.

**5. "Dangling else" problem**
*   **Your Answer:** No idea.
*   **Revised Answer:** The "dangling else" problem occurs in nested `if` statements. The rule in C is that **an `else` clause always belongs to the nearest preceding `if` statement that does not already have an `else` part**. To avoid ambiguity and force an `else` to pair with an outer `if`, you must use curly braces `{}` to define the scope of the inner `if`.
*   **Review:** This is a classic C interview question. It's a great concept to add to your notes.

#### Category 2: Iteration & Loops

**6. `while` vs. `do-while`**
*   **Your Answer:** If we want to make the loop work once and *then* check the condition, we use a `do-while` loop (as it is an exit-controlled loop). We use `while` if we want to check the condition first. `do-while` is often used for menu-based programs.
*   **Revised Answer:** A `while` loop is an **entry-controlled loop**; it checks the condition *before* executing the body, so it may run zero or more times. A `do-while` loop is an **exit-controlled loop**; it executes the body *before* checking the condition, guaranteeing it runs at least once. This makes it ideal for scenarios like user input validation or displaying a menu, where you need to perform an action first.
*   **Review:** **Perfect.** You correctly identified the core difference and a prime use-case.

**7. `for` loop as a "determinate" loop**
*   **Your Answer:** If we know how many loops are going to happen, it is better to use a `for` loop; for this reason, it is called a determinate loop. If we don't know what the number of iterations will be, it is better to use a `while` loop.
*   **Review:** **Perfect.** This is the exact distinction.

**8. Components of a `for` loop**
*   **Your Answer:** `for(i=0; i>5; i++) {}` — The first part is called initialization, the second part is condition checking, and the last part is iteration updating. If you forget the last part, congratulations, you have created an infinite loop (but sadly, you won't be able to crash your PC as it is powerful enough now).
*   **Revised Answer:** The three components are: **initialization** (executed once at the start), **condition** (checked before each iteration), and **update/increment** (executed after each iteration). If the update expression is omitted, the loop variable is never modified, which will likely result in an infinite loop if the initial condition is true.
*   **Review:** **Excellent.** Your answer is correct, and your humorous note about not crashing modern PCs is a nice touch.

**9. Nested loop iterations**
*   **Your Answer:** 25 times.
*   **Revised Answer:** The inner loop's body will execute a total of `0 + 1 + 2 + 3 + 4 = 10` times. (Assuming `for (i=0; i<5; i++) { for (j=0; j<i; j++) }`). If the inner loop was `for (j=0; j<5; j++)`, then it would be `5 * 5 = 25` times. The question was slightly ambiguous, but your answer is correct for the standard "square" nested loop.
*   **Review:** **Correct for a square.** My question was ambiguous. The revised answer clarifies the two common scenarios. Let's stick with your `25`.

**10. `for` loop that never executes**
*   **Your Answer:** Yes, `for(i=0; i>1; i++) {}`
*   **Review:** **Perfect.** The initial condition `0 > 1` is false, so the body is never entered.

#### Category 3: Jump Statements

**11. `break` vs. `continue`**
*   **Your Answer:** `break` will stop the loop from working entirely and move on to the next block of code after the loop. `continue` will skip *this* iteration and move on to the next one.
*   **Review:** **Perfect.** Clear, concise, and accurate.

**12. `break` in a nested loop**
*   **Your Answer:** Inner loop.
*   **Review:** **Perfect.** It only breaks out of the immediate enclosing loop.

**13. Skipping negative numbers**
*   **Your Answer:** Continue with `for` loop with `if-else` condition.
*   **Revised Answer:** The most appropriate statement is **`continue`**. You would use a `for` loop to iterate through the numbers. Inside the loop, you would have an `if` statement like `if (number < 0) { continue; }`. This would skip the processing for that negative number and move directly to the next iteration.
*   **Review:** **Correct.** Your answer is right. The refined version just adds a little more detail.

**14. Why is `goto` discouraged?**
*   **Your Answer:** It makes code harder to read and can introduce unexpected problems.
*   **Revised Answer:** The `goto` statement is discouraged because it leads to unstructured, "spaghetti code." The program's control flow can jump arbitrarily, making it extremely difficult to read, debug, and maintain. Structured constructs like loops and functions provide a much cleaner and more logical way to control program flow.
*   **Review:** **Correct.**

**15. Two uses for `break`**
*   **Your Answer:** In `for` loops and in `if-else` conditions.
*   **Revised Answer:** The `break` statement is used in two contexts:
    1.  To terminate a **`switch`** case.
    2.  To immediately exit a **loop** (`for`, `while`, or `do-while`).
*   **Review:** **Incorrect.** `break` does *not* apply to `if-else` statements. It only applies to `switch` and loops. This is a very important distinction to remember.

#### Category 4 & 5: Practical Logic and Common Errors

**16. ATM PIN loop:**
*   **Your Answer:** `do-while`, as it will execute at least once and then check for the condition.
*   **Review:** **Perfect.** This is the classic use case for a `do-while` loop.

**17. Leap year logic:**
*   **Your Answer:** First, we will declare an `if` where we check if the year is divisible by 4; then we print "Leap Year." In the `else if`, we check if it is divided by 100 and *not* by 400; if so, we print "Not Leap Year."
*   **Revised Answer:** The logic would be: `if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))`. This single condition correctly captures all the rules.
*   **Review:** Your logic is a bit off. The condition is more complex. The revised answer shows the correct single `if` statement that combines all the rules with logical operators.

**18. Best loop for summing N numbers:**
*   **Your Answer:** It can be solved by all three, but `for` will be best as we know we will need *n* number of iterations.
*   **Review:** **Perfect.** Correct on all points.

**19. Best statement for a menu:**
*   **Your Answer:** `do-while`, as it will first show the menu and then check the conditions.
*   **Revised Answer:** A `do-while` loop is best for repeating the menu until the user chooses to exit. To handle the user's choice, a **`switch` statement** is the most readable and efficient control structure.
*   **Review:** You correctly identified the best loop, but the question was also hinting at the `switch` statement for handling the user's selection.

**20. Infinite loop example:**
*   **Your Answer:** `for(i=0; i<1; i--) {}`
*   **Review:** **Perfect.** The value of `i` will always be less than 1, so the condition is always true.

**21. Curly braces `{}` requirement:**
*   **Your Answer:** No, it is not mandatory. If we don't use them, only the next line of code will be used for the `if-else`. However, if we need to write multiple lines of code after the `if`, then we must use `{}`.
*   **Review:** **Perfect.** This is exactly right and a common source of bugs for beginners.

**22. Output of `printf("%d", 5 > 3);`**
*   **Your Answer:** 1, because it is a conditional statement which can only return 0 or 1.
*   **Review:** **Perfect.** The relational expression `5 > 3` evaluates to true, which is represented by the integer `1` in C.

**23. Variable never updated in `while` loop:**
*   **Your Answer:** Then the loop runs forever and the condition remains true forever.
*   **Review:** **Perfect.**

**24. Empty `for` loop `for(;;)`:**
*   **Your Answer:** No idea.
*   **Revised Answer:** Yes, all three parts can be left empty. A `for(;;)` statement is a standard C idiom for creating an **infinite loop**. It is equivalent to `while(1)`. You must use a `break` statement inside to exit it.
*   **Review:** A great piece of C trivia to add to your notes!

**25. `continue` and the update expression:**
*   **Your Answer:** `continue` tries to move to the next iteration of the loop, but if the variable update is not present (or skipped), it cannot move to the next iteration effectively, which may cause unexpected problems (like an infinite loop).
*   **Review:** **Excellent.** This is a very insightful answer. In a `while` loop, if the `i++` comes *after* the `if-continue` block, `continue` will jump past it, leading to an infinite loop. This is a classic bug. Great job identifying this risk.