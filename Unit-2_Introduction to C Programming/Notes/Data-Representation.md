### Notes: Data Representation in Computers (Unit 2 - Part A)

#### 1. The Fundamental Problem: Human vs. Machine Language

At its core, a computer is an electronic device made of circuits. These circuits can only exist in two states: **ON** (representing the number 1) or **OFF** (representing the number 0). This is why the native language of any digital device is **Binary**.

Humans, however, communicate with rich data like text, images, audio, and complex numbers. A computer cannot understand these directly.

**Data Representation** is the process of translating human-readable data into the machine-readable binary format so that it can be stored, processed, and transmitted by electronic circuits.

The three main types of data representation are:
1.  **Bits and Bytes:** The physical units of data.
2.  **Number Systems:** The mathematical method for representing numbers.
3.  **Character Encoding:** The system for representing text.

#### 2. Bits and Bytes: The Building Blocks of Digital Data

*   **Bit (Binary Digit):** The smallest possible unit of data in computing. A single bit can have a value of either **0** or **1**.
*   **Byte:** A group of **8 bits**. The byte is the basic addressable unit of memory. This means that the CPU can retrieve data from memory in chunks of bytes.
*   **Nibble:** A group of **4 bits**, or half a byte.
*   **Word:** A group of bits that a computer's CPU can process at one time. A word can be 16 bits, 32 bits, or 64 bits, depending on the computer's architecture.

**Larger Units of Data:**
Computer storage and memory are measured in larger multiples of bytes. Crucially, in computing, these multiples are based on powers of 2 (specifically 2¹⁰ = 1024), not 1000.

| Unit | Value |
| :--- | :--- |
| 1 Kilobyte (KB) | 1024 Bytes |
| 1 Megabyte (MB)| 1024 Kilobytes |
| 1 Gigabyte (GB)| 1024 Megabytes |
| 1 Terabyte (TB)| 1024 Gigabytes |

#### 3. Number Systems: The Language of Numbers

A number system is a mathematical notation for representing numbers using a set of digits or symbols. The number of unique digits available is called the **base** or **radix** of the system.

**A. Decimal Number System (Base-10)**
This is the system we use in everyday life.
*   **Base:** 10
*   **Digits:** 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
*   **Positional Value:** Each digit's value depends on its position, which is a power of 10. For example, the number **5319** is:
    `(5 * 10³) + (3 * 10²) + (1 * 10¹) + (9 * 10⁰)`

**B. Binary Number System (Base-2)**
This is the system used by all computers.
*   **Base:** 2
*   **Digits:** 0, 1
*   **Positional Value:** Each digit's value is a power of 2.
    *   **LSB (Least Significant Bit):** The rightmost bit.
    *   **MSB (Most Significant Bit):** The leftmost bit.
*   **Example:** The binary number **1101₂** in decimal is:
    `(1 * 2³) + (1 * 2²) + (0 * 2¹) + (1 * 2⁰) = 8 + 4 + 0 + 1 = 13₁₀`

**C. Octal Number System (Base-8)**
Octal is a convenient way to represent long binary numbers more compactly.
*   **Base:** 8
*   **Digits:** 0, 1, 2, 3, 4, 5, 6, 7
*   **Relationship to Binary:** Each octal digit can be represented by exactly **3 binary bits** (since 2³ = 8).

**D. Hexadecimal Number System (Base-16)**
Hexadecimal is the most common way to represent binary data in modern computing (e.g., for memory addresses, color codes like `#FFFFFF`).
*   **Base:** 16
*   **Digits:** 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, **A** (10), **B** (11), **C** (12), **D** (13), **E** (14), **F** (15)
*   **Relationship to Binary:** Each hexadecimal digit can be represented by exactly **4 binary bits** (a nibble), since 2⁴ = 16.

#### 4. Number System Conversions

The ability to convert numbers between these systems is a fundamental skill.

**A. Decimal to Binary Conversion**
*   **For Integers:** Use the **repeated division by 2** method.
    1.  Divide the decimal number by 2.
    2.  Write down the **remainder** (which will be 0 or 1).
    3.  Continue dividing the quotient by 2 until the quotient is 0.
    4.  The binary number is the sequence of remainders read from the **bottom up**.
*   **For Fractions:** Use the **repeated multiplication by 2** method.
    1.  Multiply the fractional part of the decimal number by 2.
    2.  The **integer part** of the result is the first binary digit after the point.
    3.  Repeat the process using only the fractional part of the new number.
    4.  The binary fraction is the sequence of integers read from the **top down**.

**B. Binary to Decimal Conversion**
*   Multiply each binary digit by its corresponding positional value (a power of 2) and add all the results.
*   **Example:** `10110₂ = (1*2⁴) + (0*2³) + (1*2²) + (1*2¹) + (0*2⁰) = 16 + 0 + 4 + 2 + 0 = 22₁₀`

**C. Conversions involving Octal and Hexadecimal**
These systems are useful because they make converting to and from binary incredibly easy.

*   **Binary to Octal:**
    1.  Starting from the right, group the binary bits into sets of **three**.
    2.  Convert each 3-bit group into its corresponding octal digit (0-7).
*   **Octal to Binary:**
    1.  Convert each octal digit into its 3-bit binary equivalent.
*   **Binary to Hexadecimal:**
    1.  Starting from the right, group the binary bits into sets of **four**.
    2.  Convert each 4-bit group into its corresponding hexadecimal digit (0-F).
*   **Hexadecimal to Binary:**
    1.  Convert each hexadecimal digit into its 4-bit binary equivalent.

#### 5. Binary Arithmetic

Computers perform all calculations, even complex ones, using simple binary arithmetic.

*   **Binary Addition:**
    *   `0 + 0 = 0`
    *   `0 + 1 = 1`
    *   `1 + 0 = 1`
    *   `1 + 1 = 0`, carry over 1
*   **Binary Subtraction:**
    *   `0 - 0 = 0`
    *   `1 - 0 = 1`
    *   `1 - 1 = 0`
    *   `0 - 1 = 1`, borrow 1 from the next significant bit
*   **1's and 2's Complement:** Computers often perform subtraction by using a method called **2's complement**. This turns a subtraction problem (`A - B`) into an addition problem (`A + (-B)`).
    *   **1's Complement:** Invert all the bits (0 becomes 1, 1 becomes 0).
    *   **2's Complement:** Find the 1's complement and then add 1. This is the standard way to represent negative numbers in computers.

#### 6. Binary Codes for Character Encoding

*   **ASCII (American Standard Code for Information Interchange):** An early standard that uses 7 or 8 bits to represent the English alphabet, numbers, and common symbols.
*   **Unicode:** A modern standard that uses a variable number of bits (8, 16, or 32) to represent characters from virtually every language in the world. It is a superset of ASCII.