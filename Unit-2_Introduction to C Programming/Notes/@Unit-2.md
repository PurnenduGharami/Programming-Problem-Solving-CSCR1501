# **Unit 2: Introduction to C Programming - Master Notes**

## **1. Evolution of Programming Languages**

A programming language is a set of instructions designed to communicate with computers.

### **A. Language Categories**
1.  **Low-Level Languages:**
    * **Machine Language (1st Generation):**
        * Consists of binary digits (0s and 1s).
        * Directly understood by hardware.
        * **Pros:** Fastest execution, full hardware control.
        * **Cons:** Hard to read/write, machine-dependent.
    * **Assembly Language (2nd Generation):**
        * Uses mnemonics (symbols) like `ADD`, `MOV`, `SUB`.
        * Needs an **Assembler** to convert to machine code.
        * **Pros:** More readable than binary.
        * **Cons:** Still architecture-specific.

2.  **High-Level Languages (3rd Generation onwards):**
    * Uses English-like syntax (e.g., `print`, `if`, `while`).
    * Portable (platform-independent).
    * Needs a **Compiler** or **Interpreter**.
    * **Examples:** C, C++, Java, Python.

### **B. Translators**
| Feature | Compiler | Interpreter | Assembler |
| :--- | :--- | :--- | :--- |
| **Input** | High-Level Code | High-Level Code | Assembly Code |
| **Process** | Translates **whole** program at once | Translates **line-by-line** | Translates assembly mnemonics |
| **Output** | Object Code / Executable | Executes directly | Machine Code |
| **Speed** | Fast execution (once compiled) | Slower execution | Fast |
| **Example** | C, C++ | Python, Ruby | NASM, MASM |

---

## **2. Number Systems & Data Representation**

Computers store data using binary systems. You must know how to convert between them.

### **A. Standard Number Systems**
* **Binary (Base 2):** Digits `0, 1`. Used by computers.
* **Octal (Base 8):** Digits `0-7`.
* **Decimal (Base 10):** Digits `0-9`. Human standard.
* **Hexadecimal (Base 16):** Digits `0-9` and `A-F` (where A=10, B=11... F=15). Used for memory addresses and colors.

### **B. Conversions (Important for Exams)**
1.  **Decimal to Binary/Octal/Hex:**
    * **Method:** Repeated Division. Divide the decimal number by the base (2, 8, or 16) and record the **remainders** from bottom to top.
    * *Example:* $13_{10}$ to Binary $\rightarrow$ $1101_2$.
2.  **Binary/Octal/Hex to Decimal:**
    * **Method:** Positional Weight. Multiply each digit by `Base^Position` and sum them up.
    * *Example:* $1101_2 = 1*2^3 + 1*2^2 + 0*2^1 + 1*2^0 = 8+4+0+1 = 13_{10}$.
3.  **Binary Arithmetic:**
    * **Addition:** $0+0=0$, $0+1=1$, $1+0=1$, $1+1=10$ (0 carry 1).
    * **Subtraction:** $1-1=0$, $1-0=1$, $0-1=1$ (borrow 1).
4.  **Complements (For Negative Numbers):**
    * **1's Complement:** Flip all bits ($0 \rightarrow 1, 1 \rightarrow 0$).
    * **2's Complement:** 1's Complement + 1. (Used by computers to store negative integers).

---

## **3. C Language Basics (Lexical Elements)**

C was developed by **Dennis Ritchie** at Bell Labs in **1972** (originally for UNIX).

### **A. C Character Set & Tokens**
A C program consists of **Tokens** (the smallest meaningful units).
1.  **Keywords:** Reserved words with fixed meanings (e.g., `int`, `if`, `while`, `return`). Must be lowercase. (Total 32 in ANSI C).
2.  **Identifiers:** Names for variables/functions.
    * *Rules:* Must start with letter/underscore. No spaces. Case-sensitive. Cannot use keywords.
3.  **Constants:** Fixed values.
    * *Integer:* `10`, `-5`, `0x2A` (Hex), `012` (Octal).
    * *Real (Float):* `10.5`, `2.5e3`.
    * *Character:* `'A'` (Single quotes). Internally stored as ASCII value (A=65, a=97).
    * *String:* `"Hello"` (Double quotes). Ends with null character `\0`.
4.  **Special Symbols:** `{ }`, `( )`, `;`.

### **B. Data Types**
* **Primary:** `int` (2/4 bytes), `char` (1 byte), `float` (4 bytes), `double` (8 bytes), `void`.
* **Modifiers:** `signed`, `unsigned`, `short`, `long` (e.g., `unsigned int`, `long double`).
* **Derived:** Arrays, Pointers, Structures.

### **C. Variables**
* **Declaration:** `int count;`
* **Initialization:** `int count = 10;`
* **Scope:**
    * *Local:* Inside a function (auto).
    * *Global:* Outside functions (extern).

---

## **4. Operators & Expressions**

Operators perform operations on variables and constants.

### **A. Types of Operators**
1.  **Arithmetic:** `+`, `-`, `*`, `/`, `%` (Modulus - returns remainder).
2.  **Relational:** `==`, `!=`, `>`, `<`, `>=`, `<=`. (Returns 1 for True, 0 for False).
3.  **Logical:** `&&` (AND), `||` (OR), `!` (NOT).
4.  **Assignment:** `=`, `+=`, `-=`, `*=`, etc.
5.  **Increment/Decrement:** `++` (Pre/Post), `--`.
    * *Pre (`++i`):* Change value, then use.
    * *Post (`i++`):* Use value, then change.
6.  **Bitwise:** Operates on bits. `&` (AND), `|` (OR), `^` (XOR), `~` (NOT), `<<` (Left Shift), `>>` (Right Shift).
7.  **Conditional (Ternary):** `Expression ? TrueVal : FalseVal;`
8.  **Sizeof:** `sizeof(int)` returns bytes occupied.

### **B. Precedence & Associativity**
Determines the order of evaluation.
* **Highest:** `()`, `[]`.
* **High:** `*`, `/`, `%`.
* **Low:** `+`, `-`.
* **Lowest:** `=`.
* **Associativity:** Usually Left-to-Right, but Assignment (`=`) is Right-to-Left.

---

## **5. Input / Output (I/O) Functions**

### **A. Formatted I/O (`printf`, `scanf`)**
* **Header:** `#include <stdio.h>`
* **`printf()`:** Outputs data to console.
    * Format Specifiers: `%d` (int), `%f` (float), `%c` (char), `%s` (string).
    * *Example:* `printf("Age: %d", age);`
* **`scanf()`:** Reads input from keyboard.
    * Uses `&` (address of) operator for variables (except strings).
    * *Example:* `scanf("%d", &age);`

### **B. Character I/O**
* **`getchar()`:** Reads a single character.
* **`putchar()`:** Prints a single character.

---

## **6. Control Statements**

### **A. Branching (Decision Making)**
* `if (condition) { ... }`
* `if (condition) { ... } else { ... }`
* `if ... else if ... else`
* `switch (variable) { case 1: ... break; default: ... }`

### **B. Looping (Iteration)**
* `while (condition) { ... }` (Entry controlled).
* `do { ... } while (condition);` (Exit controlled, runs at least once).
* `for (init; condition; update) { ... }`.

### **C. Jump Statements**
* `break`: Exits loop/switch.
* `continue`: Skips current iteration, goes to next.
* `goto`: Jumps to a label (avoid using this).



