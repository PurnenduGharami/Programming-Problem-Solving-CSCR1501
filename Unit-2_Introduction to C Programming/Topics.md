**Unit 2: Introduction to C Programming**.

### Topic List

The unit is officially titled **"Introduction to C Programming"** and is divided into three main parts: the foundational theory of how computers represent data, the history of programming languages, and finally, the basic building blocks of the C language itself.

#### A) Data Representation in Computers
This section covers how computers internally store and manage the information we give them. It's the "language" of the hardware.

*   **Number Systems:**
    *   **Decimal (Base-10):** The number system humans use daily.
    *   **Binary (Base-2):** The fundamental number system used by all digital computers, consisting of only 0s and 1s.
    *   **(Implicitly related) Hexadecimal (Base-16) and Octal (Base-8):** Often used as a more compact way to represent binary numbers.
*   **Number System Conversion:**
    *   The practical skill of converting numbers between different bases (e.g., converting a Decimal number to its Binary equivalent and vice-versa).
*   **Binary Codes:**
    *   How different types of data are represented using binary (e.g., how characters are represented using codes like ASCII).

#### B) Evolution of Programming Languages
This section provides historical context, helping you understand where C fits into the world of programming.

*   **Low-Level Languages:** Languages that are very close to the computer's native hardware instructions.
    *   **Machine Language:** The raw binary code (0s and 1s) that the CPU directly executes.
    *   **Assembly Language:** A more human-readable representation of machine language using mnemonics (e.g., `ADD`, `MOV`).
*   **High-Level Languages:** Languages designed to be easier for humans to read, write, and understand. They abstract away the complex details of the hardware.
    *   C is a primary example, often considered a "middle-level" language because it has features of both. Other examples include C++, Java, Python, etc.

#### C) Introduction to C Programming Language
This is the core practical component of the unit, where you'll learn the fundamental syntax and building blocks of C.

*   **Basic Structure of a C Program:**
    *   Header files (`#include <stdio.h>`)
    *   The `main()` function: the entry point of every C program.
*   **Fundamental Building Blocks:**
    *   **Keywords:** Reserved words with special meaning in C (e.g., `int`, `if`, `else`, `while`).
    *   **Identifiers:** The names you give to variables, functions, etc.
    *   **Variables:** Named memory locations used to store data that can change.
    *   **Constants:** Fixed values that do not change during program execution.
*   **Data Types:** The classification of data that a variable can hold.
    *   Primary types: `int` (integers), `float` (single-precision floating-point numbers), `double` (double-precision), `char` (single characters).
*   **Operators and Expressions:**
    *   **Operators:** Symbols that perform operations on data.
        *   **Arithmetic Operators:** `+`, `-`, `*`, `/`, `%` (modulus).
        *   **Relational Operators:** `==`, `!=`, `>`, `<`, `>=`, `<=`.
        *   **Logical Operators:** `&&` (AND), `||` (OR), `!` (NOT).
        *   (And others like assignment, bitwise, etc.)
    *   **Expressions:** A combination of variables, constants, and operators that the C compiler evaluates to produce a value. For example: `area = length * width;`.
