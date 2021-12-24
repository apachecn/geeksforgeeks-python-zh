# 使用 Python 字典时错误很少

> 原文:[https://www . geesforgeks . org/little-使用 python 时出错-dictionary/](https://www.geeksforgeeks.org/few-mistakes-when-using-python-dictionary/)

通常，字典是一个无序的、可变的和有索引的集合。在 Python 中，字典是用花括号写的，它们有键和值。字典中的每个键值对由一个“冒号”分隔，而每个键由一个“逗号”分隔。

```py
my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
print(my_dict)
```

**Output:**

```py
{1: 'Geeks', 2: 'For', 3: 'Geeks'}

```

我们通常使用字典来访问其键值在方括号内的项目。

```py
my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
print(my_dict[1])
print(my_dict[2])
print(my_dict[3])
```

**Output:**

```py
Geeks
For
Geeks

```

**字典常见的操作有:**

*   为了获得字典的值，我们使用 values()方法。

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    print(my_dict.values())
    ```

    **输出:**

    ```py
    dict_values(['Geeks', 'For', 'Geeks'])

    ```

*   为了得到字典的键，我们使用 key()方法。

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    print(my_dict.keys())
    ```

    **输出:**

    ```py
    dict_keys([1, 2, 3])

    ```

*   向字典中添加新条目

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    my_dict[4]='Python'
    print(my_dict)
    ```

    **输出:**

    ```py
    {1: 'Geeks', 2: 'For', 3: 'Geeks', 4: 'Python'}

    ```

*   要更改条目

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    my_dict[3]='Python'
    print(my_dict)
    ```

    **的值，输出:**

    ```py
    {1: 'Geeks', 2: 'For', 3: 'Python'}

    ```

*   从字典中删除条目

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    del my_dict[3]
    print(my_dict)
    ```

    **输出:**

    ```py
    {1: 'Geeks', 2: 'For'}

    ```

*   要复制字典

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    my_dict1 = my_dict
    print(my_dict1)
    ```

    **输出:**

    ```py
    {1: 'Geeks', 2: 'For', 3: 'Geeks'}

    ```

*   删除所有条目。

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    my_dict.clear()
    print(my_dict)
    ```

    **输出:**

    ```py
    {}

    ```

*   找出条目的数量。

    ```py
    my_dict = {1: 'Geeks', 2: 'For', 3:'Geeks'}
    z = len(my_dict)
    print(z)
    ```

    **输出:**

    ```py
    3

    ```

**使用字典时的常见错误及克服**

*   为了访问键值，我们通常使用 dict_name[key_name]来代替，我们应该使用 get()方法来消除在整个代码中抛出的异常。
*   为了更新键的值，我们通常使用 dict_name[key_name]='new_value '来代替，我们应该更新(key=value)方法来消除在整个代码中抛出的异常。
*   为了复制字典，我们通常使用 dict_name = new_dict_name，相反，我们应该使用 copy()方法来消除在整个代码中抛出的异常。

**何时不使用字典**

*   字典很有用，但它们不是 Python 中唯一的关联数组结构。通常有一种更专门的容器类型，如[集合](https://www.geeksforgeeks.org/python-sets/)、[元组](https://www.geeksforgeeks.org/python-tuples/)等。
*   不同类型的数值可以相等(例如 1 == 1.0)，在这种情况下，它们代表相同的键。