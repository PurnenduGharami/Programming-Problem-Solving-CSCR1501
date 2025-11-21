### Unit 4: Detailed Topic List

The unit is officially titled **"Arrays"**. It covers the definition, use, and common applications of one-dimensional and multi-dimensional arrays, with a strong focus on classic searching and sorting algorithms.

#### A) One-Dimensional Arrays
This section introduces the basic concept of an array as a linear collection of elements.

*   **Declaration of an Array:**
    *   The syntax for creating an array: `data_type array_name[size];`
    *   Understanding the role of the data type (all elements must be of the same type), the name, and the fixed size.
*   **Initialization of an Array:**
    *   Initializing an array at the time of declaration (e.g., `int marks[5] = {90, 85, 92, 78, 88};`).
    *   Partial initialization and default values.
    *   Initializing without specifying a size (e.g., `int marks[] = {1, 2, 3};`).
*   **Accessing Array Elements:**
    *   Understanding that arrays use a **zero-based index** (the first element is at index `0`).
    *   Using the subscript operator `[]` to access individual elements (e.g., `marks[2]`).
*   **Manipulation of Array Elements:**
    *   Using loops (especially the `for` loop) to traverse the array for input, output, and processing.
    *   **Insert:** Adding a new element into the array (often requires shifting existing elements).
    *   **Delete:** Removing an element from the array (often requires shifting existing elements).
    *   **Search:** Finding a specific element within the array (covered in detail in Part C).

#### B) Multi-Dimensional Arrays
This section extends the concept of arrays to two or more dimensions, most commonly 2D arrays, which are used to represent matrices or tables.

*   **Declaration of a 2D Array:**
    *   The syntax for creating a 2D array: `data_type array_name[rows][columns];`.
*   **Initialization of a 2D Array:**
    *   Initializing a 2D array using nested braces (e.g., `int matrix[2][3] = {{1, 2, 3}, {4, 5, 6}};`).
*   **Accessing 2D Array Elements:**
    *   Using two indices (row and column) to access an element (e.g., `matrix[1][2]`).
*   **Matrix Operations:**
    *   Using nested loops to traverse and manipulate 2D arrays.
    *   Common operations like matrix addition, subtraction, multiplication, and finding the transpose of a matrix.

#### C) Applications of Arrays: Searching and Sorting
This is the most practical and algorithm-focused part of the unit. You will implement classic algorithms that are fundamental to computer science.

*   **Searching Algorithms:** The process of finding the location of a specific element (the "key") in an array.
    *   **Linear Search:**
        *   A simple, sequential search algorithm.
        *   It starts at the first element and checks each element one by one until the key is found or the end of the array is reached.
    *   **Binary Search:**
        *   A much more efficient search algorithm.
        *   **Requirement:** The array must be **sorted** first.
        *   It works by repeatedly dividing the search interval in half. It compares the key to the middle element and eliminates half of the remaining elements from the search.

*   **Sorting Algorithms:** The process of arranging the elements of an array in a specific order (e.g., ascending or descending).
    *   **Bubble Sort:**
        *   A simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The passes through the list are repeated until the list is sorted.
    *   **Selection Sort:**
        *   An in-place comparison sorting algorithm.
        *   It divides the array into a sorted and an unsorted part. It repeatedly finds the minimum element from the unsorted part and moves it to the end of the sorted part.
    *   **Insertion Sort:**
        *   Another simple sorting algorithm that builds the final sorted array one item at a time.
        *   It iterates through the input elements and, for each element, inserts it into its correct position in the already-sorted part of the array.

