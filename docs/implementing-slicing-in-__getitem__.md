# 在 __getitem__

中实现切片

> 原文:[https://www . geesforgeks . org/impering-slicing-in-_ _ getitem _ _/](https://www.geeksforgeeks.org/implementing-slicing-in-__getitem__/)

**__getitem__** 方法用于访问列表项、数组元素、字典条目等。**切片**是 Python 中的一个构造函数，它创建切片对象来表示范围(开始、停止、步进)指定的一组索引。`__getitem__ method`可以在一个类中实现，切片的行为可以在其中定义。

**语法:**

```py
__getitem__(slice(start, stop, step))
```

**参数:**

*   **切片():**构造函数创建切片对象。
*   **开始:**指定开始索引的整数。它是可选的，默认值为 0。
*   **stop:** 指定结束索引的整数。
*   **步骤:**指定切片步骤的整数。可选，
    默认为 1。

**例 1:**

```py
# abcde is string can be 
# an array as well.
sliced ='abcde'.__getitem__(slice(0, 2, 1)) 
print(sliced)
```

**输出**

```py
ab
```

**解释:**
字符串 **abcde** 以起始索引 0 和停止索引 2 以及步长索引 1 进行切片，因此它从字符串中切片 **ab** 并打印输出。

**例 2:**

```py
class Demo:
    def __getitem__(self, key):

        # print a[1], a[1, 2], 
        # a[1, 2, 3]
        print(key)

        return key
a = Demo()

# => slice 1
a[1]

# => slice(1, 2)
a[1, 2]

# => (1, 2, 3)
a[1, 2, 3]
```

**输出**

```py
1
(1, 2) 
(1, 2, 3)

```

**说明:**
类演示有`__getitem__`方法，切片用逗号分隔。键打印通过变量 a 在类中传递的切片对象。