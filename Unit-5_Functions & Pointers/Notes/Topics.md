### Unit 5: Detailed Topic List

The unit is officially titled **"Functions"**. It covers how to create and use your own functions, the different ways to pass data to them, and an introduction to advanced concepts like pointers and pre-processors.

#### A) Functions: The Building Blocks of Modular Code
This section covers the fundamentals of creating and using functions.

*   **Definition of a Function:**
    *   Understanding a function as a self-contained block of code that performs a specific task.
    *   The benefits: code reusability, modularity (breaking down large problems), and improved readability.
*   **Function Declaration (Prototyping):**
    *   The syntax: `return_type function_name(parameter_list);`
    *   The purpose of a prototype: to inform the compiler about the function's name, its return type, and the types of arguments it expects *before* the function is called. This is crucial for type checking.
*   **Function Definition:**
    *   Writing the actual body of the function, including the header and the statements that perform the task.
    *   `return_type function_name(parameter_list) { // function body }`
*   **Function Calling:**
    *   How to invoke or execute a function from another part of the program (e.g., from `main()` or another function).
*   **Types of Functions:**
    *   **Library Functions:** Pre-defined functions that are part of the C standard library (e.g., `printf()`, `scanf()`, `sqrt()`, `strlen()`). You use them by including the appropriate header file.
    *   **User-Defined Functions:** Functions that you, the programmer, create to perform specific tasks relevant to your program.

#### B) Pointers and Parameter Passing
This is a critical section that introduces pointers and explains how they are used to pass data to functions.

*   **Introduction to Pointers:**
    *   Understanding a pointer as a special variable that stores the **memory address** of another variable.
    *   Declaration: `data_type *pointer_name;`
    *   The `&` (address-of) operator: to get the memory address of a variable.
    *   The `*` (dereference/indirection) operator: to access the value stored at the address held by the pointer.
*   **Parameter Passing Mechanisms:**
    *   **Call by Value:**
        *   The default method in C.
        *   When you pass an argument to a function, a **copy** of the argument's value is made and sent to the function.
        *   **Key Consequence:** Any changes made to the parameter *inside* the function **do not affect** the original argument in the calling function.
    *   **Call by Reference (achieved using pointers):**
        *   Instead of passing a value, you pass the **memory address** (a pointer) of the argument to the function.
        *   The function then uses this address to directly access and modify the original variable.
        *   **Key Consequence:** Changes made to the data pointed to by the parameter *inside* the function **do affect** the original argument.

#### C) Pre-processors
This section covers a special part of the C compilation process that runs *before* the actual compilation.

*   **Pre-processor Directives:**
    *   Commands that begin with a `#` symbol. They are instructions for the pre-processor, not the compiler.
    *   Examples: `#include`, `#define`, `#undef`, `#if`, `#else`, `#endif`.
*   **Types of Pre-processor Directives:**
    *   File Inclusion (`#include`): Used to include the contents of another file (typically a header file like `<stdio.h>`).
    *   Macro Expansion (`#define`): Used to define macros. A macro is a fragment of code that has been given a name. Whenever the name is used, it is replaced by the contents of the macro.
*   **Macros:**
    *   **Object-like Macros:** Simple substitution of a value (e.g., `#define PI 3.14159`).
    *   **Function-like Macros:** Macros that take arguments (e.g., `#define SQUARE(x) (x * x)`).
*   **Pre-processor Operators:**
    *   `#` (Stringizing Operator): Converts a macro parameter into a string literal.
    *   `##` (Token-Pasting Operator): Merges or concatenates two tokens into a single token.
    *   `\` (Backslash): Used to continue a macro definition onto the next line.
*   **Predefined Macros:**
    *   Standard macros defined by the C pre-processor, such as `__DATE__`, `__TIME__`, `__FILE__`, `__LINE__`.

