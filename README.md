# Incorrect Use of free() in C

This repository demonstrates a common error in C programming: attempting to free memory allocated on the stack using the `free()` function.  The `free()` function is intended for deallocating memory allocated dynamically using functions like `malloc()`, `calloc()`, or `realloc()`.  Using `free()` on stack-allocated memory leads to undefined behavior, potentially causing program crashes or memory corruption.

## Bug Description

The `bug.c` file contains code that attempts to free a pointer (`ptr`) pointing to a stack-allocated variable (`x`). This is incorrect and results in undefined behavior.

## Solution

The `bugSolution.c` file demonstrates the corrected version.  It removes the incorrect `free()` call, as stack-allocated memory is automatically managed by the system when the function exits.

## How to Compile and Run

1.  Clone this repository.
2.  Compile both `bug.c` and `bugSolution.c` using a C compiler (e.g., GCC):
    ```bash
    gcc bug.c -o bug
    gcc bugSolution.c -o bugSolution
    ```
3.  Run the compiled executables to observe the behavior of each version.

This example serves as a reminder to carefully manage memory allocation and deallocation in C programs to prevent these types of errors.