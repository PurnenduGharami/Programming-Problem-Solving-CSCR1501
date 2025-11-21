### Notes: Iterations (Loops) in C (Unit 3 - Part B)

#### 1. Introduction to Iterative Statements (Loops)

In programming, we often need to execute a block of code repeatedly. For example, you might want to print the numbers from 1 to 100, or process every student's record in a database. Performing these tasks by writing the same code over and over again would be tedious and impractical.

**Iterative Statements**, commonly known as **loops**, are control structures that allow a program to execute a set of instructions repeatedly as long as a specific condition remains true. When the condition becomes false, the loop terminates, and the program continues with the next statement after the loop.

There are three types of loops in the C language:
1.  **`while` loop** (Entry-Controlled)
2.  **`for` loop** (Entry-Controlled)
3.  **`do-while` loop** (Exit-Controlled)

Every loop has three essential components:
*   **Initialization:** A starting value for a counter or a condition variable.
*   **Condition:** An expression that is tested before/after each iteration. The loop continues as long as this is true.
*   **Update (Increment/Decrement):** An operation that modifies the loop variable, allowing it to eventually meet the termination condition. Forgetting this leads to an infinite loop.

#### 2. The `while` Loop

The `while` loop is the most fundamental looping construct. It repeats a block of code as long as a given condition is true.

*   **Type:** **Entry-Controlled Loop**. The condition is checked *before* the body of the loop is executed.
*   **Key Behavior:** If the initial condition is false, the loop body will **not execute even once**.
*   **Best Use Case:** When the number of iterations is **not known in advance**, and the loop needs to continue as long as a condition holds true (e.g., reading data from a file until the end is reached).
*   **Syntax:**
    ```c
    initialization;
    while (test_condition) {
        // Body of the loop
        // Statements to be executed

        update_expression; // Crucial for avoiding an infinite loop
    }
    ```
*   **Flowchart:**
    ```mermaid
    graph TD
        A[Start] --> B[Initialization];
        B --> C{Test Condition};
        C -- True --> D[Body of Loop & Update];
        D --> C;
        C -- False --> E[Statement after Loop];
        E --> F[End];
    ```
*   **Example:** Calculate the sum of the first 20 natural numbers.
    ```c
    #include <stdio.h>
    int main() {
        int i = 1;      // Initialization
        int sum = 0;

        while (i <= 20) { // Condition
            sum = sum + i;
            i = i + 1;  // Update
        }

        printf("Sum of the first 20 numbers = %d\n", sum);
        return 0;
    }
    ```

#### 3. The `do-while` Loop

The `do-while` loop is similar to the `while` loop, but with one critical difference in its structure.

*   **Type:** **Exit-Controlled Loop**. The condition is checked *after* the body of the loop has been executed.
*   **Key Behavior:** This loop guarantees that its body will be executed **at least one time**, regardless of whether the initial condition is true or false.
*   **Best Use Case:** For menu-driven programs where you want to display the menu at least once, or when you need to perform an action first and then check if it needs to be repeated.
*   **Syntax:**
    ```c
    initialization;
    do {
        // Body of the loop
        // Statements to be executed

        update_expression;
    } while (test_condition); // Note the semicolon at the end
    ```
*   **Flowchart:**
    ```mermaid
    graph TD
        A[Start] --> B[Initialization];
        B --> C[Body of Loop & Update];
        C --> D{Test Condition};
        D -- True --> C;
        D -- False --> E[Statement after Loop];
        E --> F[End];
    ```
*   **Example:** A program that asks for a number until the user enters a positive one.
    ```c
    #include <stdio.h>
    int main() {
        int number;

        do {
            printf("Enter a positive number: ");
            scanf("%d", &number);
        } while (number <= 0);

        printf("You entered: %d\n", number);
        return 0;
    }
    ```

#### 4. The `for` Loop

The `for` loop is a more compact and structured loop. It is often preferred when the number of iterations is known beforehand.

*   **Type:** **Entry-Controlled Loop**. The condition is checked before the body executes.
*   **Key Behavior:** It combines initialization, condition, and update into a single, easy-to-read line.
*   **Best Use Case:** When you have a "determinate" or "definite" loop, such as iterating a fixed number of times (e.g., 10 times, `n` times, through an array).
*   **Syntax:**
    ```c
    for (initialization; test_condition; update_expression) {
        // Body of the loop
    }
    ```
    *   **Initialization:** Executed exactly **once** when the loop starts.
    *   **Test Condition:** Checked **before** each iteration. If false, the loop terminates.
    *   **Update Expression:** Executed **at the end** of each iteration.
*   **Flowchart:**
    ```mermaid
    graph TD
        A[Start] --> B[Initialization];
        B --> C{Test Condition};
        C -- True --> D[Body of Loop];
        D --> E[Update Expression];
        E --> C;
        C -- False --> F[Statement after Loop];
        F --> G[End];
    ```
*   **Example:** Print the first 5 natural numbers.
    ```c
    #include <stdio.h>
    int main() {
        int i;
        
        // i=1 is initialization, i<=5 is condition, i++ is update
        for (i = 1; i <= 5; i++) {
            printf("%d\n", i);
        }
        return 0;
    }
    ```

#### 5. Nested Loops

A nested loop is a loop placed inside the body of another loop. The inner loop executes to completion for each single iteration of the outer loop.

*   **Concept:** For every one step of the outer loop, the inner loop takes all of its steps.
*   **Use Case:** Extremely common for working with 2D structures, such as printing patterns, iterating through matrices, or creating multiplication tables.
*   **Example:** Print a 5x5 square of asterisks.
    ```c
    #include <stdio.h>
    int main() {
        int i, j;

        // Outer loop controls the rows
        for (i = 1; i <= 5; i++) {
            
            // Inner loop controls the columns (what is printed in each row)
            for (j = 1; j <= 5; j++) {
                printf("* ");
            }
            
            // After the inner loop completes, move to the next line
            printf("\n");
        }
        return 0;
    }
    ```
    **Output:**
    ```
    * * * * * 
    * * * * * 
    * * * * * 
    * * * * * 
    * * * * * 
    ```

#### 6. Comparison of Loops

| Feature | `while` Loop | `do-while` Loop | `for` Loop |
| :--- | :--- | :--- | :--- |
| **Control Type** | Entry-Controlled | Exit-Controlled | Entry-Controlled |
| **Guaranteed Execution**| No (0 or more times) | Yes (1 or more times) | No (0 or more times) |
| **Syntax** | `while(condition)` | `do { ... } while(condition);` | `for(init; cond; update)` |
| **Best For** | Number of iterations is unknown. | When the body must execute at least once. | Number of iterations is known. |
| **Semicolon**| No semicolon after `while(condition)` | Semicolon is required after `while(condition);` | No semicolon after the `for(...)` part. |