### Unit 2: Practice Answers & Review

#### Category 1: Foundational Concepts

**1. Why Binary?**
*   **Your Answer:** A number system consisting of 0s and 1s. Computers can only understand 0 and 1 (or in other words, "on" and "off"). Using this number system, we can code transistors to be in different states to signal the computer what to do. However, our base-10 number system is not something we can implement directly in computer hardware.
*   **Revised Answer:** Computers are built from electronic circuits and transistors, which can only exist in two physical states: a high voltage state ("on") or a low voltage state ("off"). The binary system, with its two digits `1` and `0`, is a perfect mathematical representation of these two states. It provides a direct way to control the computer's hardware, whereas the ten distinct states required for our decimal system are not practically implementable in digital circuits.
*   **Review:** **Excellent.** Your answer is conceptually perfect. You correctly identified the "on/off" nature of transistors as the reason. The revised answer just phrases it in slightly more technical terms.

**2. Decimal to Binary: `45`**
*   **Your Answer:** `101101`
*   **Revised Answer:** The conversion steps are:
    *   45 / 2 = 22 remainder 1
    *   22 / 2 = 11 remainder 0
    *   11 / 2 = 5 remainder 1
    *   5 / 2 = 2 remainder 1
    *   2 / 2 = 1 remainder 0
    *   1 / 2 = 0 remainder 1
    Reading the remainders from bottom to top gives `101101`. To represent this as an 8-bit number (a standard byte), we pad it with leading zeros: **`00101101`**.
*   **Review:** **Perfect calculation.** Your conversion is absolutely correct. The only minor point is that the question asked for the "8-bit" equivalent, which involves padding the front with zeros.

**3. Binary to Decimal: `10110010`**
*   **Your Answer:** 178
*   **Revised Answer:** The decimal equivalent is calculated by summing the products of each bit and its positional power of 2:
    (1 * 2⁷) + (0 * 2⁶) + (1 * 2⁵) + (1 * 2⁴) + (0 * 2³) + (0 * 2²) + (1 * 2¹) + (0 * 2⁰)
    = 128 + 0 + 32 + 16 + 0 + 0 + 2 + 0 = **178**.
*   **Review:** **Correct.** Your answer is perfect. The revised answer simply shows the steps, which is good practice for notes.

**4. Binary to Octal & Hexadecimal: `111010110`**
*   **Your Answer:** 726
*   **Revised Answer:**
    *   **To Octal (group by 3s):** `111 010 110` → `7 2 6`. Result: **`726₈`**
    *   **To Hexadecimal (group by 4s):** First, pad to a multiple of 4 bits: `0001 1101 0110`. Then convert: `0001` → `1`, `1101` → `D`, `0110` → `6`. Result: **`1D6₁₆`**
*   **Review:** **Partially Correct.** Your octal conversion (`726`) is perfect. However, you missed the hexadecimal part of the question. Remember to group by 4s for hex.

**5. High-Level vs. Low-Level:**
*   **Your Answer:** If fast execution is needed, use a low-level language. If the goal is to make code easy to maintain, share with other developers, and improve, then use a high-level language.
*   **Revised Answer:** The key difference is the level of **abstraction**. Low-level languages (like Assembly) provide little abstraction from the hardware, offering direct control and high performance at the cost of being difficult to write and non-portable. High-level languages (like C) provide high abstraction, making them easier to read, write, and maintain, and they are portable across different computer architectures.
*   **Review:** **Excellent practical answer.** You nailed the primary trade-offs (speed vs. developer-friendliness). The revised answer adds the core vocabulary word: "abstraction."

**6. Compiler vs. Interpreter:**
*   **Your Answer:** A compiler first compiles the whole file into a single executable file and then executes it. An interpreter executes the code line by line; for this reason, it is slower.
*   **Revised Answer:** A **compiler** translates the entire source code into a machine-code executable file in a single step, before execution. This results in faster runtime performance. An **interpreter** translates and executes the source code line by line at runtime. This makes the execution slower but can offer more flexibility. C uses a **compiler**.
*   **Review:** **Perfect.** Your understanding is clear and correct.

#### Category 2: C Language Basics

**7. Invalid Identifiers:**
*   **Your Answer:** `1st_place`: Invalid because the first character cannot be a number. `float`: Invalid variable name because we cannot use keywords.
*   **Revised Answer:**
    *   `1st_place`: Invalid. An identifier cannot begin with a digit.
    *   `my-name`: Invalid. The hyphen (`-`) is not an allowed character in identifiers.
    *   `float`: Invalid. It is a reserved keyword in C.
*   **Review:** **Good, but incomplete.** You correctly identified two invalid names and the reasons why. You missed `my-name`; the hyphen is a subtraction operator and isn't allowed.

**8. Data Types:**
*   **Your Answer:** We use `float` because it represents a fractional value.
*   **Review:** **Perfect.** `float` (or `double` for more precision) is the correct choice.

**9. `const` vs. `#define`:**
*   **Your Answer:** We can change the value of a variable at runtime, but we cannot change the value of a constant.
*   **Revised Answer:** A `#define` is a preprocessor directive that performs a simple text-substitution before the code is compiled. A `const` is a type-checked variable whose value cannot be changed after initialization. `const` is generally preferred in modern C as it is understood by the compiler, providing better type safety and debugging information.
*   **Review:** Your answer describes the difference between a variable and a constant, but not the difference between the two *ways* of creating a constant. This is a subtle but important distinction.

**10. Garbage Value:**
*   **Your Answer:** If we don't give any value to an integer and try to print it, it picks up a random value from memory and prints it. This is called a garbage value. *Example:* `int i; printf("%d", i);`
*   **Review:** **Perfect.** Your explanation and example are exactly right.

**11. The Address Operator (`&`):**
*   **Your Answer:** We use `&` to give the address of the variable so the `scanf` function can access it and write to it. If we forget to mention it, the user input will not be updated in the variable.
*   **Revised Answer:** The `&` is the "address-of" operator. `scanf` needs to know the memory **address** of the variable to store the input value there directly. If you forget the `&`, you pass the variable's *current value* (likely garbage) instead of its address. This causes undefined behavior, which often results in the program crashing.
*   **Review:** **Excellent.** Your understanding is correct. The revised answer just adds the technical term "undefined behavior" and clarifies the consequence (a crash).

**12. Tokens:**
*   **Your Answer:** 7
*   **Revised Answer:** The statement `printf("Total = %d\n", total);` has **7** tokens: `printf`, `(`, `"Total = %d\n"`, `,`, `total`, `)`, `;`.
*   **Review:** **Perfect.**

#### Category 3: Operators and Expressions

*   **13. `14`:** **Correct.**
*   **14. `3, 2`:** **Correct.** Your answer should be "Quotient: 3, Remainder: 2".
*   **15. `10, 10, 11`:** **Incorrect.** The correct output is `10, 11, 12`.
    *   `printf("%d, ", i++);` prints the current value of `i` (10), and *then* increments `i` to 11.
    *   `printf("%d, ", i);` prints the new value of `i` (11).
    *   `printf("%d", ++i);` first increments `i` to 12, and *then* prints the new value.
*   **16. `1`:** **Correct.**
*   **17. `20`:** **Correct.**
*   **18. `1000`:** **Incorrect.** You've given the binary result. The question asks for the decimal result.
    *   12 in binary is `1100`.
    *   10 in binary is `1010`.
    *   `1100 & 1010` = `1000`.
    *   The binary number `1000` converted to decimal is **`8`**.

#### Category 4: Write Full C Programs

**General Feedback on Code:**
*   **Standard `main`:** It's standard practice to declare `main` as `int main(void)` and end it with `return 0;`. While `void main()` might compile on some old compilers, it's not standard C.
*   **User Prompts:** It's good practice to print a prompt (e.g., `printf("Enter a number: ");`) before a `scanf` call, so the user knows what to do.

**19. Area Calculation Code:**

```c
    #include <stdio.h>
    void main(){
        int a, b;
        scanf("%d%d", &a, &b);
        printf("Area: %d", a * b);
    }
```
*   **Review:** **Correct Logic.** The code works. Adding prompts and using `int main()` would make it better.

**20. Temperature Conversion Code:**
    
```c
    #include <stdio.h>
    void main(){
        int c;
        scanf("%d", &c);
        printf("F = %d", (c * 9 / 5) + 32);
    }
```
*   **Review:** **Incorrect Logic (Major Bug).** This is a very common and important mistake.
    1.  **Data Type:** Temperature should be a `float` or `double` to handle decimal values.
    2.  **Integer Division:** In the expression `(c * 9 / 5)`, because `9` and `5` are integers, the result of `9 / 5` will be `1` (the decimal part is truncated). You must use floating-point numbers in the calculation, like `(c * 9.0 / 5.0)`, to get the correct result.
    3.  **Format Specifier:** You used `%d`, which is for integers. You need `%f` for a float.

**21. Even or Odd Checker Code:**
 ```c
    #include <stdio.h>
    void main(){
        int c;
        scanf("%d", &c);
        if(c % 2 == 0)
            printf("EVEN!");
        else
            printf("ODD!");
    }
```

*   **Review:** **Correct Logic.** The code is perfectly functional.

**22. Swapping Variables Code:**
```c
    #include <stdio.h>
    void main(){
        int a = 10, b = 20;
        a = a + b;
        b = a - b;
        a = a - b;
        printf("%d %d", a, b);
    }
```
*   **Review:** **Correct Logic.** This is a clever and correct way to swap two numbers without a temporary variable. Excellent.

**23. Print ASCII Value Code:**
```c
    #include <stdio.h>
    void main(){
        char c;
        printf("Enter a Char: ");
        scanf("%c", &c);
        printf("%d", c);
    }
```
*   **Review:** **Correct Logic.** This code works perfectly. The use of `%d` with a `char` variable to print its ASCII value is correct.