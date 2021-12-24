# CBSE 11 级 C++ |样纸-1

> 原文:[https://www . geesforgeks . org/cbse-class-11-c-sample-paper-1/](https://www.geeksforgeeks.org/cbse-class-11-c-sample-paper-1/)

说明:

{ 1 }所有问题都是强制性的。
{ 2 }编程语言:c++

**问题 1 [A]解释计算机的功能组件？2**
有一些帮助计算机工作周期的基本组件，它们被称为计算机的功能组件。它们是:
1)输入系统
2)记忆组织
3)输出系统
参考:[计算机的功能组件](https://www.geeksforgeeks.org/functional-components-of-a-computer/)

**【B】写应用软件和系统软件的不同。2**

**系统软件:**
1)这些是直接允许用户与计算机系统的硬件组件交互的软件。
2)系统软件可以称为计算机系统的主要软件，因为它处理运行硬件的主要部分。
3)本系统软件可进一步分为:
操作系统
语言处理器

**应用软件:**
1)这些是用来运行以完成特定动作和任务的基本软件。
2)这些是专用软件，专门执行简单单一的任务。
3)分为两类:
通用应用软件
专用应用软件

参考:[软件概念](https://www.geeksforgeeks.org/software-concepts/)

**【C】定义混合计算机？1**
混合计算机使用模拟和数字技术来提供模拟计算机的速度和数字计算机的精度。这些计算机接受数字或模拟信号，但必须进行大量的数据转换，从数字到模拟，从模拟到数字。混合计算机被用作复杂模拟的经济有效的手段。

**【D】操作系统发挥什么功能来管理内存。1**
在计算机中，中央处理器和输入输出设备都与内存交互。当一个程序需要被执行时，它被加载到主存储器中，直到执行完成。操作系统常用的内存管理技术有:
**分区:**总内存分为大小相同或不同的各种分区。这有助于在内存中容纳大量程序。
**虚拟内存:**这是操作系统使用的一种技术，通过这种技术，用户可以加载比计算机主内存大的程序。

**问题 2【答】写出逻辑错误和语法错误的区别 2**
**逻辑错误:**这些类型的错误提供不正确的输出，但看起来没有错误，被称为逻辑错误。这些错误完全取决于程序员的逻辑思维
**语法错误:**当你违反编写 C/C++语法的规则时出现的错误被称为语法错误。此编译器错误表明在编译代码之前必须修复一些问题。
[逻辑错误和语法错误](https://www.geeksforgeeks.org/errors-in-cc/)。

**【B】什么叫程序的健壮性。2**
健壮性是计算机程序在执行过程中处理错误和处理错误输入的能力。因此，为了更加健壮，程序应该能够处理错误输入的数据，并在所有类型的输入上正确执行。

**【C】什么是守护码。1**
计算机编程语言中的 Guard 代码是对完整性先决条件的检查，用于避免执行过程中的错误。

**【D】算法翻译成程序的过程是什么，叫做？1**
用特定语言编码的过程被称为将算法翻译成程序。

**【E】好的节目有哪些特点？2**
应该开发一个程序来确保计算机的正常功能，并且应该易于理解。一个计算机程序应该具有一些重要的特征，这些特征如下:
**灵活性:一个程序应该足够灵活，能够处理大部分的变化，而不必重写整个程序。
**用户友好**:所有类型用户都能轻松理解的程序。此外，除了使程序易于理解和修改之外，用户输入数据和显示结果的适当信息。
**可移植性**:可移植性是指一个应用程序在不同平台(操作系统)上运行的能力，无论是否有最小的改变。
**可靠性**:是程序即使在计算机系统中有哪怕很小的变化，也能准确地完成其预定功能的能力。
**自文档化代码**:对标识符(变量和方法)使用合适名称的源代码称为自文档化代码。**

****【F】说出两种编译错误？2****

**1) **语法错误**:这些编译器错误表示在可以编译代码之前必须修复的东西。所有这些错误都被编译器检测到，因此被称为编译时错误。
最常见的语法错误是:
缺少括号(})
打印变量值而不声明它
缺少分号等
2) **逻辑错误**:在编译和执行程序时，当给定某些输入值时，无法获得所需的输出。
3) **运行时错误**:编译成功后程序执行(运行时)发生的错误称为运行时错误。最常见的运行时错误之一是除以零，也称为除法错误。**

****q . 3【A】命名以下所属的头文件:2**
1。 **getch()** : conio.h
2。 **isdigit()** : ctype.h
3。 **sqrt()** : math.h
4。 **atoi()** : stdlib.h**

****【B】编写以下代码的输出:2****

```py
int val, n = 1000;
cin >> val;
res = n + val > 1500 ? 100 : 200;
cout << res;
```

****i)如果输入为 1000。** : 100
**ii)如果输入是 200。** : 200**

****【C】写出等价的 c++表达式 2**
**(1)p = 2(l+b)**
表达式:p = 2 *(l+b)；**

****(2) z=2(p/q) <sup>2</sup>**
表达式:z = 2 *幂((p/q)，2))或 2*p/q*p/q**

****(3)s = 1/2mv<sup>2</sup>T3
表达式:1/2 * m * v * v；或者 s = 1/2 * m *幂(v，2)；****

****(4) x=-b+？(b <sup>2</sup> -4ac) /2a**
表达式:x =-b+ sqrt(b * B- 4 * a * c)/2 * a；或者 x=-b+sqrt(pow(b，2)-4 * a * c)/2 * a；**

****【D】写出关键字和标识符的区别。2****

****[关键词](https://www.geeksforgeeks.org/variables-and-keywords-in-c/) :**
1)关键词是编程语言中预先定义或保留的词
2)每个关键词都意味着执行程序中的特定功能。因为关键字是编译器的参考名称，所以不能用作变量名。
3) C 语言支持 32 个关键字，而在 C++中除了 C Keywords 之外，还有 31 个附加关键字。
**[标识符](https://www.geeksforgeeks.org/cc-tokens/) :**
1)标识符用作变量、函数和数组命名的通用术语。
2)这些是用户定义的名称，由任意长的字母和数字序列组成，以字母或下划线(_)作为第一个字符。标识符名称的拼写和大小写必须不同于任何关键字。
3)在命名 c 标识符时，应该遵循某些规则:
它们必须以字母或下划线(_)开头。
它们必须仅由字母、数字或下划线组成。不允许使用其他特殊字符。
不应该是关键词。
不得包含空格。
只要只有前 31 个字符有意义，就最多 31 个字符。**

****Q4【A】画一个[流程图](https://www.geeksforgeeks.org/an-introduction-to-flowcharts/)，打印三个给定编号中最小的 2 个****

****【B】删除语法错误后重写以下程序。2****

```py
#include <iostream.h>
Void main()
{
    const MAX = 0; // Error
    int a, b;
    cin << a >> b; // Error
    if (a > b)
        MAX = a;
    for (x = 0; x < MAX; x++) // x undeclared error.
        cout << x;
}
```

```py
void main()
{
    const int MAX = 0;
    int a, b;
    cin >> a >> b;
    if (a > b)
        MAX = a;
    for (int x = 0; x < MAX; x++) // x is an undefined symbol
        cout << x;
```

****【C】用 [c++写程序打印斐波那契数列](https://www.geeksforgeeks.org/program-to-print-first-n-fibonacci-numbers/) : 0，1，1，2，3，5，8..3****

```py
#include <iostream>
using std::cout;
void fib(int n)
{
    int a = 0, b = 1, c;
    if (n >= 0)
        cout << a << " ";
    if (n >= 1)
        cout << b << " ";
    for (int i = 2; i <= n; i++) {
        c = a + b;
        cout << c << " ";
        a = b;
        b = c;
    }
}

// Driver code
int main()
{
    int n;
    cout << "Enter the value of n";
    cin >> n;
    fib(n);
    return 0;
}
```

****【D】用 [c++写一个程序，找出给定 no](https://www.geeksforgeeks.org/program-for-factorial-of-a-number/) 的阶乘。3****

```py
#include <iostream>
using namespace std;

int fact(int n)
{
    if (n == 1 || n == 0)
        return 1;
    return n * fact(n - 1);
}

int main()
{
    int n;
    cout << "Enter the number";
    cin >> n;
    cout << "factorial of n is" << fact(n);
    return 0;
}
```

****Q.5[A]用 c++编写一个程序，用连字符替换字符串中的每个空格。2****

```py
#include <iostream>
#include <string.h>
using namespace std;

void replace(char* str, int len)
{
    for (int i = 0; i < len; i++) {
        if (str[i] == ' ')
            str[i] = '_';
    }
    cout << str;
}

int main()
{
    char str[] = "geeks for geeks";
    int len = strlen(str);
    replace(str, len);
    return 0;
}
```

****【B】求以下数组的元素总数和总大小:2
(I)int student[20](ii)float A[4][5]****

**I)元素总数= 20
总大小= 20*2 = 40 字节
ii)元素总数=4*5=20
总大小=4*4*5= 80 字节**

****【C】删除语法错误后重写以下程序 2****

```py
#include <iostream.h>
main()
{
    int sum[2, 4];
    for (i = 0; i < 2; i++)
        for (j = 0; j <= 3; i++) {
            cout << sum;
        }
```

****【D】找出以下程序的输出:4****

```py
#include <iostream.h>
main()
{
    int a[5] = { 5, 10, 15, 20, 25 };
    int i, j, k = 1, m;
    i = ++a[1];
    j = a[2]++;
 m= a[i++
};
cout << i << j << k << m;
}
```

****【E】用 c++写程序求矩阵的行和列和。3****

```py
#include <iostream>
using namespace std;
#define MAX 10

int sum(int a[][MAX], int n)
{
    int i, j;
    int sum = 0;
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            if (i == 0 || j == 0 || i == (n - 1) || j == (n - 1))
                sum = sum + a[i][j];
        }
    }
    cout << sum;
    return 0;
}

int main()
{
    int a[10][10];
    int n, i, j;
    cout << "enter the dimension of matrix";
    cin >> n;
    cout << "enter the elements";
    for (i = 0; i < n; i++)
        for (j = 0; j < n; j++)
            cin >> a[i][j];
    sum(a, n);
    return 0;
}
```

****[F] Give the proper array declaration for the following :- 2****(i) Declare an integer array A which can hold 30 values.****(ii) declare a two dimensional array called MIN, 4* 5 of integer.**(i) int A[30];(ii)int MIN[4][5];

**问题 6【答】使用[功能](https://www.geeksforgeeks.org/c-language-2-gq/functions-gq/)有哪三个步骤。3**
正确使用函数的三个步骤是:
i)函数声明:声明函数原型，让编译器知道函数的参数和返回类型
ii)函数定义:函数的整个主体和功能都是在函数块内部设计和编写的。
iii)函数调用:最后在定义和声明一个函数后，在驱动程序/主函数内部调用它来执行所需的功能。

**【B】找到以下程序的输出:2**

```py
#include <iostream.h>
void Execute(int& x, int y = 200)
{
    int temp = x + y;
    x + = temp;
    if (y != 200)
        cout << temp << x << y;
}
main()
{
    int a = 50, b = 20;
    Execute(a, b);
    cout << a << b;
}
```

输出:

(一)a= 120
(二)b=20

**【C】用 C++写一个函数，有 2 个整数类型的参数 x 和 n，结果类型为 float，求以下级数的和:-
1 + x/2！+ x <sup>2</sup> /3！+…………………..+x <sup>n</sup> /(n+1)！3**

```py
#include <iostream>
#include <math.h>

int fact(int z)
{
    if (z == 1)
        return 1;
    return x * fact(x - 1);
}

double sum(int x, int n)
{
    double i, total = 1.0;
    for (i = 1; i <= n; i++)
        total = total + (pow(x, i) / fact(i + 1));
    return total;
}

// Driver code
int main()
{
    int x;
    int n;
    cout << "" enter x and n ";
                               cin
                               >> x >> n printf("%.2f", sum(x, n));
    return 0;
}
```

**【D】编写程序，利用函数计算 n 个自然数之和。
3**

```py
#include <iostream>
using namespace std;
int sum(int n)
{
    int i, sum;
    sum = 0;
    for (i = 1; i <= n; i++) {
        sum = sum + i;
    }
    cout <<”sum of natural numbers is”<< sum;
}

int main()
{
    int n;
    cout << "enter the range of sum";
    cin >> n;
    sum(n);
    return 0;
}
```

**问题 7[A]将下列代码转换为其二进制等价代码。4**
**(一)(84) <sub>10</sub> =(？)<sub>2</sub>**
=(1010100)<sub>2</sub>
**(ii)(2c 9)<sub>16</sub>=(？)<sub>10</sub>**
=(2c 9)<sub>16</sub>=(001011001001)<sub>2</sub>=(713)<sub>10</sub>
**(iii)(101010)<sub>2</sub>=(？)<sub>10</sub>**
=(42)<sub>10</sub>
**(iv)(3674)<sub>8</sub>=(？)<sub>2</sub>T42
=(1111011100)<sub>2</sub>**

参考:[数字系统和基数转换](https://www.geeksforgeeks.org/number-system-and-base-conversions/)

**【B】用 1 的补码形式表示-4。1**

**【C】公交车的功能是什么。1**
总线是一组承载信息的导线，所有外设都通过总线与微处理器相连。

**【D】写两种类型的缓存。2**
两种类型的缓存是 L1 缓存和 L2 缓存。

**【D】SRAM 和 DRAM 的写入差异。2**
SRAM 访问时间更短。所以比 DRAM 快。
SRAM 成本更高。
DRAM 访问时间更长。所以比 DRAM 慢。
DRAM 更便宜。

参考: [SRAM 和 DRAM](https://www.geeksforgeeks.org/different-types-ram-random-access-memory/)**