# get_next_line

> Reading a line from a file descriptor is far too tedious.

## 🧠 Project Overview

This project is part of the 42 school curriculum. It focuses on implementing the `get_next_line` function, a utility that reads and returns one line at a time from a file descriptor. It teaches essential C programming concepts such as static variables and file I/O handling.

## 🚀 Function Prototype

```c
char *get_next_line(int fd);
```

## 🛠️ Features
- Reads from a file descriptor, one line at a time.

- Returns each line including the terminating \n (if present).

- Handles standard input as well as files.

- Efficient buffer-based reading using read().

- Memory-safe (no leaks, no crashes).

- Fully norm-compliant (-Wall -Wextra -Werror).

## 🗂️ File Structure
.\
├── get_next_line.c \
├── get_next_line.h \
├── get_next_line_utils.c \
├── get_next_line_bonus.c \
├── get_next_line_bonus.h \
├── get_next_line_utils_bonus.c \
├── Makefile \

## 🧪 Usage

To compile:
```bash
make            # Compiles mandatory part
make bonus      # Compiles bonus version
```
Example usage:
```c
#include "get_next_line.h"
#include <fcntl.h>
#include <stdio.h>

int main(void)
{
    int fd = open("file.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }

    close(fd);
    return 0;
}
```

## ✅ Bonus Features

- Multi-file descriptor support: Handles multiple open files simultaneously.

- Single static variable: Clean and optimized implementation.

## ❗ Constraints
- No usage of lseek() or global variables.

- No usage of external libraries, including libft.

- Undefined behavior may occur when reading from binary files.

## 📚 What I Learned

- The use of static variables to maintain state across function calls.

- Buffer management and reading files efficiently with read().

- Handling edge cases in input/output operations.

- Modular code design and adherence to strict coding standards.

## 📎 Resources
 - [Static variable explanation](https://en.wikipedia.org/wiki/Static_variable)
