### Unit 2: Practice Questions

#### Category 1: Foundational Concepts (Theory & Conversion)

1.  **Why Binary?** In your own words, explain why computers fundamentally operate on the binary (base-2) system and not the decimal (base-10) system that humans use.
2.  **Number Conversion (Decimal to Binary):** Convert the decimal number `45` into its 8-bit binary equivalent. Show your steps using the division-by-2 method.
3.  **Number Conversion (Binary to Decimal):** Convert the binary number `10110010` into its decimal equivalent. Show your steps.
4.  **Number Conversion (Shortcut):** Convert the binary number `111010110` to its Octal and Hexadecimal equivalents using the grouping method.
5.  **Language Hierarchy:** What is the key difference between a low-level language (like Assembly) and a high-level language (like C)? Why would a developer choose one over the other?
6.  **Translators:** Explain the difference between how a **compiler** and an **interpreter** process source code. Which one does C use?

#### Category 2: C Language Basics & Syntax

7.  **Identifiers:** Identify which of the following are **invalid** C identifiers and explain why:
    *   `_total`
    *   `1st_place`
    *   `my-name`
    *   `float`
    *   `averageScore`
8.  **Data Types:** You need to store the price of an item, which could be ₹49.99. Would you use an `int`, `float`, or `char`? Why?
9.  **Constants:** What is the practical difference between defining a constant using `#define PI 3.14` versus `const float PI = 3.14;`?
10. **Garbage Value:** What is a "garbage value" in the context of a variable? Write a single line of code that would likely print a garbage value.
11. **The `scanf` Ampersand:** What is the purpose of the address-of operator (`&`) in a `scanf` statement? What would likely happen if you forgot to include it (e.g., `scanf("%d", age);`)?
12. **Tokens:** How many tokens are in the following C statement? `printf("Total = %d\n", total);`

#### Category 3: Operators and Expressions (Predict the Output)

For each of the following code snippets, predict the exact output.

13. **Integer Division & Precedence:**
    ```c
    int x = 5 + 10 / 2 * 2 - 1;
    printf("%d", x);
    ```
14. **Modulus Operator:**
    ```c
    int a = 14, b = 4;
    printf("Quotient: %d, Remainder: %d", a / b, a % b);
    ```
15. **Post-increment vs. Pre-increment:**
    ```c
    int i = 10;
    printf("%d, ", i++); // First printf
    printf("%d, ", i);   // Second printf
    printf("%d", ++i);   // Third printf
    ```
16. **Relational and Logical Operators:**
    ```c
    int a = 10, b = 20, c = 10;
    int result = (a == c) && (b > a);
    printf("%d", result); // Note: In C, true is 1, false is 0
    ```
17. **Ternary Operator:**
    ```c
    int x = 10, y = 20;
    int max = (x > y) ? x : y;
    printf("%d", max);
    ```
18. **Bitwise Operators:** What is the decimal result of the bitwise operation `12 & 10`? (Hint: Convert both numbers to binary first).

#### Category 4: Problem Solving (Write Full C Programs)

For each problem below, write a complete, simple C program that solves it.

19. **Area of a Rectangle:** Write a program that asks the user to enter the length and width of a rectangle (as integers), and then calculates and prints its area.
20. **Celsius to Fahrenheit:** Write a program that asks the user for a temperature in Celsius (this can be a decimal value) and converts it to Fahrenheit. The formula is `F = (C * 9/5) + 32`.
21. **Even or Odd:** Write a program that asks the user to enter an integer and then prints whether the number is "Even" or "Odd".
22. **Swap Two Numbers:** Write a program that takes two integer variables, `a` and `b`, assigns them values (e.g., `a=10`, `b=20`), swaps their values **without using a third temporary variable**, and then prints their new values.
23. **ASCII Value:** Write a program that prompts the user to enter a single character and then prints its corresponding ASCII integer value.

---

### Next Steps

1.  **Set Up Your Environment:** If you haven't already, install a C compiler (like GCC) and a code editor (like VS Code or Code::Blocks).
2.  **Code the Solutions:** Create a new folder in your repository named `Unit-2_Introduction-to-C`. For each question in **Category 4**, create a new `.c` file (e.g., `area_of_rectangle.c`) and write the code.
3.  **Compile and Run:** Use your compiler to compile the code and then run the executable to see if your program works as expected.
4.  **Debug:** If you get errors (and you will!), read them carefully. This is a critical part of learning to code. Try to fix them yourself before looking for a solution.
5.  **Document:** For the theory questions (Categories 1-3), create a `Unit-2_Practice_Answers.md` file and write down your answers. This will be an excellent revision tool.