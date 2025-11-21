# **Unit 4: Arrays, Searching, and Sorting - Master Notes**

## **1. Introduction to Arrays**

### **A. Definition**

An **Array** is a collection of a finite number of **homogeneous** (similar type) data elements stored in **contiguous** (successive) memory locations.

  * It allows storing multiple values in a single variable name.
  * **Index/Subscript:** Elements are accessed using an index.
  * **Base Index:** In C, indexing always starts at **0** and ends at **size - 1**.

### **B. One-Dimensional (1D) Arrays**

Used to store a list of items (e.g., Marks of students).

1.  **Declaration Syntax:**
    `data_type array_name[size];`

      * *Example:* `int marks[30];` (Allocates memory for 30 integers).

2.  **Initialization:**

      * **Static:** `int arr[5] = {10, 20, 30, 40, 50};`
      * **Partial:** `int arr[5] = {10, 20};` (Remaining elements become 0).
      * **Without Size:** `int arr[] = {1, 2, 3};` (Size inferred as 3).

3.  **Accessing Elements:**

      * `arr[0]` accesses the first element.
      * `arr[i]` accesses the element at index `i`.
      * *Address Calculation:* If base address is `B` and size of data type is `S`, address of `arr[i]` = `B + (i * S)`.

-----

## **2. Multi-Dimensional Arrays (2D Arrays)**

Used to store data in a tabular format (Rows and Columns), like matrices.

1.  **Declaration Syntax:**
    `data_type array_name[rows][columns];`

      * *Example:* `int matrix[3][3];`

2.  **Initialization:**

    ```c
    int table[2][3] = {
        {10, 20, 30},  // Row 0
        {40, 50, 60}   // Row 1
    };
    ```

      * *Note:* Specifying the number of **columns** is mandatory, but rows can be optional during initialization.

3.  **Memory Representation:**

      * Elements are stored row by row in contiguous memory (Row-Major Order).

4.  **Matrix Operations (Key Logic):**

      * **Addition:** `sum[i][j] = A[i][j] + B[i][j];` (Dimensions must be same).
      * **Transpose:** `trans[j][i] = mat[i][j];` (Swap rows and columns).
      * **Multiplication:** Requires nested loops. `res[i][j] += A[i][k] * B[k][j];`

-----

## **3. Searching Algorithms**

Searching is the process of finding a specific element (**Target/Key**) in an array.

### **A. Linear Search (Sequential Search)**

  * **Method:** Checks every element one by one from the start to the end.
  * **Requirement:** Array **does not** need to be sorted.
  * **Logic:**
    ```c
    for(i = 0; i < n; i++) {
        if(arr[i] == key) {
            print("Found at index", i);
            break;
        }
    }
    ```
  * **Complexity:** Worst case is checking all N elements.

### **B. Binary Search**

  * **Method:** Uses "Divide and Conquer". Compares the target with the **middle** element.
      * If `Target == Middle`: Found.
      * If `Target < Middle`: Search Left half.
      * If `Target > Middle`: Search Right half.
  * **Requirement:** Array **MUST be sorted** (Ascending/Descending).
  * **Logic:**
    ```c
    mid = (low + high) / 2;
    if (arr[mid] == key) found;
    else if (arr[mid] < key) low = mid + 1;
    else high = mid - 1;
    ```
  * **Complexity:** Much faster than Linear Search for large datasets ($O(\log n)$).

-----

## **4. Sorting Algorithms**

Sorting is arranging elements in a specific order (Ascending/Descending).

### **A. Bubble Sort**

  * **Concept:** Repeatedly steps through the list, compares adjacent elements, and **swaps** them if they are in the wrong order.
  * **Process:** Large values "bubble" to the top (end of the array) after each pass.
  * **Logic:**
    ```c
    for(i = 0; i < n-1; i++) {       // Passes
        for(j = 0; j < n-i-1; j++) { // Comparisons
            if(arr[j] > arr[j+1]) {
                swap(arr[j], arr[j+1]);
            }
        }
    }
    ```

### **B. Insertion Sort**

  * **Concept:** Builds the sorted array one item at a time. It picks an element and inserts it into its correct position within the already sorted part.
  * **Analogy:** Sorting playing cards in your hand.
  * **Logic:**
    ```c
    for(i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;
        // Move elements greater than key one position ahead
        while(j >= 0 && arr[j] > key) {
            arr[j+1] = arr[j];
            j--;
        }
        arr[j+1] = key;
    }
    ```

### **C. Selection Sort** (Mentioned in Syllabus)

  * **Concept:** Repeatedly finds the minimum element from the unsorted part and puts it at the beginning.

-----

## **5. Summary of Operations (Code Snippets)**

| Operation | Key Logic/Formula |
| :--- | :--- |
| **Sum of Array** | `sum = sum + arr[i];` inside a loop. |
| **Matrix Add** | `C[i][j] = A[i][j] + B[i][j];` inside nested loops. |
| **Matrix Mul** | `C[i][j] += A[i][k] * B[k][j];` inside triple loops. |
| **Linear Search** | `if(arr[i] == key) return index;` |
| **Binary Search** | `mid = (low+high)/2;` update `low` or `high`. |

-----

