Of course. You've now covered all the material for **Unit 4: Arrays**. This unit is extremely practical, so the VIVA questions will focus heavily on implementation logic, use-cases, and the trade-offs between different algorithms.

As your CodeMentor, I've prepared a set of 25 VIVA-style questions designed to test your deep understanding of how to use arrays and how the classic searching and sorting algorithms work.

---

### VIVA Voce Examination: Unit 4 - Arrays

#### Category 1: Array Fundamentals

1.  What is the primary advantage of using an array over multiple individual variables? Give a practical example.
2.  Explain what **zero-based indexing** means. If you declare an array `int arr[10];`, what is the index of the first element and the last element?
3.  What happens if you try to access an element that is "out of bounds," for example, `arr[10]` in an array of size 10?
4.  Why is the size of a C array required to be a constant value?
5.  Explain the difference in memory layout between a 1D array `int arr[6];` and a 2D array `int matrix[2][3];`. How many elements does each hold?

#### Category 2: Array Operations and Logic

6.  Why are `for` loops so commonly used when working with arrays?
7.  You need to insert a new number into the middle of a fully populated array. What steps must you take to accomplish this, and what is the main drawback of this operation?
8.  When traversing a 2D array (a matrix), what do the outer and inner loops typically represent?
9.  To add two matrices, what is the one critical condition that must be met? Explain how the addition is performed.
10. Matrix multiplication is more complex than addition. To multiply matrix A (size 3x4) by matrix B (size 4x2), what will be the dimensions of the resulting matrix C?

#### Category 3: Searching Algorithms

11. Describe the core logic of a **Linear Search**. What is its main advantage and its main disadvantage?
12. You are given a large, unsorted list of numbers and asked to find a specific value. Which searching algorithm must you use? Why can't you use the other one?
13. What is the single most important prerequisite for using a **Binary Search**?
14. Explain the "divide and conquer" strategy of Binary Search. How does it achieve its efficiency?
15. In the worst-case scenario, how many comparisons would a Linear Search take to find an item in an array of 1000 elements? How many would a Binary Search take (approximately)?

#### Category 4: Sorting Algorithms

16. In your own words, describe how **Bubble Sort** works. Why is it called "bubble" sort?
17. After the very first pass of a Bubble Sort on an unsorted array, where is the largest element located?
18. Explain the core logic of **Selection Sort**. How is its approach to finding the correct position different from Bubble Sort?
19. Describe the analogy of sorting a hand of playing cards. Which sorting algorithm does this analogy represent, and why?
20. You have an array that is already almost completely sorted, with only one or two elements out of place. Which of the three sorting algorithms (`Bubble`, `Selection`, `Insertion`) would likely perform the best, and why?

#### Category 5: Practical Application and Trade-offs

21. Imagine you are programming a dictionary application. When a user types a word, you need to find its definition. Would you store the words in a sorted or unsorted array? Which search algorithm would you use and why is it the best choice for this application?
22. You are given a choice between Linear Search and Binary Search. If performance and speed are the top priority, why wouldn't you *always* choose Binary Search? What is the hidden cost?
23. How would you modify a Bubble Sort algorithm to stop early if the array becomes sorted before all passes are complete?
24. You are writing a program to manage the top 10 high scores for a game. The scores are always kept sorted. When a player gets a new score, it needs to be added to the list. Which sorting algorithm's logic is most similar to this process?
25. All three sorting algorithms you learned have poor performance on large datasets. Why, then, are they so important for a computer science student to learn and implement?

---

### Next Steps

Theory is one thing, but the true test for this unit is implementation. These algorithms are tangible and you can see them work.

1.  **Code Every Algorithm:** Create a new folder `Unit-4_Arrays` in your repository. Inside, create separate `.c` files for:
    *   `linear_search.c`
    *   `binary_search.c`
    *   `bubble_sort.c`
    *   `selection_sort.c`
    *   `insertion_sort.c`
2.  **Test Your Code:** In each file, create a sample array, print it, call your search/sort function, and then print the result to verify it works correctly. Test with different arrays (e.g., already sorted, reverse sorted, all same elements).
3.  **Implement Matrix Operations:** Create a file like `matrix_operations.c` and write functions to add and multiply two 2x2 or 3x3 matrices. This will solidify your understanding of nested loops.
4.  **Solve the Exercises:** Your course slides often have exercise problems. Attempting these is the best way to prepare for exams.

Writing the code for these algorithms yourself, from scratch, is the single most effective way to master the concepts of Unit 4.