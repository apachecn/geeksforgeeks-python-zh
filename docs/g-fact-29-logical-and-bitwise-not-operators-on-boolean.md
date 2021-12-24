# G-Fact 19(布尔逻辑和按位非运算符)

> 原文:[https://www . geeksforgeeks . org/g-fact-29-逻辑和按位非布尔运算符/](https://www.geeksforgeeks.org/g-fact-29-logical-and-bitwise-not-operators-on-boolean/)

包括 C、C++、Java 和 Python 在内的大多数语言都提供布尔类型，可以设置为**假**或**真**。
考虑以下使用**逻辑非(或！)**运算符 on boolean。

<gfg-tab role="tab" slot="tab" id="gfg-tab-0">C/C++</gfg-tab><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="C"></gfg-panel>

```
 // A C/C++ program that uses Logical Not or ! on boolean
#include <stdio.h>
#include <stdbool.h>

int main()
{
    bool a = 1, b = 0;
    a = !a;
    b = !b;
    printf("%d\n%d", a, b);
    return 0;
}
// Output: 0
//         1 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program that uses Logical Not or ! on boolean
import java.io.*;

class GFG
{
    public static void main (String[] args)
    {
        boolean a = true, b = false;
        System.out.println(!a);
        System.out.println(!b);
    }
}
// Output: False
//         True
```