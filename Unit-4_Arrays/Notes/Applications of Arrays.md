### Notes: Applications of Arrays: Searching and Sorting (Unit 4 - Part C)

#### 1. Introduction: Why Search and Sort?

Once you have data stored in an array, two of the most common tasks you'll need to perform are:
1.  **Searching:** Finding a specific piece of data within the collection. For example, "Does the number 78 exist in our list of student marks?"
2.  **Sorting:** Arranging the entire collection of data in a specific order (e.g., ascending or descending). For example, "List all student marks from lowest to highest."

Mastering these algorithms is essential. Efficient searching and sorting are critical for the performance of countless applications, from databases to web search engines.

---

### Part I: Searching Algorithms

Searching is the process of finding the location (index) of a target element, often called the **key**, within an array.

#### A. Linear Search (Sequential Search)

Linear search is the simplest search algorithm. It sequentially checks each element of the array for the key until a match is found or the entire list has been searched.

*   **Analogy:** Finding a specific book on a messy, unsorted bookshelf. You start at one end and check every single book, one by one, until you find the one you're looking for.
*   **How it Works:**
    1.  Start at the first element (index `0`).
    2.  Compare the current element with the `key`.
    3.  If they match, the search is successful. Return the current index.
    4.  If they don't match, move to the next element.
    5.  Repeat steps 2-4 until you either find the key or reach the end of the array.
    6.  If you reach the end of the array without a match, the key is not present.

*   **Key Characteristic:** Works on **both sorted and unsorted** arrays.
*   **Efficiency:** It is relatively slow for large arrays. In the worst case, you have to check every single element.

*   **C Implementation:**
    ```c
    #include <stdio.h>

    int linearSearch(int arr[], int size, int key) {
        for (int i = 0; i < size; i++) {
            if (arr[i] == key) {
                return i; // Element found, return its index
            }
        }
        return -1; // Element not found, return -1 as a signal
    }

    int main() {
        int marks[] = {90, 85, 92, 78, 88};
        int size = 5;
        int key = 78;

        int result = linearSearch(marks, size, key);

        if (result != -1) {
            printf("Element %d found at index %d.\n", key, result);
        } else {
            printf("Element %d not found in the array.\n", key);
        }
        return 0;
    }
    ```

#### B. Binary Search

Binary search is a much faster and more efficient search algorithm, but it has one critical prerequisite.

*   **Prerequisite:** The array **MUST BE SORTED** before you can perform a binary search.
*   **Analogy:** Finding a word in a dictionary. You don't start from the first page. You open it to the middle. If the word you're looking for comes alphabetically before the words on that page, you know it's in the first half. If it comes after, you know it's in the second half. You discard half the dictionary with a single check and repeat the process.
*   **How it Works (Divide and Conquer):**
    1.  Find the middle element of the array.
    2.  Compare the middle element with the `key`.
    3.  **If they match,** the search is successful. Return the middle index.
    4.  **If the `key` is less than the middle element,** then the key can only be in the **left half** of the array. Discard the right half and repeat the search on the left half.
    5.  **If the `key` is greater than the middle element,** then the key can only be in the **right half** of the array. Discard the left half and repeat the search on the right half.
    6.  The process continues until the element is found or the search interval becomes empty.

*   **Efficiency:** Extremely fast for large arrays because it eliminates half the data at each step.

*   **C Implementation:**
    ```c
    #include <stdio.h>

    int binarySearch(int arr[], int size, int key) {
        int low = 0;
        int high = size - 1;

        while (low <= high) {
            int mid = low + (high - low) / 2; // Avoids potential overflow vs (low+high)/2

            // Check if key is present at mid
            if (arr[mid] == key) {
                return mid; // Element found
            }

            // If key is smaller than mid, it must be in the left subarray
            if (arr[mid] > key) {
                high = mid - 1;
            } 
            // Else the key must be in the right subarray
            else {
                low = mid + 1;
            }
        }
        return -1; // Element not found
    }

    int main() {
        // IMPORTANT: The array must be sorted!
        int sorted_marks[] = {78, 85, 88, 90, 92};
        int size = 5;
        int key = 90;

        int result = binarySearch(sorted_marks, size, key);

        if (result != -1) {
            printf("Element %d found at index %d.\n", key, result);
        } else {
            printf("Element %d not found in the array.\n", key);
        }
        return 0;
    }
    ```

---

### Part II: Sorting Algorithms

Sorting is the process of arranging array elements into a specific order (usually ascending or descending).

#### A. Bubble Sort

Bubble Sort is the simplest sorting algorithm. It works by repeatedly stepping through the array, comparing each pair of adjacent items, and swapping them if they are in the wrong order.

*   **Analogy:** Bubbles in water rising to the surface. In each pass, the largest unsorted element "bubbles up" to its correct position at the end of the array.
*   **How it Works:**
    1.  Iterate through the array from the first element to the second-to-last element (this is the outer loop, representing passes).
    2.  In each pass, compare the current element with the next one (this is the inner loop).
    3.  If the current element is greater than the next element, swap them.
    4.  After the first pass, the largest element will be at the very end of the array.
    5.  Repeat the process for the remaining unsorted part of the array (`n-1` passes for an array of size `n`).

*   **Efficiency:** Very slow for large arrays. Not practical for real-world applications but excellent for learning the fundamentals of sorting.

*   **C Implementation:**
    ```c
    #include <stdio.h>

    void bubbleSort(int arr[], int size) {
        int i, j, temp;
        for (i = 0; i < size - 1; i++) {      // Outer loop for passes
            for (j = 0; j < size - i - 1; j++) { // Inner loop for comparisons
                if (arr[j] > arr[j + 1]) {
                    // Swap the elements
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
    ```

#### B. Selection Sort

Selection Sort works by repeatedly finding the minimum element from the unsorted part of the array and putting it at the beginning of the sorted part.

*   **Analogy:** Picking the shortest person out of a line and moving them to the front. Then, finding the next shortest person from the remaining line and moving them to the second position, and so on.
*   **How it Works:**
    1.  Consider the entire array as unsorted.
    2.  Find the smallest element in the unsorted array.
    3.  Swap this smallest element with the element at the very beginning of the unsorted part.
    4.  The first element is now considered sorted.
    5.  Repeat the process for the remaining unsorted part of the array (from the second element onwards) until the entire array is sorted.

*   **Efficiency:** Better than Bubble Sort in some cases, but still inefficient for large datasets.

*   **C Implementation:**
    ```c
    #include <stdio.h>

    void selectionSort(int arr[], int size) {
        int i, j, min_index, temp;
        for (i = 0; i < size - 1; i++) {
            // Assume the first element of the unsorted part is the minimum
            min_index = i;
            
            // Find the true minimum in the rest of the array
            for (j = i + 1; j < size; j++) {
                if (arr[j] < arr[min_index]) {
                    min_index = j;
                }
            }
            
            // Swap the found minimum element with the first element of the unsorted part
            temp = arr[i];
            arr[i] = arr[min_index];
            arr[min_index] = temp;
        }
    }
    ```

#### C. Insertion Sort

Insertion Sort builds the final sorted array one item at a time. It is much more efficient than Bubble and Selection Sort for small or nearly-sorted datasets.

*   **Analogy:** Sorting a hand of playing cards. You pick up one card at a time and insert it into its correct position among the cards you are already holding.
*   **How it Works:**
    1.  Assume the first element is already sorted.
    2.  Pick the next element (the "key").
    3.  Compare the key with the elements in the sorted part (to its left).
    4.  Shift all elements in the sorted part that are greater than the key one position to the right.
    5.  Insert the key into the newly created space.
    6.  Repeat the process until all elements have been inserted into the sorted part.

*   **Efficiency:** A good choice for small arrays or for arrays that are already mostly sorted.

*   **C Implementation:**
    ```c
    #include <stdio.h>

    void insertionSort(int arr[], int size) {
        int i, key, j;
        for (i = 1; i < size; i++) {
            key = arr[i]; // Pick the element to be inserted
            j = i - 1;

            // Move elements of arr[0..i-1] that are greater than key,
            // one position ahead of their current position
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key; // Insert the key
        }
    }
    ```