# **Unit 5: Functions & Pointers - Master Notes**

## **1. Functions**

### **A. Definition & Purpose**

A function is a self-contained block of statements that performs a specific task.

  * **Why use them?**
    1.  **Modularity:** Breaks complex problems into smaller, manageable pieces (Divide and Conquer).
    2.  **Reusability:** Write code once, use it multiple times.
    3.  **Debugging:** Easier to isolate and fix errors.

### **B. The Three Elements of a Function**

To use a function effectively, you need three parts:

1.  **Function Declaration (Prototype):**

      * Tells the compiler about the function's name, return type, and parameters *before* `main()`.
      * *Syntax:* `return_type function_name(parameter_list);`
      * *Example:* `int add(int x, int y);`

2.  **Function Call:**

      * The point where the function is invoked. Control jumps from `main` to the function.
      * *Syntax:* `variable = function_name(arguments);`
      * *Example:* `sum = add(5, 10);`

3.  **Function Definition:**

      * The actual body of the code that executes.
      * *Syntax:*
        ```c
        return_type function_name(parameter_list) {
            // body of function
            return value;
        }
        ```

### **C. Types of Arguments**

  * **Actual Arguments:** The values passed *during the function call* (e.g., `add(a, b)` — here `a` and `b` are actual).
  * **Formal Arguments:** The variables declared *in the function definition* that receive the values (e.g., `int add(int x, int y)` — here `x` and `y` are formal).

-----

## **2. Parameter Passing Techniques**

This is a very important interview/exam topic.

### **A. Call by Value**

  * **Mechanism:** The **value** of the actual argument is copied into the formal argument.
  * **Effect:** Changes made inside the function **DO NOT** affect the original variable in `main`.
  * **Memory:** Separate memory is allocated for formal arguments.
  * *Example:* Normal variables.

### **B. Call by Reference**

  * **Mechanism:** The **address** (pointer) of the actual argument is passed to the function.
  * **Effect:** Changes made inside the function **DIRECTLY AFFECT** the original variable.
  * **Memory:** The function works on the original memory location.
  * *Usage:* Required when a function needs to return more than one value or modify the input.

**Comparison:**

| Feature | Call by Value | Call by Reference |
| :--- | :--- | :--- |
| **Input** | Values | Addresses (`&var`) |
| **Receiver** | Variables (`int x`) | Pointers (`int *x`) |
| **Original Data** | Unchanged | Modified |

-----

## **3. Recursion**

A function is **Recursive** if it calls itself within its own body.

  * **Logic:** It breaks a problem into smaller instances of the same problem.
  * **Requirements:**
    1.  **Base Case:** A condition to **stop** the recursion (otherwise, it loops infinitely and crashes the stack).
    2.  **Recursive Step:** The function calling itself with a value closer to the base case.
  * *Classic Example:* Factorial ($n! = n \times (n-1)!$).

-----

## **4. Storage Classes**

Storage classes determine the **Scope** (visibility), **Lifetime**, **Location**, and **Default Value** of a variable.

| Class | Keyword | Storage Location | Default Value | Scope | Lifetime |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Automatic** | `auto` | RAM (Stack) | Garbage | Local to block | Until block ends |
| **Register** | `register` | CPU Register | Garbage | Local to block | Until block ends |
| **Static** | `static` | RAM | Zero | Local to block | **Persists** between calls |
| **External** | `extern` | RAM | Zero | Global (All files) | Entire program runtime |

> **Note:** `register` is a request to the CPU for fast access; if registers are full, it defaults to `auto`. `static` variables remember their value even after the function finishes execution.

-----

## **5. Pointers**

### **A. Definition**

A **Pointer** is a variable that stores the **memory address** of another variable.

### **B. Operators**

  * **`&` (Address of):** Returns the memory address of a variable.
  * **`*` (Dereference/Indirection):** Returns the **value** stored at a specific address.

### **C. Declaration & Usage**

```c
int x = 10;
int *ptr;    // Declaration: ptr is a pointer to an integer
ptr = &x;    // Initialization: ptr now holds the address of x

printf("%d", *ptr); // Prints 10 (Value at address)
printf("%u", ptr);  // Prints memory address (e.g., 64224)
```

### **D. Pointer Arithmetic**

You can add/subtract integers to/from pointers.

  * **Formula:** `ptr + 1` does not add 1 byte. It adds `1 * sizeof(data_type)`.
      * If `ptr` is `int` (4 bytes) and points to `1000`, `ptr + 1` points to `1004`.
      * If `ptr` is `char` (1 byte) and points to `1000`, `ptr + 1` points to `1001`.

### **E. Pointers and Arrays**

Arrays and pointers are closely related.

  * The **Array Name** (e.g., `arr`) acts as a **constant pointer** to the first element (`&arr[0]`).
  * **Accessing Elements:**
      * `arr[i]` is internally interpreted by the compiler as `*(arr + i)`.
      * This is why array indexing starts at 0.

### **F. Double Pointers (Pointer to Pointer)**

A variable that stores the address of another pointer.

  * *Syntax:* `int **pptr;`
  * *Logic:* `pptr` holds address of `ptr`; `ptr` holds address of `var`; `var` holds value.

-----

## **6. Returning Multiple Values**

Standard functions in C can only return **one** value using `return`. To return multiple values, we use:

1.  **Pointers:** Pass variables by reference, modify them, and the changes persist in `main`.
2.  **Structures:** Bundle multiple values into a structure and return the structure.
3.  **Global Variables:** (Not recommended) Modify variables accessible everywhere.

-----
