### Notes: Algorithms for Problem Solving (Version 2.0)

#### 1. The Mindset Before the Method: How to *Think* Like a Problem Solver

Before we even write a single step of an algorithm, we must adopt a certain way of thinking. Programming is not just about code; it's about applying intellectual skills to solve problems.

**A. Critical Thinking**
This is the skill of **logical and analytical reasoning**. It's the foundation of a good algorithm. In problem-solving, critical thinking involves:
*   **Analyzing the Problem:** Breaking it down into its core components.
*   **Developing an Argument:** Forming a logical plan of action.
*   **Using Evidence:** Ensuring each step in your plan is justified and leads towards the solution.
*   **Drawing Reasoned Conclusions:** Arriving at a correct and efficient solution.

**B. Creative Thinking**
This is the skill of **generating new ideas and looking at a problem from unconventional angles**. It's how we find innovative and efficient solutions. Creative thinking involves:
*   **Seeing Existing Situations in a New Way:** "Is there a simpler way to do this?"
*   **Identifying Alternative Explanations:** "If the lamp doesn't work, what are all the *possible* reasons?"
*   **Making New Links:** Combining different ideas to generate a positive outcome.

An effective problem solver uses both **critical thinking** to build a logical structure and **creative thinking** to ensure that structure is the best one possible.

#### 2. The Formal Problem-Solving Lifecycle

Solving a problem with a computer program follows a structured lifecycle. The algorithm is a critical part of this process, but it doesn't exist in isolation.

1.  **Phase 1: Problem Solving (The Planning Phase)**
    *   **Define the Problem:** Thoroughly understand what you need to achieve. Visualize the situation, identify the core issue, and determine the necessary **inputs** (data you need) and **outputs** (the desired result).
    *   **Design / Develop a Plan:** This is where you **create the algorithm**. You outline the logical, step-by-step instructions required to transform the inputs into the outputs.

2.  **Phase 2: Implementation (The Doing Phase)**
    *   **Execute the Plan:** Translate your algorithm into a specific programming language (like C). This is the act of **coding**.
    *   **Evaluate the Results:** Compile and run your program. Test it thoroughly to ensure it works correctly for all valid inputs and produces the desired output.

#### 3. What is an Algorithm? (The Core Definition)

**Formal Definition:** An algorithm is a **finite, step-by-step, and unambiguous sequence of instructions** created to solve a specific problem or to perform a calculation. It is the logical blueprint that a programmer creates *before* writing any code.

**Analogy:** An algorithm is like a recipe for a computer. It lists the inputs (ingredients), provides a sequence of well-defined steps (instructions), and guarantees a specific output (the finished dish).

#### 4. The Five Essential Properties of a Good Algorithm

For any set of instructions to be a valid algorithm, it must satisfy these five criteria:

1.  **Finiteness:** It must terminate after a finite number of steps. It cannot go on forever.
2.  **Definiteness (No Ambiguity):** Each step must be precise and clearly defined. "Add some sugar" is ambiguous; "Add 1 cup (200g) of sugar" is definite.
3.  **Input:** It must have zero or more well-defined inputs.
4.  **Output:** It must produce one or more well-defined outputs.
5.  **Effectiveness:** Each step must be basic and feasible enough to be carried out, in principle, with just a pencil and paper.

#### 5. Developing an Algorithm: Top-Down Design and Stepwise Refinement

When faced with a complex problem, we don't try to solve it all at once. We use a strategy called **Top-Down Design**.

**Top-Down Design:** The process of starting with a high-level problem and progressively breaking it down into smaller, more manageable sub-problems.

This process of breaking things down is also known as **Stepwise Refinement**.

**Example: The "Making Coffee" Algorithm**

*   **Level 0 (The Main Goal):**
    1.  Boil water.
    2.  Put coffee in a cup.

*   **Level 1 (First Refinement):** We refine "Boil water."
    1.1. Fill the kettle.
    1.2. Switch the kettle on.
    1.3. Wait for it to boil.
    1.4. Switch the kettle off.

*   **Level 2 (Second Refinement):** We refine "Fill the kettle."
    1.1.1. Put the kettle under the tap.
    1.1.2. Turn the tap on.
    1.1.3. Wait until the kettle is full.
    1.1.4. Turn the tap off.

This process continues until every step is simple enough to be a single, effective instruction.

#### 6. Sub-algorithms and Modularity

The smaller, self-contained chunks we create during top-down design are often called **sub-algorithms** (or modules).

*   **Definition:** A sub-algorithm is an independent, often reusable, part of a larger algorithm.
*   **Analogy:** In programming, the main algorithm is like the `main()` function, and a sub-algorithm is like any other function that `main()` can call to perform a specific task.
*   **Benefits:** Using sub-algorithms makes the main logic easier to read and allows for code reuse.

#### 7. The Importance of Algorithm Correction

Your first draft of an algorithm is rarely perfect. A crucial part of the design process is to test your logic and refine it.

**Example: The "Broken Lamp" Algorithm**

*   **Flawed First Draft:**
    1.  START
    2.  If lamp is unplugged, plug it in.
    3.  If bulb is burnt out, replace it.
    4.  If lamp is broken, repair it.
    5.  END
    *   **The Problem:** This algorithm is inefficient. It will check the bulb even if plugging in the lamp already solved the problem!

*   **Corrected, Efficient Algorithm:**
    1.  START
    2.  IF the lamp is unplugged THEN
    3.      Plug it in.
    4.  ELSE IF the bulb is burnt out THEN
    5.      Replace the bulb.
    6.  ELSE
    7.      Repair the lamp.
    8.  ENDIF
    9.  END

This demonstrates the use of branching and logic to create an algorithm that is not only correct but also efficient.

#### 8. How to Represent an Algorithm

The same logical algorithm can be represented in many different ways. The underlying logic does not change, only the implementation.

*   **Formulas:** `F = (9/5)C + 32`
*   **Words (Algorithm):** "Multiply the Celsius temperature by 9/5, then add 32."
*   **Flowcharts:** A visual diagram of the steps.
*   **Pseudo-code:** A text-based sketch of the logic.
*   **Program:** The final implementation in a language like C.

The ability to create the core **algorithm in words** is the first and most critical skill you must develop.