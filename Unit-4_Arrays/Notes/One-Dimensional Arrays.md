### Notes: One-Dimensional Arrays (Unit 4 - Part A)

#### 1. The Problem: Why Do We Need Arrays?

So far, you've used variables to store single pieces of data. For example:
`int student1_marks = 85;`
`int student2_marks = 92;`
`int student3_marks = 78;`

This works for a few students, but what if you need to store the marks of 100 students? Declaring 100 separate variables would be incredibly inefficient, hard to manage, and impossible to process systematically with a loop.

This is the problem that arrays solve. An array allows you to store a collection of related items under a **single variable name**.

#### 2. What is an Array? (The Formal Definition)

An array is a **fixed-size, sequential collection of elements of the same data type**.

Let's break down this definition:
*   **Fixed-Size:** When you create an array in C, you must specify its size, and this size cannot be changed later.
*   **Sequential Collection:** The elements are stored one after another in a continuous block of memory. Think of them as a row of numbered mailboxes.
*   **Same Data Type:** All elements in an array must be of the same type (e.g., all `int`, all `float`, or all `char`). You cannot mix an integer and a character in the same C array.

#### 3. Declaring a One-Dimensional Array

Declaration is the process of telling the compiler to allocate memory for the array.

*   **Syntax:**
    ```c
    data_type array_name[size];
    ```
*   **Breakdown:**
    *   `data_type`: The type of data that all elements in the array will hold (e.g., `int`, `float`, `char`).
    *   `array_name`: The identifier (name) you give to your array. It follows the same naming rules as variables.
    *   `[size]`: The number of elements the array can hold. The `size` must be a **constant integer value**.

*   **Examples:**
    ```c
    // An array to store the marks of 50 students
    int student_marks[50];

    // An array to store the prices of 20 items
    float item_prices[20];

    // An array to store a name (a sequence of characters)
    char student_name[30];
    ```

#### 4. Memory Representation and Accessing Elements (Indexing)

Understanding how arrays are stored in memory is key to using them correctly.

*   **Contiguous Memory:** The elements of an array are stored in adjacent memory locations. If an `int` takes 4 bytes and the first element is at memory address 1000, the second will be at 1004, the third at 1008, and so on.

*   **Zero-Based Indexing:** C uses **zero-based indexing** to access array elements. This is a crucial concept.
    *   The **first** element is at index `0`.
    *   The **second** element is at index `1`.
    *   The **last** element is at index `size - 1`.

*   **Accessing Syntax:**
    ```c
    array_name[index];
    ```

*   **Example:** For an array `int marks[5];`
    *   `marks[0]` accesses the 1st element.
    *   `marks[2]` accesses the 3rd element.
    *   `marks[4]` accesses the 5th (and last) element.
    *   `marks[5]` is **out of bounds** and will lead to undefined behavior or a program crash. This is a very common bug.

#### 5. Initializing a One-Dimensional Array

Initialization is the process of assigning initial values to the array elements.

**Method 1: Initialization at Declaration (Most Common)**
You provide a list of values in curly braces `{}`.

```c
// Full initialization
int marks[5] = {90, 85, 92, 78, 88};

// The compiler automatically calculates the size
int numbers[] = {1, 2, 3, 4}; // This creates an array of size 4

// Partial initialization
int data[10] = {10, 20, 30}; // First 3 elements are initialized.
                              // The remaining 7 elements are automatically set to 0.
```

**Method 2: Using a Loop (For User Input)**
This is the most practical way to fill an array with data from the user. You must use a loop to iterate through each index.

```c
#include <stdio.h>
int main() {
    int scores[5];
    int i;

    // Taking input into the array
    printf("Enter 5 scores:\n");
    for (i = 0; i < 5; i++) {
        printf("Enter score for student %d: ", i + 1);
        scanf("%d", &scores[i]); // Note the & and the index i
    }

    // Displaying the array elements
    printf("\nThe scores you entered are:\n");
    for (i = 0; i < 5; i++) {
        printf("%d ", scores[i]);
    }
    printf("\n");

    return 0;
}
```

#### 6. Manipulation of Array Elements

Once an array is created, you can perform various operations on it.

**A. Traversal**
Traversal means visiting every element of the array exactly once. This is what we did in the example above using a `for` loop to print all elements.

**B. Insertion**
Inserting an element at a specific position in an array is a multi-step process because arrays have a fixed size and elements are sequential.

*   **Algorithm:**
    1.  Check if the array is already full. If so, you cannot insert.
    2.  Ask for the `element` to be inserted and the `position` (index).
    3.  Shift all elements from the target position to the end, one step to the right. This must be done from **right to left** to avoid overwriting data.
    4.  Place the new `element` at the desired `position`.
    5.  Logically, increase the count of elements in the array.

*   **Code Snippet (Assuming `n` is the current number of elements):**
    ```c
    // Insert 'element' at 'pos' in array 'arr' of size 'n'
    for (i = n; i >= pos; i--) {
        arr[i] = arr[i - 1]; // Shift elements to the right
    }
    arr[pos - 1] = element; // Insert the element (pos-1 for 0-based index)
    n++; // Increment the size
    ```

**C. Deletion**
Deleting an element also requires shifting elements to fill the gap.

*   **Algorithm:**
    1.  Ask for the `position` of the element to delete.
    2.  Shift all elements from the position *after* the deleted element, one step to the left. This overwrites the element to be deleted.
    3.  Logically, decrease the count of elements in the array.

*   **Code Snippet:**
    ```c
    // Delete element at 'pos'
    for (i = pos - 1; i < n - 1; i++) {
        arr[i] = arr[i + 1]; // Shift elements to the left
    }
    n--; // Decrement the size
    ```

**D. Searching (Linear Search)**
Searching is the process of finding whether a given element (the "key") exists in the array. The simplest method is a **Linear Search**.

*   **Algorithm:**
    1.  Start from the first element (index `0`).
    2.  Compare the current element with the `key`.
    3.  If they match, you've found the element. Return its index.
    4.  If they don't match, move to the next element.
    5.  If you reach the end of the array without finding the `key`, the element is not present.

*   **Code Snippet:**
    ```c
    int key = 78;
    int found_index = -1; // Use -1 to indicate not found

    for (i = 0; i < n; i++) {
        if (arr[i] == key) {
            found_index = i;
            break; // Exit the loop once found
        }
    }

    if (found_index != -1) {
        printf("Element found at index %d\n", found_index);
    } else {
        printf("Element not found.\n");
    }
    ```