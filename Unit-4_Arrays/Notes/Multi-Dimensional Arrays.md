### Notes: Multi-Dimensional Arrays (Unit 4 - Part B)

#### 1. Introduction: Beyond a Single Line

A one-dimensional array is like a single row of data. However, many real-world problems require data to be organized in a grid or table with both rows and columns. Examples include:
*   A tic-tac-toe board.
*   A spreadsheet.
*   The pixels on a screen.
*   A matrix in a mathematical equation.

A **multi-dimensional array** is an "array of arrays." It allows you to store data in a structure with two or more dimensions. The most common and widely used type is the **two-dimensional (2D) array**.

#### 2. Two-Dimensional (2D) Arrays

A 2D array is best visualized as a grid or a table containing rows and columns. All elements in the grid must be of the **same data type**.

**A. Declaration of a 2D Array**
Declaration tells the compiler to allocate a block of memory for the grid.

*   **Syntax:**
    ```c
    data_type array_name[number_of_rows][number_of_columns];
    ```
*   **Breakdown:**
    *   `data_type`: The type for every element in the array (e.g., `int`, `float`).
    *   `array_name`: The identifier for the array.
    *   `[number_of_rows]`: The first dimension, specifying how many rows the grid has.
    *   `[number_of_columns]`: The second dimension, specifying how many columns the grid has.
*   **Total Elements:** The total number of elements that can be stored is `rows * columns`.

*   **Examples:**
    ```c
    // A 3x3 integer matrix for a tic-tac-toe board
    int tic_tac_toe[3][3];

    // A matrix to store marks of 10 students in 5 subjects
    // 10 rows (one for each student), 5 columns (one for each subject)
    float student_marks[10][5];
    ```

**B. Memory Representation**
Although we visualize a 2D array as a grid, computer memory is linear (a single long sequence). C stores 2D arrays in a **row-major order**.

*   **Row-Major Order:** All the elements of the first row are stored first, followed by all the elements of the second row, and so on.

*   **Example:** For `int matrix[2][3];`
    *   **Visual Grid:**
        `matrix[0][0]`, `matrix[0][1]`, `matrix[0][2]`
        `matrix[1][0]`, `matrix[1][1]`, `matrix[1][2]`
    *   **Actual Memory Layout:**
        `[ m[0][0] | m[0][1] | m[0][2] | m[1][0] | m[1][1] | m[1][2] ]`

**C. Accessing 2D Array Elements**
To access an element, you need to specify both its row and column index. Like 1D arrays, 2D arrays use **zero-based indexing** for both dimensions.

*   **Syntax:**
    ```c
    array_name[row_index][column_index];
    ```
*   **Example:** For `int matrix[3][4];`
    *   `matrix[0][0]` accesses the element in the 1st row, 1st column.
    *   `matrix[1][2]` accesses the element in the 2nd row, 3rd column.
    *   `matrix[2][3]` accesses the last element (3rd row, 4th column).

**D. Initialization of a 2D Array**
You can initialize a 2D array at the time of its declaration using nested curly braces.

*   **Syntax:**
    ```c
    data_type array_name[R][C] = { {r0_val1, r0_val2}, {r1_val1, r1_val2}, ... };
    ```

*   **Examples:**
    ```c
    // Full initialization of a 2x3 matrix
    int matrix[2][3] = { {10, 20, 30}, {40, 50, 60} };

    // You can omit the inner braces, but it's less readable
    int matrix[2][3] = { 10, 20, 30, 40, 50, 60 };

    // Omitting the row size is allowed, but the column size is mandatory
    int matrix[][3] = { {1, 2, 3}, {4, 5, 6} }; // Compiler infers 2 rows

    // Partial initialization - remaining elements are set to 0
    int matrix[2][3] = { {1, 2}, {3} }; // Equivalent to { {1, 2, 0}, {3, 0, 0} }
    ```

#### 3. Matrix Operations with 2D Arrays

The most common way to work with 2D arrays is by using **nested `for` loops**.
*   The **outer loop** iterates through the **rows**.
*   The **inner loop** iterates through the **columns** of the current row.

**A. Taking Input and Displaying a Matrix**

```c
#include <stdio.h>
#define ROWS 3
#define COLS 4

int main() {
    int matrix[ROWS][COLS];
    int i, j;

    // Taking input into the matrix
    printf("Enter the elements of the %dx%d matrix:\n", ROWS, COLS);
    for (i = 0; i < ROWS; i++) {       // Outer loop for rows
        for (j = 0; j < COLS; j++) {   // Inner loop for columns
            printf("Enter element [%d][%d]: ", i, j);
            scanf("%d", &matrix[i][j]);
        }
    }

    // Displaying the matrix
    printf("\nThe matrix you entered is:\n");
    for (i = 0; i < ROWS; i++) {
        for (j = 0; j < COLS; j++) {
            printf("%d\t", matrix[i][j]); // Use \t for neat formatting
        }
        printf("\n"); // Newline after each row
    }

    return 0;
}
```

**B. Matrix Addition**
To add two matrices, they must have the **same dimensions**. The addition is done element-wise.

*   **Algorithm:** `C[i][j] = A[i][j] + B[i][j]`

*   **Code Snippet:**
    ```c
    int A[2][2] = {{1, 2}, {3, 4}};
    int B[2][2] = {{5, 6}, {7, 8}};
    int C[2][2];
    int i, j;

    for (i = 0; i < 2; i++) {
        for (j = 0; j < 2; j++) {
            C[i][j] = A[i][j] + B[i][j];
        }
    }
    // Now matrix C will hold the result: {{6, 8}, {10, 12}}
    ```

**C. Matrix Multiplication**
Matrix multiplication is more complex. To multiply matrix `A` (of size `r1 x c1`) and matrix `B` (of size `r2 x c2`), the number of columns in `A` must equal the number of rows in `B` (`c1 == r2`). The resulting matrix `C` will have the size `r1 x c2`.

*   **Algorithm:** The element `C[i][j]` is the sum of the products of elements from the `i`-th row of `A` and the `j`-th column of `B`.
    `C[i][j] = Σ (A[i][k] * B[k][j])` for `k` from 0 to `c1-1`. This requires a third, inner loop.

*   **Code Snippet (for `r1 x c1` and `c1 x c2` matrices):**
    ```c
    // A is r1xc1, B is c1xc2, C is r1xc2
    for (i = 0; i < r1; i++) {
        for (j = 0; j < c2; j++) {
            C[i][j] = 0; // Initialize the element to 0
            for (k = 0; k < c1; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }
    ```

#### 4. Arrays with More Than Two Dimensions

While less common, C supports arrays with three or more dimensions. The concept is a direct extension.

*   **Declaration (3D Array):**
    ```c
    // An array to store data across 3 pages, each with 5 rows and 4 columns
    int data_cube[3][5][4];
    ```
*   **Accessing:** `data_cube[page][row][column]`
*   **Processing:** Requires three nested `for` loops.

These are conceptually "arrays of 2D arrays." They are used in specialized applications like 3D modeling or complex scientific simulations. For this course, a strong understanding of 1D and 2D arrays is the primary focus.