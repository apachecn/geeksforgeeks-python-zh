# 不同编程语言中的格式说明符

> 原文:[https://www . geesforgeks . org/format-不同编程语言中的说明符/](https://www.geeksforgeeks.org/format-specifiers-in-different-programming-languages/)

### [<u>C 中格式化</u>](https://www.geeksforgeeks.org/format-specifiers-in-c/)

[![](img/91d990eefe975ae7c340db2d4edf6ffb.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200519122152/CProgramming.png)

在 C 语言中[格式说明符](https://www.geeksforgeeks.org/format-specifiers-in-c/)用于输入和输出。这是一种在使用 [scanf()](https://www.geeksforgeeks.org/scanf-and-fscanf-in-c-simple-yet-poweful/) 进行输入或使用 [printf()](https://www.geeksforgeeks.org/return-values-of-printf-and-scanf-in-c-cpp/) 进行打印时告诉编译器变量中的数据类型的方法。下面是 C 语言中的一些格式说明符:

*   **%d 或%i:** 整数格式说明符
*   **%c:** 字符格式说明符
*   **%f:** 浮点格式说明符。
*   **%s:** 字符串格式说明符。
*   **%lf:** 双格式说明符。
*   **%e 或%E:** 浮点格式说明符(指数)。

在 C 语言编程中，我们使用 scanf()进行格式化输入，使用 printf()进行格式化输出，[get()或 getchar()](https://www.geeksforgeeks.org/difference-getchar-getch-getc-getche/) 进行未格式化输入，[put()或 putchar()](https://www.geeksforgeeks.org/putchar-function-in-c/) 进行未格式化输出。
下面是用 C 语言说明一些格式说明符的程序:

## C

```py
// C program to illustrate format
// specifiers in C
#include <stdio.h>

// Driver Code
int main()
{
    int N = 10;
    double F = 42.152;

    // Integer formatted output
    printf("%d \n", N);

    // Exponential formatted output
    printf("%e \n", F);

    // Unformatted String Output
    puts("Welcome to GeeksforGeeks!");
}
```

**Output:** 

```py
10 
4.215200e+01 
Welcome to GeeksforGeeks!
```