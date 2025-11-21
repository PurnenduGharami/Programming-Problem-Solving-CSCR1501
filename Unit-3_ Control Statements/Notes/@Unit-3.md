# **Unit 3: Control Statements - Master Notes**

## **1. Introduction to Control Flow**

Control flow determines the order in which instructions are executed. By default, C programs execute sequentially (line by line). Control statements allow you to divert this flow in two ways:

  * **Branching (Decision Making):** Choosing a path based on a condition (e.g., `if`, `switch`).
  * **Looping (Iteration):** Repeating a block of code until a condition is met (e.g., `for`, `while`).

-----

## **2. Decision Control Statements (Branching)**

These statements evaluate a condition (Expression). If the condition is **True (non-zero)**, a specific block runs; if **False (0)**, it is skipped.

### **A. The `if` Family**

1.  **Simple `if` Statement:**

      * Executes a block only if the condition is true.
      * *Syntax:* `if (condition) { // code }`

2.  **`if-else` Statement:**

      * Executes one block if true, and a different block if false.
      * *Syntax:*
        ```c
        if (condition) {
            // True block
        } else {
            // False block
        }
        ```

3.  **Nested `if-else`:**

      * An `if` statement inside another `if` statement.
      * Used for complex logic like finding the largest of three numbers.

4.  **`else-if` Ladder:**

      * Used to check multiple conditions sequentially.
      * *Example:* Calculating grades or discounts.
        ```c
        if (marks > 90) grade = 'A';
        else if (marks > 80) grade = 'B';
        else grade = 'C';
        ```

### **B. The `switch-case` Statement**

A multi-way branch statement that tests a variable against a list of values (cases). It is an alternative to a long `else-if` ladder.

  * **Syntax:**
    ```c
    switch (expression) {
        case constant1:
            // code
            break;
        case constant2:
            // code
            break;
        default:
            // code if no case matches
    }
    ```
  * **Key Rules:**
    1.  The expression must evaluate to an **integer** or **character** (No floats or strings).
    2.  **`break`** is optional but recommended. Without it, the program "falls through" and executes the next case automatically.
    3.  **`default`** executes if no cases match.

### **Comparison: `if-else` vs. `switch`**

| Feature | `if-else` | `switch` |
| :--- | :--- | :--- |
| **Expression** | Checks logical/equality expressions ($>, <, ==$). | Checks equality only against constants. |
| **Data Types** | All types (int, float, char). | Only **int** or **char**. |
| **Performance** | Slower for many branches (checks one by one). | Faster (jump table implementation). |
| **Flexibility** | Good for ranges (`x > 10 && x < 20`). | Good for specific menu choices. |

-----

## **3. Iterative Statements (Loops)**

Loops allow you to execute a block of code repeatedly.

### **A. `while` Loop (Entry-Controlled)**

  * Checks the condition **before** entering the loop.
  * If the condition is false initially, the loop body never runs.
  * *Use case:* When the number of iterations is unknown.
  * *Syntax:*
    ```c
    while (condition) {
        // code
        // update counter
    }
    ```

### **B. `do-while` Loop (Exit-Controlled)**

  * Checks the condition **after** executing the loop body.
  * **Guarantee:** The loop runs **at least once**, even if the condition is false.
  * *Use case:* Menu-driven programs where the menu must show at least once.
  * *Syntax:*
    ```c
    do {
        // code
    } while (condition);
    ```

### **C. `for` Loop (Determinate Loop)**

  * Best used when the number of iterations is known.
  * Combines initialization, condition, and update in one line.
  * *Syntax:* `for (initialization; condition; update) { // code }`

*(Note: Standard flowcharts for loops typically show a diamond decision box pointing back to a previous step).*

-----

## **4. Execution Sequence (Jump Statements)**

These statements transfer control unconditionally to another part of the program.

### **A. `break`**

  * **Purpose:** Terminates the loop or switch **immediately**.
  * **Use:** To exit a loop early (e.g., if a search key is found) or to prevent fall-through in switch cases.

### **B. `continue`**

  * **Purpose:** Skips the **current iteration** and jumps to the next iteration.
  * **Use:** To skip specific values (e.g., printing numbers 1-10 but skipping 5).

### **C. `goto`**

  * **Purpose:** Jumps to a labeled part of the code.
  * **Use:** Generally discouraged (spaghetti code), but can be used to break out of deeply nested loops.
  * *Syntax:*
    ```c
    goto label_name;
    ...
    label_name:
    // code
    ```

### **Comparison: `break` vs. `continue`**

| Feature | `break` | `continue` |
| :--- | :--- | :--- |
| **Action** | Exits the loop completely. | Skips current iteration only. |
| **Control Flow** | Moves to the statement *after* the loop. | Moves to the loop *update/condition*. |

-----

## **5. Common Logic Patterns (From Slides)**

  * **Pattern Printing (Nested Loops):**
      * Outer loop controls **rows**.
      * Inner loop controls **columns** (printing stars or numbers).
  * **Prime Number Check:**
      * Loop from `2` to `num/2`. If `num % i == 0`, it is not prime. `break` immediately.
  * **Sum of Digits:**
      * Use `num % 10` to get the last digit.
      * Use `num / 10` to remove the last digit.
      * Repeat in a `while (num > 0)` loop.

-----
