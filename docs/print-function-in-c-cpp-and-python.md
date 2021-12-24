# C、C++和 Python 中的打印功能

> 原文:[https://www . geesforgeks . org/print-function-in-c-CPP-and-python/](https://www.geeksforgeeks.org/print-function-in-c-cpp-and-python/)

本文的任务是观察 [C](https://www.geeksforgeeks.org/c-programming-language/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 和 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中**打印**函数的行为。打印功能用于在屏幕上显示内容。

**方式:**

*   Some characters are stored in the [integer](https://www.geeksforgeeks.org/c-data-types/) value inside the printf function.
*   Print the values and counts of characters.
*   Give examples of different uses of printf ().

下面是 C 程序打印里面的 printf:

## C

```py
// C program printing inside printf()

#include <stdio.h>

// Driver Code
int main()
{
    // Stores no of characters printed by printf
    int val = printf("GeeksForGeeks\n");

    // Print the count of characters
    printf("Int printf(\"GeeksForGeeks\\n \") = %d\n", val);

    return 0;
}
```

输出

```py
GeeksForGeeks
Int printf("GeeksForGeeks\n ") = 14
```