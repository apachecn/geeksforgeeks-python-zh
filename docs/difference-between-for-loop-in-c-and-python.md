# C 语言中 for 循环与 Python

的区别

> 原文:[https://www . geeksforgeeks . org/c 与 python 循环的区别/](https://www.geeksforgeeks.org/difference-between-for-loop-in-c-and-python/)

**对于循环**，一般用于顺序遍历。它属于确定迭代的范畴。明确的迭代意味着重复的次数是预先明确指定的。然而，对于循环，c 和 python [的工作方式是不同的，尽管两者都用于迭代，但工作方式是不同的。](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)

### [**为丙回路**](https://www.geeksforgeeks.org/c-c-for-loop-with-examples/)

C 中的 For 循环从初始化的值开始，然后检查条件。如果测试表达式被证明为真，则执行 for 下的代码，并且在没有任何异常的情况下执行，更新表达式等式相应地增加或减少变量。

**语法:**

> for(初始化表达式；测试表达式；更新 expr)
> 
> {
> 
> //循环体
> 
> //我们要执行的语句
> 
> }

> ***<u>例 1:</u>***
> 
> for(int I = 1；i < = 10i++)
> 
> {
> 
> printf("%d "，I)；
> 
> }
> 
> **输出**
> 
> *1 2 3 4 5 6 7 8 9 10*
> 
> 每当我大于 10 时，它就停止执行 for 循环的主体。
> 
> ***<u>例 2:</u>***
> 
> for(int I = 1；i < = 10i++)
> 
> {
> 
> i=i+1
> 
> printf("%d "，I)；
> 
> }
> 
> **输出:**
> 
> *2 4 6 10*
> 
> //因为每当我的 body 增加 1，并且每当我大于 10 时，它就停止执行。

**程序**

## C

```py
//Program to show working of for loop in C

#include <stdio.h>

int main()
{

    // code
    for (int i = 1; i <= 10; i++)
    {
      // it will have effect on termination
      // condition
      i=i+1;
      printf("%d\n", i);
    }
    return 0;
}
```

**输出:**

> Two
> 
> four
> 
> six
> 
> eight
> 
> Ten

### [**为 Python 中的循环**](https://www.geeksforgeeks.org/python-for-loops/)

python 中的 For 循环适用于给定的范围。随声明一起给出的变量名从初始值开始改变其值，然后相应地递增或递减。该循环比结束值少一个。

**语法**

> 对于范围(x，y，z)中的值

哪里，

x=初始值

y =最终值

z =增量/减量

> ***<u>例 1:</u>***
> 
> 对于范围(1，11)中的 I:
> 
> 打印(一)
> 
> **输出:**
> 
> 1 2 3 4 5 6 7 8 9 10
> 
> //如我们所见，它迭代了 10 次，即(11-1)=10 次
> 
> ***<u>例 2:</u>***
> 
> 对于范围(1，11)中的 I:
> 
> I = 1+1；
> 
> 打印(一)
> 
> **输出:**
> 
> 2 3 4 5 6 7 8 9 10 11
> 
> //虽然我们在 for body 中递增 I，但它仍在迭代 10 次。

**程序**

## 蟒蛇 3

```py
# program to show for loop in python

for i in range(1, 11):

    # it will have no effect in termination
    # condition
    i = i+1

    # it will always iterate for 10 times as
    # given in range
    print(i)
```

**输出**

> Two
> 
> three
> 
> four
> 
> five
> 
> six
> 
> seven
> 
> eight
> 
> nine
> 
> Ten
> 
> Eleven

**c 与 python 的区别为循环**

<figure class="table">

| **C** | T1】巨蟒 T3】 |
| --- | --- |
| C 语言中的 for 循环重复执行一条语句或一个语句块，直到指定的表达式计算为 false | Python 中的 foreach 循环为数组或对象集合中的每个元素重复一组嵌入语句。您不需要指定循环边界最小值或最大值。 |
| 表达式的求值决定执行 | 不需要这样的评估 |
| 必须明确指定递增或递减操作 | 如果没有给定，则假定为+1 |

</figure>