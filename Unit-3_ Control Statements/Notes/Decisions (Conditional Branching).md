
### Notes: Decisions (Conditional Branching) in C (Unit 3 - Part A)

#### 1. Introduction to Control Statements

By default, a C program executes statements sequentially, one after the other. **Control Statements** are programming constructs that allow you to alter this default flow. They enable your program to make choices, repeat actions, and jump to different parts of the code based on specific conditions.

Conditional statements, also known as **decision control statements**, are the foundation of "smart" programs. They allow the program to evaluate a condition and determine which block of code to execute and which to ignore.

In C, any non-zero value is considered **`true`**, and the value `0` is considered **`false`**.

#### 2. The `if` Statement

The `if` statement is the most basic decision-making construct. It executes a block of code only if a specified condition is true.

*   **Purpose:** To perform an action conditionally.
*   **Syntax:**
    ```c
    if (test_expression) {
        // block of code to be executed if test_expression is true
    }
    ```
*   **How it Works:** The `test_expression` inside the parentheses is evaluated.
    *   If the expression is **true** (evaluates to any non-zero value), the code inside the curly braces `{}` is executed.
    *   If the expression is **false** (evaluates to 0), the code inside the braces is skipped, and the program continues with the statement immediately following the `if` block.
*   **Flowchart:**
    ```mermaid
    graph TD
        A(Start) --> B{Test Expression};
        B -- True --> C[Body of if];
        C --> D(Statement after if);
        B -- False --> D;
    ```
*   **Example:**
    ```c
    // Program to display a message only if a user enters a negative number
    #include <stdio.h>
    int main() {
        int number;
        printf("Enter an integer: ");
        scanf("%d", &number);

        // The test expression is (number < 0)
        if (number < 0) {
            printf("You entered a negative number.\n");
        }

        printf("Execution continues...\n");
        return 0;
    }
    ```

#### 3. The `if-else` Statement

The `if-else` statement provides an alternative path for when the condition is false. It guarantees that one of two blocks of code will be executed.

*   **Purpose:** To choose between two different actions.
*   **Syntax:**
    ```c
    if (test_expression) {
        // block of code to execute if test_expression is true
    } else {
        // block of code to execute if test_expression is false
    }
    ```
*   **Key Rule:** An `else` statement cannot exist on its own; it must always be paired with a preceding `if` statement.
*   **Flowchart:**
    ```mermaid
    graph TD
        A(Start) --> B{Test Expression};
        B -- True --> C[Body of if];
        B -- False --> D[Body of else];
        C --> E(Statement after if-else);
        D --> E;
    ```
*   **Example:**
    ```c
    // Program to check if a number is even or odd
    #include <stdio.h>
    int main() {
        int number;
        printf("Enter an integer: ");
        scanf("%d", &number);

        if (number % 2 == 0) {
            printf("%d is an even integer.\n", number);
        } else {
            printf("%d is an odd integer.\n", number);
        }
        return 0;
    }
    ```

#### 4. The `if-else if-else` Ladder

This structure is used when a choice must be made from more than two possibilities. It tests conditions sequentially until one is found to be true.

*   **Purpose:** To select one block of code from multiple alternatives.
*   **Syntax:**
    ```c
    if (condition1) {
        // executes if condition1 is true
    } else if (condition2) {
        // executes if condition1 is false AND condition2 is true
    } else if (condition3) {
        // executes if both above are false AND condition3 is true
    } else {
        // executes if none of the above conditions are true
    }
    ```
*   **How it Works:** The conditions are checked from top to bottom. As soon as a condition evaluates to true, its corresponding block is executed, and the rest of the ladder is skipped. The final `else` is optional and acts as a "default" case.
*   **Example:**
    ```c
    // Program to relate two integers using =, >, or <
    #include <stdio.h>
    int main() {
        int num1, num2;
        printf("Enter two integers: ");
        scanf("%d %d", &num1, &num2);

        if (num1 == num2) {
            printf("Result: %d = %d\n", num1, num2);
        } else if (num1 > num2) {
            printf("Result: %d > %d\n", num1, num2);
        } else {
            printf("Result: %d < %d\n", num1, num2);
        }
        return 0;
    }
    ```

#### 5. Nested `if-else` Statements

A nested `if-else` is an `if` statement that is the target of another `if` or `else` statement. It is used to test for conditions that are dependent on other conditions.

*   **Purpose:** To handle complex, multi-level decision logic.
*   **Syntax:**
    ```c
    if (condition1) {
        // Executes if condition1 is true
        if (condition2) {
            // Executes if both condition1 AND condition2 are true
        } else {
            // Executes if condition1 is true AND condition2 is false
        }
    } else {
        // Executes if condition1 is false
    }
    ```
*   **Example:** Find the largest of three numbers.
    ```c
    #include <stdio.h>
    int main() {
        int a, b, c;
        printf("Enter three numbers: ");
        scanf("%d %d %d", &a, &b, &c);

        if (a >= b) {
            // We know 'a' is greater than or equal to 'b'
            if (a >= c) {
                // 'a' is also greater than or equal to 'c', so it's the largest
                printf("%d is the largest.\n", a);
            } else {
                // 'a' is not the largest, so 'c' must be
                printf("%d is the largest.\n", c);
            }
        } else {
            // We know 'b' is greater than 'a'
            if (b >= c) {
                // 'b' is also greater than or equal to 'c', so it's the largest
                printf("%d is the largest.\n", b);
            } else {
                // 'b' is not the largest, so 'c' must be
                printf("%d is the largest.\n", c);
            }
        }
        return 0;
    }
    ```

#### 6. The `switch-case` Statement

The `switch` statement is a powerful alternative to a long `if-else if` ladder. It is used to test the value of a single variable against a list of constant values.

*   **Purpose:** To perform a multi-way branch based on the value of an integer or character.
*   **Syntax:**
    ```c
    switch (expression) {
        case constant1:
            // statements
            break;
        case constant2:
            // statements
            break;
        ...
        default:
            // statements
    }
    ```
*   **Crucial Rules:**
    1.  The `expression` inside `switch` must evaluate to an **integer** or a **character**. Floats and strings are not allowed.
    2.  The `case` labels must be **unique constant** values (e.g., `5`, `'A'`, `1+2`). They cannot be variables.
    3.  **`break` is Essential:** The `break` statement terminates the `switch` block. If you omit it, the program will **"fall through"** and continue executing the code in the *next* case block, which is usually unintended.
    4.  **`default` is Optional:** The `default` case executes if the expression's value does not match any of the `case` constants. It's a good practice to always include a `default` case.

*   **Example:** A simple menu-driven program.
    ```c
    #include <stdio.h>
    int main() {
        char op;
        double first, second;
        printf("Enter an operator (+, -, *, /): ");
        scanf("%c", &op);
        printf("Enter two operands: ");
        scanf("%lf %lf", &first, &second);

        switch (op) {
            case '+':
                printf("%.1lf + %.1lf = %.1lf\n", first, second, first + second);
                break;
            case '-':
                printf("%.1lf - %.1lf = %.1lf\n", first, second, first - second);
                break;
            case '*':
                printf("%.1lf * %.1lf = %.1lf\n", first, second, first * second);
                break;
            case '/':
                printf("%.1lf / %.1lf = %.1lf\n", first, second, first / second);
                break;
            default:
                printf("Error! Operator is not correct\n");
        }
        return 0;
    }
    ```

#### 7. Comparison: `if-else` Ladder vs. `switch-case`

| Feature | `if-else` Ladder | `switch-case` Statement |
| :--- | :--- | :--- |
| **Expression** | Can handle complex logical expressions with relational operators (`>`, `<`, `&&`, `||`). | Can only test for **equality** against a single integer or character expression. |
| **Data Types** | Can evaluate any expression that results in a true (non-zero) or false (0) value. | Limited to integer and character data types. |
| **Speed** | Can be slower if there are many conditions, as each one is checked sequentially. | Often faster because the compiler can optimize it into a direct jump table. |
| **Readability**| Can become complex and hard to read with many nested `else if` blocks. | Cleaner and easier to read when checking a variable against a set of discrete values. |
| **Use Case**| Best for **range-based** conditions or complex logical checks. | Best for **value-based** conditions or menu-driven programs. |