### Notes : The C Pre-processor

#### 1. What is the Pre-processor?

Before your C source code is handed over to the compiler, it goes through a preliminary processing step. This step is performed by a separate program called the **C Pre-processor**.

The pre-processor's job is **not** to understand C syntax or logic. It is a powerful but simple **text-processing tool**. It scans your source code for special commands called **pre-processor directives**, which all begin with a hash symbol (`#`), and modifies the source code textually based on these commands.

The output of the pre-processor is a temporary, modified C source file that is then fed to the compiler.

**Analogy:** Imagine you are writing a report. Before you submit it, you tell your assistant (the pre-processor) to perform a few tasks:
*   "Everywhere you see the acronym 'FY', replace it with 'Fiscal Year'." (This is like `#define`).
*   "Take the entire 'Appendix A' document and paste it at the end of my report." (This is like `#include`).
*   "If this is a draft for internal review, include this confidential paragraph." (This is like `#if`).

Your assistant doesn't need to understand the report's content, just how to follow these text-based instructions.

#### 2. Pre-processor Directives

Directives are the commands that the pre-processor looks for.

**A. `#include` - File Inclusion**
This is the most common directive. It tells the pre-processor to find a file and paste its entire contents into the current source file.

*   **Purpose:** To include standard library functions and your own custom code from other files, promoting reusability and organization.
*   **Syntax:**
    1.  `#include <filename.h>`
        *   **Usage:** For standard library header files (e.g., `stdio.h`, `math.h`, `stdlib.h`).
        *   **Search Path:** The angle brackets `< >` tell the pre-processor to look for the file in the standard system directories where all the built-in C libraries are stored.
    2.  `#include "filename.h"`
        *   **Usage:** For header files that you have created yourself as part of your project.
        *   **Search Path:** The double quotes `" "` tell the pre-processor to look for the file in the **current directory** first. If it's not found there, it will then search the standard system directories.

**B. `#define` - Macro Definition**
This directive is used to define a **macro**. A macro is a named piece of text or code. The pre-processor will replace every instance of the macro's name with its defined content.

*   **1. Object-like Macros (Symbolic Constants)**
    *   **Purpose:** To give a symbolic name to a constant value. This makes the code more readable and easier to maintain.
    *   **Syntax:** `#define MACRO_NAME replacement_text`
    *   **Example:**
        ```c
        #define PI 3.14159
        #define MAX_STUDENTS 50
        //...
        float area = PI * r * r;
        int scores[MAX_STUDENTS];
        
        // After pre-processing, the compiler sees:
        // float area = 3.14159 * r * r;
        // int scores[50];
        ```
    *   **Advantage:** If the value of PI needs to be more precise later, you only need to change it in one place (the `#define` line).

*   **2. Function-like Macros**
    *   **Purpose:** To create short, simple "functions" that are expanded directly into the code, avoiding the overhead of a true function call.
    *   **Syntax:** `#define MACRO_NAME(param1, param2) (replacement_expression)`
    *   **Crucial Best Practice:** Always enclose each parameter and the entire replacement expression in parentheses `()` to avoid **operator precedence errors**.
    *   **Example (The Right Way):**
        ```c
        #define SQUARE(x) ((x) * (x))
        
        int result = SQUARE(5); // Becomes: int result = ((5) * (5));
        
        // Why parentheses are vital:
        int y = 4;
        int result2 = SQUARE(y + 1); // Becomes: int result2 = ((y + 1) * (y + 1));
                                     // Correctly calculates (4+1)*(4+1) = 25
        ```
    *   **Example (The Wrong Way):**
        ```c
        #define SQUARE_WRONG(x) x * x
        
        int y = 4;
        int result2 = SQUARE_WRONG(y + 1); // Becomes: int result2 = y + 1 * y + 1;
                                         // Due to precedence, this is 4 + (1*4) + 1 = 9. WRONG!
        ```

**C. `#undef` - Undefining a Macro**
This directive "undefines" a previously defined macro. After this point, the macro name is no longer recognized by the pre-processor. This is used in more advanced scenarios to limit the scope of a macro.

```c
#define DEBUG_MODE 1
// ... some debugging code ...
#undef DEBUG_MODE
```

#### 3. Conditional Compilation Directives

These directives allow you to include or exclude blocks of code from compilation based on certain conditions. This is extremely useful for writing code that needs to behave differently on different operating systems, or for including debugging code that you want to easily turn on or off.

*   **`#if`, `#elif`, `#else`, `#endif`:** Works like a regular `if-else if-else` structure, but at the pre-processing stage.
    ```c
    #define VERSION 2

    #if VERSION == 1
        printf("Running version 1.0\n");
    #elif VERSION == 2
        printf("Running version 2.0\n"); // This line will be included
    #else
        printf("Running an unknown version.\n");
    #endif // The #endif is mandatory
    ```
*   **`#ifdef`, `#ifndef`:** Checks if a macro is **def**ined (`ifdef`) or **n**ot **def**ined (`ifndef`).
    *   **Use Case:** A very common use is to prevent a header file from being included more than once in the same file (which would cause errors). This is called an **include guard**.
    ```c
    // Inside a file named "myheader.h"
    #ifndef MYHEADER_H
    #define MYHEADER_H

    // All the content of the header file goes here...
    struct MyStruct { ... };
    void myFunction(int);

    #endif // MYHEADER_H
    ```

#### 4. Pre-processor Operators

*   **`\` (Continuation):** A backslash at the very end of a line tells the pre-processor that the macro definition continues on the next line.
    ```c
    #define LONG_MACRO "This is a very long string that \
    continues on the next line."
    ```
*   **`#` (Stringizing Operator):** When used inside a function-like macro's replacement list, it converts the macro parameter into a string literal.
    ```c
    #define PRINT_VAR(x) printf(#x " = %d\n", x)
    
    int count = 100;
    PRINT_VAR(count); // Becomes: printf("count" " = %d\n", count);
                      // which the compiler treats as: printf("count = %d\n", count);
    ```
*   **`##` (Token-Pasting Operator):** This operator concatenates (pastes together) two tokens to create a single new token.
    ```c
    #define PASTE(a, b) a##b
    
    int PASTE(my, var) = 10; // Becomes: int myvar = 10;
    ```

#### 5. Predefined Macros

C provides several standard macros that give you information about the compilation process. These are useful for logging and debugging.

*   `__DATE__`: The compilation date as a string literal (e.g., "Nov 21 2025").
*   `__TIME__`: The compilation time as a string literal (e.g., "14:30:00").
*   `__FILE__`: The name of the current source file as a string literal.
*   `__LINE__`: The current line number in the source file as an integer.

```c
#include <stdio.h>
int main() {
    printf("This program was compiled on %s at %s\n", __DATE__, __TIME__);
    printf("Error reported in file %s at line %d\n", __FILE__, __LINE__);
    return 0;
}
```