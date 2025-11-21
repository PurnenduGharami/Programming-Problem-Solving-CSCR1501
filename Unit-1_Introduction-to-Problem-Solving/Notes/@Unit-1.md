# **Unit 1: Introduction to Problem Solving - Master Notes**

## **1. The Nature of Problem Solving**

Before writing code, one must understand the problem. Problem-solving is the process of removing barriers to achieve a specific goal.

### **A. Types of Thinking Skills**
* **Critical Thinking:** Involves analyzing, evaluating, reasoning, and using evidence to solve a problem. It follows strict logic (e.g., *"If A is true, then B must be true"*).
* **Creative Thinking:** Involves generating new ideas, alternative explanations, and seeing existing situations in a new way.
* **Logic:** The principles of correct reasoning. It governs the validity of arguments.

### **B. The Problem-Solving Strategy (7 Steps)**
1.  **Define the Problem:** Thoroughly understand what is asked.
2.  **Analyze the Problem:** Identify relevant info and constraints.
3.  **Outline Requirements:** What is needed to solve it?
4.  **Formal Representation:** Model the problem (e.g., mathematically).
5.  **Design a Plan:** Create the Algorithm.
6.  **Execute the Plan:** Write the code.
7.  **Evaluate Results:** Check if the output is correct.

> **Note:** Not all problems can be solved. Problems that have no solution are called **Open Problems**.

---

## **2. Algorithms**

### **A. Definition**
An **Algorithm** is a finite sequence of precise, unambiguous steps to solve a specific problem. It is the "recipe" for the computer program.

### **B. Donald Knuth’s 5 Properties of an Algorithm**
For a set of steps to be considered a valid algorithm, it **must** satisfy these five properties:
1.  **Finiteness:** The algorithm must always terminate (stop) after a finite number of steps. It cannot run forever (infinite loop).
2.  **Definiteness:** Each step must be clear and unambiguous. There should be no room for confusion or multiple interpretations.
3.  **Input:** The algorithm accepts zero or more inputs (values supplied externally).
4.  **Output:** It must produce at least one output (result) that relates to the input.
5.  **Effectiveness:** The steps must be basic enough that they can, in principle, be performed exactly by a person using pencil and paper in a finite amount of time.

### **C. Sub-Algorithms (Modules)**
* **Definition:** A complex algorithm is often broken down into smaller chunks called "Sub-algorithms" or "Modules".
* **Purpose:**
    * Makes the logic easier to read and debug.
    * **Reusability:** The same sub-algorithm can be used multiple times (e.g., a `Square()` function called whenever you need to square a number).
    * **Independence:** They can be developed and tested independently.

---

## **3. Flowcharts**

### **A. Definition**
A flowchart is a **graphical/pictorial representation** of an algorithm using standard symbols to depict the flow of logic and data.

### **B. Standard Symbols**

| Symbol Name | Shape | Function |
| :--- | :--- | :--- |
| **Terminal** | Oval / Rounded Rectangle | Indicates the **Start** or **Stop** (End) of the program. |
| **Input/Output** | Parallelogram | Used for **Read** (Input) and **Print** (Output) operations. |
| **Process** | Rectangle | Indicates calculations or data manipulation (e.g., `Sum = A + B`). |
| **Decision** | Diamond | Used for branching (Yes/No questions). Has 1 entry and 2 exits (True/False). |
| **Connector** | Small Circle | Connects parts of a flowchart on the **same page**. |
| **Off-page Connector** | Pentagon / Shield | Connects parts of a flowchart across **different pages**. |
| **Flow Lines** | Arrows | Shows the direction of logical flow. |
| **Predefined Process** | Rectangle with double sides | Represents a Sub-algorithm or Module call. |



[Image of Flowchart Symbols]


### **C. Four Basic Control Structures**
1.  **Sequence:** Steps are executed linearly, one after another.
2.  **Decision (Branching/Selection):** The flow splits based on a condition (e.g., `If X > Y`).
3.  **Repetition (Looping):** A set of instructions is executed repeatedly until a condition is met (e.g., `While I < 10`).
4.  **Case (Switch):** One of several actions is selected based on the value of a single variable (e.g., `Bonus` depends on `Years_Employed`).

### **D. Advantages of Flowcharts**
* **Communication:** Explains logic clearly to others (clients/programmers).
* **Effective Analysis:** Helps visualize bottlenecks or logical errors.
* **Documentation:** Serves as a blueprint for the system.
* **Maintenance:** Makes it easier to update the program later.

### **E. Guidelines for Drawing**
* Standard flow is **Top to Bottom** or **Left to Right**.
* Arrows should not cross each other (use connectors if needed).
* Every flowchart must have exactly **one Start** and **one Stop**.

---

## **4. Pseudo-Code**

* **Definition:** An informal, high-level description of an algorithm using English-like syntax.
* **Nature:** It is **not** machine-readable and cannot be compiled. It is for human understanding before coding begins.
* **Common Keywords:**
    * `START`, `STOP`
    * `READ`, `GET`, `PRINT`, `DISPLAY`
    * `COMPUTE`, `CALCULATE`, `SET`
    * `IF`, `ELSE`, `ENDIF`
    * `WHILE`, `ENDWHILE`, `FOR`

---

## **5. Problem Solving Approaches (Top-Down vs. Bottom-Up)**

This is a key theoretical concept distinguishing how different programming languages function.

### **A. Top-Down Approach (Decomposition)**
* **Concept:** Starts with the "Whole" problem (Main Routine) and breaks it down into smaller sub-problems (Modules/Functions).
* **Flow:** High-Level $\rightarrow$ Low-Level.
* **Focus:** Emphasis is on **Algorithms** and **Procedures** (Doing things).
* **Used By:** Structured/Procedural languages like **C** and **Fortran**.
* **Pros:** Easier to visualize the big picture; good for debugging.

### **B. Bottom-Up Approach (Composition)**
* **Concept:** Starts by identifying/building the smallest components (Low-level tools) and combining them to form the final system.
* **Flow:** Low-Level $\rightarrow$ High-Level.
* **Focus:** Emphasis is on **Data** and **Objects** rather than just procedure.
* **Used By:** Object-Oriented languages like **C++** and **Java**.
* **Pros:** High **Reusability** of code; data hiding (encapsulation) reduces redundancy.

---

## **6. Quick Comparison Table**

| Feature | Algorithm | Flowchart | Pseudo-Code |
| :--- | :--- | :--- | :--- |
| **Form** | Step-by-step text | Graphical Diagram | Structured English |
| **Purpose** | Logic definition | Visual Logic Flow | Draft for Coding |
| **Machine Executable?** | No | No | No |
| **Standard Rules?** | No strict syntax | Strict Symbols | No strict syntax |

---

**Completion Check:**
* **Syllabus covered:** Flowcharts (elements, branching, iteration), Algorithms, Pseudo-code.
* **Slides covered:** Thinking skills, Top-down/Bottom-up tables, Flowchart symbols & rules, Knuth's properties, Sub-algorithms.



