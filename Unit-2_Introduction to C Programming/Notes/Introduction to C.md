### Notes: Introduction to C Programming Language (Unit 2 - Part C)

#### 1. What is a Program and Why C?

*   **What is a Program?** A program is a set of instructions that tells the computer's hardware what to do. Without a program, a computer is just a collection of useless hardware. A program has two purposes:
    1.  To tell the computer what actions to perform.
    2.  To communicate our intent to other developers.

*   **What is C?** C is a **structured, procedural, middle-level** programming language.
    *   **Developed:** At Bell Laboratories in 1972 by **Dennis Ritchie**.
    *   **Original Purpose:** It was invented to implement the UNIX operating system.
    *   **Key Characteristics:**
        *   **Reliable, Simple, and Easy:** Its syntax is compact and relatively easy to learn.
        *   **Performance:** C is renowned for its speed. Because it is compiled into efficient machine code, it is one of the fastest high-level languages.
        *   **Middle-Level:** It combines the easy-to-use features of a high-level language with the power and hardware control of a low-level language (like Assembly).
    *   **Uses:** System applications (Operating Systems like Windows, Linux), device drivers, compilers, embedded systems, databases, and any application where performance is critical.

#### 2. The Building Blocks of C: From Alphabets to Programs

Learning C is analogous to learning a natural language like English.
*   **English:** Alphabets → Words → Sentences → Paragraphs
*   **C:** Character Set → **Tokens** (Keywords, Identifiers, etc.) → **Instructions/Statements** → **Program**

#### 3. C Character Set

These are the only valid characters and symbols that can be used to write a C program. They are grouped into four categories:
1.  **Letters:** `A-Z` and `a-z`
2.  **Digits:** `0-9`
3.  **Special Characters:** `+ - * / = , . _ ( ) { } [ ] # ? ' " : ; ! ~ & | ^ % $ @` etc.
4.  **White Spaces:** Blank space, newline (`\n`), tab (`\t`), carriage return (`\r`).

#### 4. C Tokens: The Smallest Units of a Program

A **token** is the smallest individual unit in a C program that is meaningful to the compiler. The compiler breaks down the source code into these tokens.

The six types of tokens in C are:

**A. Keywords**
*   **Definition:** Reserved words that have a fixed, predefined meaning in the C language.
*   **Rules:**
    *   There are **32 keywords** in ANSI C (e.g., `int`, `float`, `if`, `else`, `for`, `while`, `return`).
    *   Their meaning cannot be changed.
    *   They must always be written in **lowercase**.

**B. Identifiers**
*   **Definition:** A user-defined name given to an entity like a **variable**, **function**, or **array**.
*   **Rules for Naming:**
    1.  Can only contain letters (`a-z`, `A-Z`), digits (`0-9`), and underscore (`_`).
    2.  The first character **must** be a letter or an underscore. It cannot be a digit.
    3.  Cannot be a keyword.
    4.  No spaces or other special characters are allowed.
    5.  C is case-sensitive (`age` and `Age` are different identifiers).

**C. Constants**
*   **Definition:** Fixed values that do not change during the execution of the program.
*   **Types:**
    *   **Integer Constants:** Whole numbers. Can be decimal (e.g., `123`), octal (prefix `0`, e.g., `0173`), or hexadecimal (prefix `0x`, e.g., `0x7B`).
    *   **Real (Floating-Point) Constants:** Numbers with fractional parts (e.g., `12.34`) or expressed in exponential notation (e.g., `1.234e1`).
    *   **Character Constants:** A single character enclosed in **single quotes** (e.g., `'a'`, `'5'`, `'+'`). Internally, they are stored as their integer ASCII value.
    *   **String Constants:** A sequence of characters enclosed in **double quotes** (e.g., `"Hello, World!"`).

**D. Strings** (Specifically, String Literals)
*   These are string constants, as described above. A sequence of characters in double quotes.

**E. Operators**
*   **Definition:** Symbols that perform specific operations (mathematical, logical, etc.) on data. We will cover these in detail in section 7.

**F. Punctuators (or Separators)**
*   **Definition:** Symbols used to organize the structure of a program.
*   **Examples:** Brackets `[]`, parentheses `()`, braces `{}`, comma `,`, semicolon `;`, colon `:`, etc. The semicolon `;` is crucial as it terminates a C statement.

#### 5. Data Types: Defining the Nature of Data

A **data type** specifies the type of data a variable can hold, which in turn determines the memory size allocated and the operations that can be performed on it.

**A. Primary Data Types**
*   `int`: Used to store whole numbers (integers). Typically 2 or 4 bytes.
*   `char`: Used to store a single character. Always 1 byte.
*   `float`: Used to store single-precision floating-point numbers (numbers with decimal points). Typically 4 bytes.
*   `double`: Used to store double-precision floating-point numbers, offering greater precision than `float`. Typically 8 bytes.
*   `void`: A special-purpose type meaning "no type." Used for functions that return nothing or have no parameters.

**B. Data Type Modifiers**
These keywords modify the properties of the primary data types:
*   `signed` / `unsigned`: Determines if a number can hold negative values (`signed`) or only non-negative values (`unsigned`). `unsigned` doubles the positive range.
*   `short` / `long`: Modifies the size (and range) of the `int` and `double` data types. For example, `long int` can hold a larger range of integers than a plain `int`.

#### 6. Variables and Constants

*   **Variable:** A named location in memory used to store a data value that can be **changed** during program execution.
    *   **Declaration:** `data_type variable_name;` (e.g., `int age;`)
    *   **Initialization:** Assigning a value at the time of declaration. (e.g., `int age = 25;`). Uninitialized variables hold "garbage values."

*   **Constant:** A value that **cannot be changed** during program execution.
    *   **Using the `const` keyword:** Creates a read-only variable. This is the preferred method.
        `const float PI = 3.14159;`
    *   **Using `#define` (Symbolic Constant):** A preprocessor directive.
        `#define PI 3.14159`

#### 7. Operators in C

Operators are the workhorses of C, used to form expressions.

*   **Arithmetic Operators:** `+` (add), `-` (subtract), `*` (multiply), `/` (divide), `%` (modulus/remainder).
*   **Relational Operators:** Used for comparison, result in true (1) or false (0). `==` (equal to), `!=` (not equal to), `>` (greater than), `<` (less than), `>=` (greater than or equal to), `<=` (less than or equal to).
*   **Logical Operators:** Used to combine conditions. `&&` (logical AND), `||` (logical OR), `!` (logical NOT).
*   **Assignment Operators:** Used to assign values. `=` (simple assignment), `+=`, `-=`, `*=`, `/=`, `%=` (compound assignment).
*   **Increment/Decrement Operators:** `++` (increment by 1), `--` (decrement by 1).
    *   **Prefix (`++i`):** Increment first, then use the value.
    *   **Postfix (`i++`):** Use the value first, then increment.
*   **Bitwise Operators:** Perform operations on the individual bits of data. `&` (AND), `|` (OR), `^` (XOR), `~` (NOT), `<<` (left shift), `>>` (right shift).
*   **Conditional (Ternary) Operator:** A shorthand for an `if-else` statement. `condition ? value_if_true : value_if_false;`
*   **`sizeof` Operator:** A special operator that returns the size of a data type or variable in bytes. `sizeof(int);`

#### 8. Operator Precedence and Associativity

*   **Precedence:** The order in which operators in a complex expression are evaluated. For example, `*` and `/` have higher precedence than `+` and `-`. (e.g., `2 + 3 * 4` is `2 + 12 = 14`).
*   **Associativity:** The order in which operators of the *same* precedence are evaluated. Most are **Left-to-Right** (e.g., `100 / 10 * 2` is `(100 / 10) * 2 = 20`). Some are **Right-to-Left**, notably assignment operators (e.g., `a = b = 5` assigns `5` to `b`, then the result of that (`5`) to `a`).

#### 9. Basic Input/Output (I/O) in C

To make programs interactive, we need to get input and display output. This is done using functions from the **Standard I/O Library** (`stdio.h`).

*   **`#include <stdio.h>`:** This preprocessor directive must be included at the top of your file to use I/O functions.

*   **Output: `printf()`**
    *   **Purpose:** To print formatted output to the console.
    *   **Syntax:** `printf("format_string", arg1, arg2, ...);`
    *   **Format String:** Contains plain text and **format specifiers**.
    *   **Format Specifiers:** Placeholders that tell `printf` how to interpret and display the arguments.
        *   `%d` or `%i`: Integer (`int`)
        *   `%f`: Floating-point number (`float`)
        *   `%lf`: Double (`double`)
        *   `%c`: Character (`char`)
        *   `%s`: String

*   **Input: `scanf()`**
    *   **Purpose:** To read formatted input from the keyboard.
    *   **Syntax:** `scanf("format_string", &var1, &var2, ...);`
    *   **Crucial Point:** You must use the **address-of operator (`&`)** before the variable name to tell `scanf` *where in memory* to store the input value.

#### 10. Structure of a C Program & Execution Flow

A C program has a well-defined structure and execution flow.

**A. Structure**
```c
/* Comment Section (Optional) */
#include <stdio.h>    // Preprocessor Directive (Link Section)

/* Global Declarations (Optional) */

int main() {          // The main() function - Entry Point
    
    // Declaration Part (variables, etc.)
    int num1, num2, sum;
    
    // Executable Part (statements)
    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);
    
    sum = num1 + num2;
    
    printf("The sum is %d\n", sum);
    
    return 0;         // Return statement
}
```

**B. Execution Flow (Compilation and Linking)**
1.  **Write Source Code:** You write your code in a text editor and save it as a `.c` file.
2.  **Preprocessor:** The preprocessor (`cpp`) executes directives like `#include` (copying header file contents) and `#define`.
3.  **Compiler:** The compiler (`gcc`) translates the preprocessed code into **Assembly code**, then into **Object code** (`.o` or `.obj` file), which is machine code but not yet fully executable. It checks for **Syntax Errors** at this stage.
4.  **Linker:** The linker combines your object code with the code from any libraries you used (like `stdio.h`) to create a final **Executable file** (`.exe` on Windows, `a.out` on Linux).
5.  **Loader:** When you run the program, the loader loads the executable file from the disk into RAM.
6.  **Execution:** The CPU executes the instructions from RAM one by one. **Logical Errors** (where the program runs but gives the wrong output) become apparent at this stage.