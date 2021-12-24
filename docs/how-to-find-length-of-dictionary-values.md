# 如何求字典值的长度？

> 原文:[https://www . geesforgeks . org/如何查找字典长度值/](https://www.geeksforgeeks.org/how-to-find-length-of-dictionary-values/)

在 Python 中，[字典](https://www.geeksforgeeks.org/python-dictionary/)是无序数据值的集合。字典也是可变的和有索引的。字典保存键:值对，它们写在花括号内。每个**键:值**对将键映射到其关联值。

这里我们使用 [isinstance()](https://www.geeksforgeeks.org/python-isinstance-method/) 方法检查值的类型是否是列表、int、str、tuple 等。`isinstance()`方法，Python 中的内置方法。如果传递的对象是否是给定类的实例，它将返回一个布尔值。

让我们讨论不同的方法来找到字典值的长度。

**注意:**在下面的方法中，字符串值的长度是取一。

**操作员使用的方法#1**

**例:1**

```
# Python program to find the 
# length of dictionary values

def main():

    # Defining the dictionary
    dict1 = {'a':[1, 2, 3],
             'b'🙁1, 2, 3),
             'c':5,
             'd':"nopqrs",
             'e':["A", "B", "C"]}

    # Initialize count 
    count = 0

    # using in operator 
    for k in dict1:

        # Check the type of value 
        # is int or not
        if isinstance(dict1[k], int):
            count += 1

        # Check the type of value 
        # is str or not
        elif isinstance(dict1[k], str):
            count += 1
        else:
            count += len(dict1[k])

    print("The total length of value is:", count)

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

```
The total length of value is: 11
```

**例:2**

```
# Python program to find the
# length of dictionary values

def main():

    # Defining the dictionary
    dict1 = {'A':"abcd",
             'B':set([1, 2, 3]), 
             'C'🙁12, "number"), 
             'D':[1, 2, 4, 5, 5, 5]}

    # Create a empty dictionary
    dict2 = {}

    # using in operator
    for k in dict1:

        # Check the type of value
        # is int or not
        if isinstance(dict1[k], int):
            dict2[k] = 1

        # Check the type of value 
        # is str or not
        elif isinstance(dict1[k], str):
            dict2[k] = 1

        else:
            dict2[k] = len(dict1[k])

    print("The length of values associated\
    with their keys are:", dict2)
    print("The length of value associated\
    with key 'B' is:", dict2['B'])

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

> 与其键关联的值的长度为:{“A”:1，“B”:3，“C”:2，“D”:6 }
> 与键“B”关联的值的长度为:3

**方法 2** 使用列表理解

```
# Python program to find the 
# length of dictionary values

def main():

    # Defining the dictionary
    dict1 = {'a':[1, 2, 3],
           'b'🙁1, 2, 3),
           'c':5,
           'd':"nopqrs",
           'e':["A", "B", "C"]}

    # using list comprehension
    count = sum([1 if isinstance(dict1[k], (str, int))
                 else len(dict1[k]) 
                 for k in dict1])

    print("The total length of values is:", count)

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

```
The total length of values is: 11
```

**方法#3** 使用词典理解

```
# Python program to find the 
# length of dictionary values

def main():

    # Defining the dictionary
    dict1 = {'A': "abcd",
             'B': set([1, 2, 3]),
             'C': (12, "number"),
             'D': [1, 2, 4, 5, 5, 5]}

    # using dictionary comprehension
    dict2 = {k:1 if isinstance(dict1[k], (str, int)) 
             else len(dict1[k])
             for k in dict1}

    print("The length of values associated \
    with their keys are:", dict2)
    print("The length of value associated \
    with key 'B' is:", dict2['B'])

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

> 与其键关联的值的长度为:{“A”:1，“B”:3，“C”:2，“D”:6 }
> 与键“B”关联的值的长度为:3

**方法#4** 使用字典项目()

**例:1**

```
# Python program to find the
# length of dictionary values

def main():
    # Defining the dictionary
    dict1 = {'a':[1, 2, 3], 
             'b'🙁1, 2, 3), 
             'c':5,
             'd':"nopqrs",
             'e':["A", "B", "C"]}

    # Initialize count 
    count = 0

    # using dict.items()
    for key, val in dict1.items():

        # Check the type of value 
        # is int or not
        if isinstance(val, int):
            count += 1

        # Check the type of value
        # is str or not
        elif isinstance(val, str):
            count += 1

        else:
            count += len(val)
    print("The total length of value is:", count)

# Driver code
if __name__ == '__main__':
    main()
```

**输出:**

```
The total length of values is: 11

```

**例:2**

```
# Python program to find the
# length of dictionary values

def main():
    # Defining the dictionary
    dict1 = {'A': "abcd", 
             'B': set([1, 2, 3]), 
             'C': (12, "number"),
             'D': [1, 2, 4, 5, 5, 5]}

    # Create a empty dictionary
    dict2 = {}

    # using dict.items()
    for key, val in dict1.items():

        # Check the type of value 
        # is int or not
        if isinstance(val, int):
            dict2[key] = 1

        # Check the type of value
        # is str or not
        elif isinstance(val, str):
            dict2[key] = 1

        else:
            dict2[key] = len(val)

    print("The length of values associated \
    with their keys are:", dict2)

    print("The length of value associated \
    with key 'B' is:", dict2['B'])

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

> 与其键关联的值的长度为:{“A”:1，“B”:3，“C”:2，“D”:6 }
> 与键“B”关联的值的长度为:3

**方法#5** 使用枚举()

**例:1**

```
# Python program to find the
# length of dictionary values

def main():

    # Defining the dictionary
    dict1 = {'a':[1, 2, 3], 
             'b'🙁1, 2, 3),
             'c':5,
             'd':"nopqrs",
             'e':["A", "B", "C"]}

    # Initialize count 
    count = 0

    # using enumerate()
    for k in enumerate(dict1.items()):

        # Check the type of value 
        # is int or not
        if isinstance(k[1][1], int):
            count += 1

        # Check the type of value 
        # is str or not
        elif isinstance(k[1][1], str):
            count += 1

        else:
            count += len(k[1][1])

    print("The total length of value is:", count)

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

```
The total length of value is: 11
```

**例:2**

```
# Python program to find the
# length of dictionary values

def main():

    # Defining the dictionary
    dict1 = {'A': "abcd",
             'B': set([1, 2, 3]), 
             'C': (12, "number"), 
             'D': [1, 2, 4, 5, 5, 5]}

    # Create a empty dictionary
    dict2 = {}

    # using enumerate()
    for k in enumerate(dict1.items()):

        # Check the type of value 
        # is int or not
        if isinstance(k[1][1], int):
            dict2[k[1][0]] = 1

        # Check the type of value 
        # is str or not
        elif isinstance(k[1][1], str):
            dict2[k[1][0]] = 1

        else:
            dict2[k[1][0]] = len(k[1][1])

    print("The length of values associated\
    with their keys are:", dict2)

    print("The length of value associated \
    with key 'B' is:", dict2['B'])

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

> 与其键关联的值的长度为:{“A”:1，“B”:3，“C”:2，“D”:6 }
> 与键“B”关联的值的长度为:3