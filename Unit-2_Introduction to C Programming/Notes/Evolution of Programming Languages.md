### Notes: Evolution of Programming Languages (Unit 2 - Part B)

#### 1. What is a Programming Language?

A programming language is a **formal language** designed to communicate instructions to a machine, particularly a computer. It provides a structured way for humans to write programs that control the behavior and output of a computer.

Think of it as a specialized language that acts as a bridge between human logic and the computer's electronic circuits. Examples range from very basic languages like Assembly to highly advanced ones like Python and Java.

#### 2. The Hierarchy of Programming Languages

Programming languages are broadly classified into two main categories based on their level of **abstraction**. Abstraction refers to how far removed the language is from the computer's hardware.

*   **Low-Level Languages:** Have very little abstraction and are very close to the hardware. They are machine-oriented.
*   **High-Level Languages:** Have a high degree of abstraction and are designed to be easily understood by humans. They are programmer-oriented.

This hierarchy is often described in terms of "generations" (G).

#### 3. Low-Level Languages

Low-level languages provide direct control over the computer's hardware (like the CPU and memory) but are very difficult for humans to write and understand.

**A. First Generation Language (1GL): Machine Language**
*   **Era:** 1940s
*   **Description:** This is the computer's native language, consisting purely of binary digits (**0s and 1s**). Each instruction is a sequence of bits that the CPU can understand and execute directly.
*   **Readability:** Unreadable for humans.
*   **Portability:** **None.** Machine language is entirely hardware-specific. Code written for one type of CPU will not work on another.
*   **Translation Needed:** **None.** The CPU executes it directly.
*   **Example:** `10110101 00101100`

**B. Second Generation Language (2GL): Assembly Language**
*   **Era:** 1949 onwards
*   **Description:** Assembly language is a step up from machine language. It replaces the binary sequences with human-readable symbolic codes called **mnemonics** (e.g., `MOV` for move, `ADD` for add, `SUB` for subtract).
*   **Readability:** Readable by programmers, but still very cryptic.
*   **Portability:** **Limited.** It is CPU-specific. Code written for an x86 processor won't work on an ARM processor.
*   **Translation Needed:** Yes. An **Assembler** is required to translate the assembly code into machine code.
*   **Uses:** Embedded systems, device drivers, and OS kernels where direct hardware control and maximum performance are critical.
*   **Example:** `MOV AX, BX` (Move the value from register BX to register AX).

#### 4. High-Level Languages

High-level languages were created to make programming simpler, faster, and more portable. They use English-like syntax and mathematical notations, making them much easier to learn and use.

**A. Third Generation Languages (3GL)**
*   **Era:** 1957 onwards
*   **Description:** These are the first languages that are truly programmer-friendly. They are procedural or object-oriented and require a **compiler** or **interpreter** to be translated into machine code.
*   **Readability:** Highly readable and much closer to English.
*   **Portability:** **High.** They are platform-independent. The same C or Java code can be compiled to run on different types of machines.
*   **Key Feature:** They provide a high level of abstraction, hiding the complex details of the hardware from the programmer.
*   **Examples:** **FORTRAN** (for science/math), **COBOL** (for business), **C** (for system programming), **C++**, **Java**, **Python**.

**B. Fourth Generation Languages (4GL)**
*   **Era:** 1970s onwards
*   **Description:** These languages are designed to be even closer to human language than 3GLs. They are often used for specific purposes like database management and report generation.
*   **Key Feature:** They require significantly fewer lines of code to achieve a result compared to a 3GL. A single 4GL statement can replace many lines of 3GL code.
*   **Examples:** **SQL** (for database queries), **MATLAB** (for mathematical analysis), **SAS** (for statistics).

**C. Fifth Generation Languages (5GL)**
*   **Era:** 1980s onwards
*   **Description:** These are the most abstract languages, primarily used in the field of Artificial Intelligence and logic programming. The programmer specifies the **constraints** and **conditions** of the problem, and the language/compiler figures out how to solve it.
*   **Key Feature:** The focus is on solving a problem "without the programmer" having to specify the step-by-step algorithm.
*   **Examples:** **Prolog**, **Mercury**. Modern applications include AI tools and chatbots.

#### 5. Translators: Compiler vs. Interpreter vs. Assembler

Since computers can only understand machine code, we need special programs called **translators** to convert our source code into executable binary.

| Feature | Compiler | Interpreter | Assembler |
| :--- | :--- | :--- | :--- |
| **Input** | High-level language source code (e.g., a `.c` file). | High-level language source code. | Assembly language source code. |
| **Output** | Machine code (executable file, e.g., `.exe`). | None (executes directly). | Machine code (object file). |
| **Translation**| Translates the **entire program at once** before execution. | Translates and executes **one line at a time**. | Translates the entire assembly file at once. |
| **Speed**| **Fast** execution, because translation is already done. | **Slower** execution, because translation happens at runtime. | **Fast** execution (very close to hardware). |
| **Error Checking**| Reports all errors after compiling the whole program. | Stops at the first error it finds. | Reports errors after assembling. |
| **Examples**| C, C++, FORTRAN | Python, JavaScript, Ruby | NASM, MASM |

**The Process for C:** When you write a C program, you use a **compiler** (like GCC) to translate your human-readable `.c` file into a machine-readable executable file that the CPU can then run.