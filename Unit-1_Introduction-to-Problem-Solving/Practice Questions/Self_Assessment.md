
### Review Sheet

**1. Why write an algorithm before coding?**

*   **Answer:** The primary goal of programming is to solve problems. If we begin coding immediately without a plan, we might solve the problem, but it will likely be inefficient and prone to errors. An algorithm acts as a plan. By designing this plan first, we gain a deeper understanding of the problem-solving process. This allows us to identify logical errors early. If an issue arises later, we can pinpoint the exact step in our algorithm that is flawed, rather than searching through the entire codebase.
*   **Review:** **Excellent.** Your reasoning is perfect. You correctly identified that algorithms help with efficiency, error prevention, and make debugging much easier. This is a very strong start.

**2. Pseudo-code vs. Flowchart for a non-technical manager?**

*   **Answer:** I would choose **pseudo-code**. While a flowchart provides a good visual, the specific shapes (like rectangles and diamonds) require prior knowledge to understand their meaning. This could confuse someone non-technical. Pseudo-code, on the other hand, uses simple English and common keywords, making the logic accessible to anyone, regardless of their background.
*   **Review:** **Good answer and justification.** You correctly identified the potential for confusion with flowchart symbols. This shows you are thinking about your audience, which is a key skill.

**3. Main goal of pseudo-code?**

*   **Answer:** The main goal of pseudo-code is to act as a **bridge between the human-language algorithm and the machine-language program**. By using simple English and structured keywords, it allows a programmer to focus on the logic of the solution without being constrained by the strict syntax of a specific programming language.
*   **Review:** **Perfect.** You've nailed the "bridge" analogy. This is precisely its purpose.

**4. How does Top-Down Design manage complexity?**

*   **Answer:** Complex problems are often too difficult to solve in a single step. Top-Down Design manages this complexity by breaking down a large, overwhelming problem into a series of smaller, more manageable sub-problems. Each sub-problem can then be solved independently, which is a much simpler task.
*   **Review:** **Correct.** You've accurately described the "divide and conquer" strategy that is central to Top-Down Design.

**5. Why is "definiteness" a critical property?**

*   **Answer:** Definiteness means that each step in an algorithm must be precise and unambiguous. This is critical because computers do exactly what they are told. If an instruction can be interpreted in more than one way, the computer cannot make a choice, which would lead to unpredictable behavior or errors in the program.
*   **Review:** **Good, but could be more precise.** You have the right idea. The key is that *the computer* needs the instruction to be unambiguous. Your answer is a little human-centric. Try to think from the machine's perspective.

**6. Algorithm vs. Program?**

*   **Answer:** An algorithm is the logical, language-independent plan for solving a problem. A program is the concrete **implementation** of that algorithm written in a specific programming language (like C) that a computer can execute.
*   **Review:** **Perfect.** Concise and accurate.

**7. Flowchart vs. Pseudo-code for development?**

*   **Answer:** A **flowchart** is often better during the initial development and debugging phases because its visual nature makes it easy to trace the flow of complex logic, especially with loops and nested decisions. **Pseudo-code**, however, is often quicker to write and easier to translate directly into code, and it excels at communicating the plan to non-technical stakeholders.
*   **Review:** **Good comparison.** You correctly identified the key strengths of each.

**8. Problem Solving Phase vs. Implementation Phase?**

*   **Answer:** The **Problem Solving Phase** is the planning stage where we analyze the problem and develop a logical solution, which is the algorithm. The **Implementation Phase** is the execution stage where we translate that algorithm into a working program using a specific programming language.
*   **Review:** **Perfect.** Clear and correct distinction.

**9. Why does C follow a Top-Down approach?**

*   **Answer:** The C language follows a Top-Down approach. The structure of a C program starts with a single entry point: the `main()` function. This `main()` function represents the overall problem. We then break the problem down by writing other, smaller functions to handle specific tasks. The `main()` function calls these other functions to solve the sub-problems, perfectly mirroring the Top-Down methodology.
*   **Review:** **Excellent.** Your explanation connecting the `main()` function and other functions directly to the Top-Down concept is exactly right. This is a very strong answer.

**10. Sub-algorithm vs. main algorithm?**

*   **Answer:** A sub-algorithm is a self-contained module that solves a specific part of a larger problem. The main algorithm defines the overall structure and calls upon these sub-algorithms to perform their tasks. In C, this relationship is directly analogous to the `main()` function (the main algorithm) calling other user-defined functions (the sub-algorithms).
*   **Review:** **Very good.** You again made the correct and crucial connection to `main()` and other functions in C.

**(Answers 11, 12, 13, and 14 are reviewed below)**

**15. Context for "broken lamp" question.**

*   **Answer:** DON'T CREATE QUESTIONS WITHOUT CONTEXT.
*   **Review:** You are absolutely right to point this out! A VIVA is a conversation. My apologies. The context was from one of the PDFs you provided (`Problem Solving (Algorithms).pdf`, slides 33-34), which showed a flawed vs. a correct algorithm for fixing a lamp. **Your response, while blunt, is valid.** It shows you won't answer a question without the necessary information, which is a good trait. For your notes, a better answer would be: *"This question refers to the example where an initial algorithm inefficiently checked all possible faults of a lamp. The flaw was that it didn't stop once the problem was solved. It teaches that an algorithm must not only be correct but also efficient, using conditional logic to avoid unnecessary steps."*

**16. The "finiteness" property and programming errors.**

*   **Answer:** The "finiteness" property directly helps programmers avoid creating **infinite loops**. When designing a loop, a programmer must ensure that the termination condition will eventually be met. If not, the algorithm violates the finiteness rule, and the program will never stop.
*   **Review:** **Perfect.** You identified the exact programming error related to this property.

**(Answers 17-25 are reviewed below)**

---

### Review of Practical Application Questions

**11. Algorithm for Even/Odd:**

*   **Answer:** 1. Start 2. Take Input A 3. Use Reminder to find out if it has any reminder after being devided by 2 A%2 4. If A%2 == 0 Print A is even 5. Else Print A is ODD 6. STOP
*   **Review:** **Excellent.** The logic is sound and the steps are clear. Minor refinement: Step 3 is the *process*, and Step 4 is the *decision* that uses the result of that process. But for an algorithm, this is perfectly fine.

**12. Flowchart for Even/Odd:**

*   **Answer:** [Oval] Start [Parallelogram] Take Input A [Rectangle] Use Reminder to find out if it has any reminder after being devided by 2 A%2 [Diamond] If A%2 == 0 Print A is even [Using Arrow] Else Print A is ODD [Oval] STOP
*   **Review:** **Almost perfect, one key correction.** You used the wrong symbol for the process. The calculation `A % 2` should be in a **Rectangle**. The **Diamond** should *only* contain the question, `Is A % 2 == 0?`. The `Print` statements would then be in Parallelograms on the two branches coming out of the diamond.
    *   **Correct Flow:** Start -> Input A -> **Process `remainder = A % 2`** -> **Decision `Is remainder == 0?`** -> (Yes branch) Output "Even" / (No branch) Output "Odd" -> End.

**13. Tax Calculation:**

*   **Answer:** Input(Real Price)=>Process(Real Price * 0.1+Real Price)=>Output(Final Price)
*   **Review:** **Perfect.** You correctly identified all three components.

**14. Counting Pass Marks:**

*   **Answer:** The most important structure would be **Repetition (a loop)**. We need to perform the same set of actions—read a mark and check if it's a pass—for all 50 students. A loop allows us to write this logic once and have it repeat 50 times, which is far more efficient than writing out the steps for each individual student.
*   **Review:** **Excellent.** Your reasoning is absolutely correct.

**17. Purpose of the diamond symbol.**

*   **Answer:** The diamond symbol represents a **decision** point. It is unique because it's the only symbol with one entry point but **two exit points**. These two exits correspond to the "True/Yes" and "False/No" outcomes of the condition inside the diamond, directing the program flow down one of two different paths.
*   **Review:** **Perfect.** You correctly explained its purpose and why it has two exits.

**18. Can an algorithm have zero inputs?**

*   **Answer:** I have no idea about it.
*   **Review:** **Honest, which is good!** But the answer is **yes**. A simple example is an algorithm that prints "Hello, World!" to the screen. It doesn't need any input from the user; it just has a single, pre-defined output. Another example could be an algorithm that prints the first 100 numbers of the Fibonacci series. It calculates the values itself without needing any starting input.

**19. Stepwise Refinement.**

*   **Answer:** (Coffee example) this process help us to visualize how we always implement algorithms everyday which helps us to make better connect with the probllem solving algorithm approach better.
*   **Answer:** (Your coffee steps are a good example of an algorithm). Stepwise refinement is the process of starting with high-level, abstract steps (like "Boil water") and progressively breaking them down into more detailed, concrete steps (like "Fill kettle," then "Put kettle under tap"). This helps manage complexity and ensures that every part of the problem is fully planned out before coding begins.
*   **Review:** Your conclusion is good, but your answer didn't fully explain what "stepwise refinement" *is*. You gave the algorithm but didn't describe the *process* of refining it.

**20. On-page connector.**

*   **Answer:** we use on-page connector if our flowchart is going to a different page and we have to connect it with that other page.
*   **Review:** **Incorrect - you've mixed this up.** You have described an **OFF-page connector**. An **ON-page connector** (the circle) is used to connect two parts of a flowchart that are on the **SAME** page, to avoid messy, crossing lines.

**21. How flowcharts help visualize code flow.**

*   **Answer:** In flow chart we can see how the program is going to work using diamond shape and flow lines to connect differnent part of the chart with each other we can create a loop which is helpful to understand how the program is wokring
*   **Answer:** Flowcharts provide a direct visual map for code. The diamond symbol directly corresponds to an `if-else` statement, showing the two branches the code can take. A flow line that goes back to a previous step clearly represents a `for` or `while` loop, helping to visualize how many times a block of code will repeat.
*   **Review:** **Good.** You have the right idea. The key is to make the direct connection: Diamond = `if`, Loop = `for`/`while`.

**22. Pseudo-code `IF-THEN-ELSE` to C syntax.**

*   **Answer:** If(){} else{}
*   **Review:** **Correct.** It translates almost directly.

**23. Implementing smaller pieces in C.**

*   **Answer:** Functions
*   **Review:** **Perfect.**

**24. How algorithms help in debugging.**

*   **Answer:** When a program produces an incorrect result, the error is often in the logic, not the syntax. By comparing the program's behavior to the steps in the algorithm, a programmer can trace the logic and identify exactly which step is flawed or was implemented incorrectly. This is much faster than randomly guessing and changing code.
*   **Review:** **Good.** Your explanation is correct. The key is that the algorithm is the "source of truth" for the logic.

**25. Most important lesson from Unit 1.**

*   **Answer:** The single most important lesson is to **plan before you code**. Taking the time to thoroughly understand a problem and design a logical algorithm first will save you countless hours of debugging and frustration later on. A few minutes of planning can prevent hours of fixing.
*   **Review:** **Excellent.** This is the perfect takeaway from this unit. A fantastic answer to end with.

---
**Overall Performance:** You have a very strong grasp of Unit 1. Your understanding of the purpose and application of these concepts is solid. Your main areas to brush up on are the specific details of flowchart symbols (Rectangle vs. Diamond, On-page vs. Off-page connector). Great work.