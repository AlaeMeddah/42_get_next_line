# Get Next Line -- Reading a File Line by Line in C

**get_next_line** is a 42 project that teaches you how to read from a
file descriptor one line at a time using low-level system calls.

The goal is to implement: - A function that returns **exactly one line
per call** - A mechanism to handle partial reads using a **static
variable** - A solution that works with **any BUFFER_SIZE**

------------------------------------------------------------------------

## 📌 Mandatory Part

### **Function**

``` c
char *get_next_line(int fd);
```

### **Files to Submit**

-   `get_next_line.c`
-   `get_next_line_utils.c`
-   `get_next_line.h`

### **Behavior**

-   Returns **one full line**, including the `\n` if present.
-   Returns **NULL** if:
    -   Nothing is left to read
    -   An error occurs
-   Should work with files **and standard input (stdin)**.
-   Must use:
    -   `read`
    -   `malloc`
    -   `free`
-   **No libft**, no `lseek`, no global variables.

### **Compilation**

Example:

    cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 *.c

The `BUFFER_SIZE` will be changed by evaluators.\
Your code must handle all cases:
- `BUFFER_SIZE = 1`
- `BUFFER_SIZE = 9999`
- `BUFFER_SIZE = 10000000`

------------------------------------------------------------------------

## 🧠 Key Concepts Learned

-   How file descriptors work in Linux
-   Using `read()` efficiently
-   Handling buffers and leftover text
-   Working with a **static variable** to keep state between calls
-   Extracting substrings and reallocating memory manually
-   Ensuring no memory leaks and freeing correctly on errors
-   Why reading "as little as possible" matters
-   Line-by-line file processing without loading the entire file

------------------------------------------------------------------------

## ⭐ Bonus Part

If the mandatory part is perfect:

### Additional Requirements

-   Only **one static variable** used for all descriptors
-   Handle **multiple file descriptors** independently\
    → `get_next_line(fd1)` should not break reading from `fd2`

### Extra Files

-   `get_next_line_bonus.c`
-   `get_next_line_bonus.h`
-   `get_next_line_utils_bonus.c`

------------------------------------------------------------------------

## ✅ Summary

**get_next_line** is a foundational project that deepens understanding
of: - memory management\
- file handling\
- persistent state\
- edge cases in input processing

It prepares you for future projects like **minishell**, where reading
input line‑by‑line is essential.
