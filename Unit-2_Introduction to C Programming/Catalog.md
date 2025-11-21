# **Unit 2 — Introduction to C Programming (Full Detailed Notes)**

This unit usually covers the foundations of the C language — structure, tokens, variables, data types, operators, input/output, and basic programming structure.

---

# 1) **Introduction to C**

## What is C?

C is a **general-purpose, procedural, middle-level programming language** developed by Dennis Ritchie at Bell Labs (1972).
It is widely used because it is:

* Fast and memory-efficient
* Close to hardware yet portable
* Used to build OS, compilers, embedded systems, device drivers

## Features of C

* **Simple** — small number of keywords
* **Structured** — supports functions and modular code
* **Portable** — C code can run on many machines
* **Efficient** — low-level memory access
* **Extensible** — we can add functions easily
* **Rich library support**

## Structure of a C Program

```
#include <stdio.h>

int main() {
    // variable declarations
    // statements
    return 0;
}
```

**Breakdown:**

| Part                 | Meaning                                                    |
| -------------------- | ---------------------------------------------------------- |
| `#include <stdio.h>` | Preprocessor directive (includes the Standard I/O library) |
| `int main()`         | Entry point of the program                                 |
| `{ ... }`            | Block of code                                              |
| `return 0;`          | Returns control to OS                                      |

---

# 2) **Tokens in C**

Tokens are the smallest individual units of a program.

### Types of Tokens

1. **Keywords**
2. **Identifiers**
3. **Constants**
4. **Strings**
5. **Operators**
6. **Special Symbols**

---

## 2.1 **Keywords**

Reserved words that have pre-defined meaning.
Examples:

```
auto, break, case, char, const, continue, default, do,
double, else, enum, extern, float, for, goto, if, int,
long, register, return, short, signed, sizeof, static,
struct, switch, typedef, union, unsigned, void, volatile, while
```

---

## 2.2 **Identifiers**

Names given to variables, functions, arrays, etc.

### Rules:

* Only letters, digits, and underscore
* Cannot start with a digit
* No spaces
* Case-sensitive
* Keywords cannot be used

Examples:
`myVariable`, `_count`, `totalMarks`

---

## 2.3 **Constants**

### Types:

* **Integer constants** → `10`, `-5`
* **Floating constants** → `3.14`, `2.0E3`
* **Character constants** → `'A'`, `'\n'`
* **String constants** → `"Hello"`
* **Boolean constants** → represented by integers `0` (false), `1` (true)

---

## 2.4 **Special Symbols**

Symbols that have special meaning in C:

```
( ) { } [ ] # ; : " ' ? , .
```

---

# 3) **Variables & Data Types**

## 3.1 Variables

A variable is a named memory location that stores data.

### Syntax:

```
data_type variable_name;
```

Examples:

```
int age;
float salary;
char grade;
```

---

## 3.2 Data Types

### **Primary Data Types**

| Type     | Size         | Range                            |
| -------- | ------------ | -------------------------------- |
| `char`   | 1 byte       | -128 to +127                     |
| `int`    | 2 or 4 bytes | -32,768 to +32,767 OR -2B to +2B |
| `float`  | 4 bytes      | ~6 decimal digits                |
| `double` | 8 bytes      | ~15 decimal digits               |

---

### **Derived Data Types**

* Arrays
* Pointers
* Structures
* Unions
* Functions

---

### **User-defined Data Types**

* `typedef`
* `enum`
* `struct`

---

## 3.3 Variable Declaration vs Initialization

```c
int a;        // declaration
a = 10;       // initialization

int b = 20;   // combined
```

---

# 4) **Operators in C**

Operators are symbols that perform operations on operands.

---

## 4.1 Arithmetic Operators

```
+  -  *  /  %
```

Example:

```
c = a + b;
```

---

## 4.2 Relational Operators

```
== != > < >= <=
```

Used in conditions (returns 0 or 1).

---

## 4.3 Logical Operators

```
&&  ||  !
```

Examples:

* `a > b && b > c`
* `!(a == b)`

---

## 4.4 Assignment Operators

```
=  +=  -=  *=  /=  %=
```

Example:

```
x += 5;    // x = x + 5
```

---

## 4.5 Increment/Decrement

```
++  --
```

Two types:

* pre-increment `++i`
* post-increment `i++`

---

## 4.6 Conditional (Ternary) Operator

```
condition ? value1 : value2
```

---

## 4.7 Bitwise Operators

```
&   |   ^   ~   <<   >>
```

---

## 4.8 Special Operators

* `sizeof`
* comma `,`
* pointer operators: `*` and `&`

---

# 5) **Input and Output (I/O)**

### `printf()` — output

```c
printf("Sum = %d", result);
```

### `scanf()` — input

```c
scanf("%d", &age);
```

### Format specifiers:

| Data Type | Specifier |
| --------- | --------- |
| `int`     | `%d`      |
| `float`   | `%f`      |
| `double`  | `%lf`     |
| `char`    | `%c`      |
| `string`  | `%s`      |

---

# 6) **Basic Structure of a C Program (Step-by-step)**

### Example Program

```c
#include <stdio.h>

int main() {
    int a, b, sum;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    sum = a + b;

    printf("Sum = %d", sum);

    return 0;
}
```

### Execution steps:

1. Program loads
2. `main()` function starts
3. Variables created
4. User inputs values
5. Arithmetic executed
6. Output printed
7. Program returns 0

---

# 7) **Common Errors in C**

| Error Type                    | Example                   |
| ----------------------------- | ------------------------- |
| Missing semicolon             | `printf("Hi")`            |
| Wrong format specifier        | `%f` used for `int`       |
| Using uninitialized variables | `int a; printf("%d", a);` |
| Using `=` instead of `==`     | `if(a = b)`               |


