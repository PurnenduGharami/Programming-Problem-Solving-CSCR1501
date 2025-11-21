### Notes: Execution Sequence (Jump Statements) in C (Unit 3 - Part C)

#### 1. What are Jump Statements?

In C, the program flow is typically sequential (line by line) or controlled by loops and conditional branches. **Jump Statements** are special statements that unconditionally transfer the program's control from one point in the code to another.

They break the normal flow of execution. C has three primary jump statements:
1.  **`break`**
2.  **`continue`**
3.  **`goto`**

#### 2. The `break` Statement

The `break` statement immediately **terminates** the execution of the nearest enclosing loop (`for`, `while`, `do-while`) or `switch` statement. Control is then transferred to the very first statement following the terminated block.

*   **Purpose:** To exit a loop or `switch` block prematurely, before its normal termination condition is met.
*   **Common Use:** It is almost always used inside an `if` statement to exit based on a specific condition.

**A. Using `break` in a `switch` Statement**
*   **Role:** In a `switch` block, `break` prevents "fall-through." Without it, after a matching `case` is executed, the program would continue to execute all subsequent `case` blocks until a `break` or the end of the `switch` is reached.
*   **Example:**
    ```c
    switch (choice) {
        case 'A':
            printf("You chose option A.\n");
            break; // Exits the switch block here.
        case 'B':
            printf("You chose option B.\n");
            break; // Without this, if choice was 'A', this would also print.
        default:
            printf("Invalid choice.\n");
    }
    // Control jumps here after a break.
    ```

**B. Using `break` in a Loop**
*   **Role:** To exit a loop immediately, regardless of the loop's continuation condition.
*   **Example:** A loop to find a number, which should stop as soon as the number is found.
    ```c
    #include <stdio.h>
    int main() {
        int i;
        for (i = 1; i <= 10; i++) {
            if (i == 5) {
                printf("Found 5! Exiting the loop.\n");
                break; // The loop terminates immediately.
            }
            printf("%d ", i);
        }
        // Output: 1 2 3 4 Found 5! Exiting the loop.
        return 0;
    }
    ```

#### 3. The `continue` Statement

The `continue` statement is used exclusively inside loops. It **skips the remaining statements in the current iteration** and immediately proceeds to the next iteration of the loop.

*   **Purpose:** To bypass a part of the loop's body for a specific iteration without terminating the entire loop.
*   **`break` vs. `continue`:**
    *   `break` **exits** the loop entirely.
    *   `continue` **skips** one iteration and stays in the loop.

*   **How it Works in Different Loops:**
    *   In a **`for` loop**, `continue` jumps to the *update expression* (`i++`).
    *   In a **`while`** or **`do-while` loop**, `continue` jumps to the *condition test*.

*   **Flowchart:**
    ```mermaid
    graph TD
        A(Start Iteration) --> B{Is continue condition met?};
        B -- Yes --> C(Jump to next iteration);
        B -- No --> D[Execute rest of loop body];
        D --> C;
    ```
*   **Example:** Print numbers from 1 to 10, but skip the number 5.
    ```c
    #include <stdio.h>
    int main() {
        int i;
        for (i = 1; i <= 10; i++) {
            if (i == 5) {
                continue; // Skip the rest of this iteration.
            }
            printf("%d ", i); // This line is skipped when i is 5.
        }
        // Output: 1 2 3 4 6 7 8 9 10 
        return 0;
    }
    ```
    **Warning:** Be careful when using `continue` in `while` loops. Ensure your update statement is not skipped, as this can easily cause an infinite loop.

#### 4. The `goto` Statement

The `goto` statement provides an unconditional jump from the `goto` to a labeled statement somewhere within the same function.

*   **Purpose:** To transfer program control to any arbitrary point.
*   **Syntax:**
    ```c
    // ... code ...
    goto my_label; // Jump command
    // ... more code (this part might be skipped) ...

    my_label: // A label is an identifier followed by a colon
    // ... code to be executed after the jump ...
    ```

**IMPORTANT NOTE: The Use of `goto` is Highly Discouraged**

While it is part of the C language, using `goto` is considered extremely poor programming practice in modern software development for several reasons:
*   **Creates "Spaghetti Code":** The program flow jumps all over the place, making the logic incredibly difficult to follow, like trying to untangle a bowl of spaghetti.
*   **Unstructured:** It breaks the structured programming principles that loops and `if-else` statements enforce.
*   **Hard to Debug:** When a program has a bug, tracing the flow of execution becomes a nightmare if `goto` is used.
*   **Better Alternatives Exist:** Almost every problem that can be solved with a `goto` can be solved more cleanly and logically using `if`, `switch`, loops, `break`, `continue`, or functions.

It is included in the syllabus for historical context and completeness, but you should **avoid using it in your programs.**

*   **Example (for educational purposes only):** Demonstrate jumping back to repeat input if a negative number is entered.
    ```c
    #include <stdio.h>
    int main() {
        int num;

    input_label: // Define the label
        printf("Enter a positive number: ");
        scanf("%d", &num);

        if (num < 0) {
            printf("Invalid input. Please try again.\n");
            goto input_label; // Jump back to the label
        }

        printf("You entered: %d\n", num);
        return 0;
    }
    // Note: This exact logic is better implemented with a do-while loop.
    ```

#### 5. Comparison: `break` vs. `continue`

| Feature | `break` Statement | `continue` Statement |
| :--- | :--- | :--- |
| **Purpose** | To **exit** the current loop or `switch` block. | To **skip** the current iteration of a loop. |
| **Effect** | Terminates the entire loop prematurely. | Terminates only the current iteration. |
| **Control Flow**| Jumps to the statement immediately *after* the loop. | Jumps to the *next iteration* of the loop. |
| **Applicability**| Used within loops (`for`, `while`, `do-while`) and `switch` statements. | Used only within loops. |
| **Typical Use Case**| Stop a search once an item is found. Exit a menu after a choice is made. | Skip processing for an invalid data point but continue with the rest. |
| **Example (`i == 5`)**| Loop stops at 5. Output: `1 2 3 4` | Loop skips 5. Output: `1 2 3 4 6 7...` |