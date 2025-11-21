### Unit 3: Topic List

The unit is officially titled **"Control Statements"**. These are C statements that alter the normal sequential flow of execution in a program. They are categorized into two main types: decision-making (branching) and looping (iteration), with a third category for jumping.

#### A) Decisions (Conditional Branching)
This group of statements allows your program to choose a path of execution based on whether a certain condition is true or false.

*   **`if` Statement:**
    *   The most basic decision-making statement.
    *   It executes a block of code **only if** a given condition is true. If the condition is false, the block is skipped.
*   **`if-else` Statement:**
    *   An extension of the `if` statement.
    *   It specifies two blocks of code: one to be executed if the condition is **true** (the `if` block), and another to be executed if the condition is **false** (the `else` block).
*   **Nested `if-else` Statement:**
    *   Placing an `if` or `if-else` statement inside another `if` or `if-else` statement.
    *   This is used to test for multiple, dependent conditions.
*   **`else if` Ladder:**
    *   A common structure used to choose one option from multiple alternatives.
    *   It consists of a sequence: `if`, followed by any number of `else if` blocks, and an optional final `else` block.
    *   The program checks the conditions from top to bottom and executes the block for the *first* condition that evaluates to true.
*   **`switch` Case Statement:**
    *   A specialized alternative to the `else if` ladder, used specifically for checking the value of a single integer or character variable against a list of constant cases.
    *   It's often cleaner and more efficient than a long `else if` chain for multi-way branching.
    *   Includes the `case`, `break`, and `default` keywords.

#### B) Iterations (Loops)
This group of statements allows your program to execute a block of code repeatedly as long as a certain condition is met.

*   **`while` Loop:**
    *   An **entry-controlled** loop.
    *   The condition is checked **before** the loop body is executed.
    *   If the condition is true, the body executes, and the condition is checked again.
    *   If the initial condition is false, the loop body will not execute even once.
*   **`do-while` Loop:**
    *   An **exit-controlled** loop.
    *   The loop body is executed **first**, and then the condition is checked at the end.
    *   This guarantees that the loop body will be executed **at least once**, regardless of the condition.
*   **`for` Loop:**
    *   A compact and structured **entry-controlled** loop.
    *   It combines three essential parts into a single line:
        1.  **Initialization:** Executed once before the loop begins.
        2.  **Condition:** Checked before each iteration.
        3.  **Increment/Decrement:** Executed at the end of each iteration.
    *   It is most commonly used when the number of iterations is known beforehand.

#### C) Execution Sequence (Jump Statements)
These statements cause an unconditional jump to another part of the code, breaking the normal flow.

*   **`goto` Statement:**
    *   Transfers control to a labeled statement anywhere within the same function.
    *   **Note:** The use of `goto` is heavily discouraged in modern programming because it makes code unstructured, difficult to read, and hard to debug (often leading to "spaghetti code"). It is included in the syllabus for completeness.
*   **`break` Statement:**
    *   Has two main uses:
        1.  To terminate a `switch` case and prevent "fall-through" to the next case.
        2.  To immediately **exit** a loop (`while`, `do-while`, or `for`) before its normal termination condition is met.
*   **`continue` Statement:**
    *   Used inside loops.
    *   It immediately **skips the remainder of the current iteration** and proceeds to the next iteration of the loop.

