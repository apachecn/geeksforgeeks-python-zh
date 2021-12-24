# Python |克隆或复制列表

> 原文:[https://www.geeksforgeeks.org/python-cloning-copying-list/](https://www.geeksforgeeks.org/python-cloning-copying-list/)

在本文中，我们将介绍在 Python 中复制或克隆列表的各种方法。这些不同的复制方式需要不同的执行时间，所以我们可以根据时间进行比较。

1.  **Using slicing technique**
    This is the easiest and the fastest way to clone a list. This method is considered when we want to modify a list and also keep a copy of the original. In this we make a copy of the list itself, along with the reference. This process is also called cloning. This technique takes about 0.039 seconds and is the fastest technique.

    ```py
    # Python program to copy or clone a list
    # Using the Slice Operator
    def Cloning(li1):
        li_copy = li1[:]
        return li_copy

    # Driver Code
    li1 = [4, 8, 2, 10, 15, 18]
    li2 = Cloning(li1)
    print("Original List:", li1)
    print("After Cloning:", li2)
    ```

    输出:
    原始列表:[4，8，2，10，15，18]
    克隆后:[4，8，2，10，15，18]

2.  **使用 extend()方法**
    可以使用 extend()函数将列表复制到新列表中。这会将可迭代对象的每个元素(例如，一个列表)附加到新列表的末尾。这大约需要 0.053 秒来完成。
    示例:

```py
# Python code to clone or copy a list
# Using the in-built function extend()
def Cloning(li1):
    li_copy = []
    li_copy.extend(li1)
    return li_copy

# Driver Code
li1 = [4, 8, 2, 10, 15, 18]
li2 = Cloning(li1)
print("Original List:", li1)
print("After Cloning:", li2)
```

输出:

```py
Original List: [4, 8, 2, 10, 15, 18]
After Cloning: [4, 8, 2, 10, 15, 18]
```

8.  **Using the list() method**
    This is the simplest method of cloning a list by using the builtin function list(). This takes about 0.075 seconds to complete.
    Example:

    ```py
    # Python code to clone or copy a list
    # Using the in-built function list()
    def Cloning(li1):
        li_copy = list(li1)
        return li_copy

    # Driver Code
    li1 = [4, 8, 2, 10, 15, 18]
    li2 = Cloning(li1)
    print("Original List:", li1)
    print("After Cloning:", li2)
    ```

    输出:

    ```py
    Original List: [4, 8, 2, 10, 15, 18]
    After Cloning: [4, 8, 2, 10, 15, 18]
    ```

9.  **使用浅拷贝的方法**
    使用 copy.copy 的这种拷贝方法在文章[浅拷贝](https://www.geeksforgeeks.org/copy-python-deep-copy-shallow-copy/)中有很好的解释。这大约需要 0.186 秒来完成。
10.  **Using list comprehension**
    The method of list comprehension can be used to copy all the elements individually from one list to another. This takes around 0.217 seconds to complete.

    ```py
    # Python code to clone or copy a list
    # Using list comprehension
    def Cloning(li1):
        li_copy = [i for i in li1]
        return li_copy

    # Driver Code
    li1 = [4, 8, 2, 10, 15, 18]
    li2 = Cloning(li1)
    print("Original List:", li1)
    print("After Cloning:", li2)
    ```

    输出:

    ```py
    Original List: [4, 8, 2, 10, 15, 18]
    After Cloning: [4, 8, 2, 10, 15, 18]
    ```

11.  **Using the append() method**
    This can be used for appending and adding elements to list or copying them to a new list. It is used to add elements to the last position of list. This takes around 0.325 seconds to complete and is the slowest method of cloning.

    ```py
    # Python code to clone or copy a list
    # Using append()
    def Cloning(li1):
        li_copy =[]
        for item in li1: li_copy.append(item)
        return li_copy

    # Driver Code
    li1 = [4, 8, 2, 10, 15, 18]
    li2 = Cloning(li1)
    print("Original List:", li1)
    print("After Cloning:", li2)
    ```

    输出:

    ```py
    Original List: [4, 8, 2, 10, 15, 18]
    After Cloning: [4, 8, 2, 10, 15, 18]
    ```

12.  **Using the copy() method**
    The inbuilt method copy is used to copy all the elements from one list to another. This takes around 1.488 seconds to complete.
    Example:

    ```py
    # Python code to clone or copy a list
    # Using bilt-in method copy()
    def Cloning(li1):
        li_copy =[]
        li_copy = li1.copy()
        return li_copy

    # Driver Code
    li1 = [4, 8, 2, 10, 15, 18]
    li2 = Cloning(li1)
    print("Original List:", li1)
    print("After Cloning:", li2)
    ```

    输出:

    ```py
    Original List: [4, 8, 2, 10, 15, 18]
    After Cloning: [4, 8, 2, 10, 15, 18]
    ```

13.  **使用深度复制**
    的方法这种复制方法在[深度复制](https://www.geeksforgeeks.org/copy-python-deep-copy-shallow-copy/)一文中有很好的解释。这大约需要 10.59 秒来完成，是最慢的克隆方法。

参考[堆栈溢出](https://stackoverflow.com/questions/2612802/how-to-clone-or-copy-a-list)。