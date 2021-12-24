# Python |查找词典深度

> 原文:[https://www . geeksforgeeks . org/python-find-depth-of-a-dictionary/](https://www.geeksforgeeks.org/python-find-depth-of-a-dictionary/)

**先决条件:** [嵌套词典](https://www.geeksforgeeks.org/python-nested-dictionary/)

任务是在 Python 中找到给定字典的深度。让我们讨论一下完成这项任务的所有不同方法。

**示例:**

```py
Input : {1:'a', 2: {3: {4: {}}}}
Output : 4

Input : {'a':1, 'b': {'c':'geek'}}
Output : 3

```

**方法#1 :** 幼稚 alproach

为了找到字典的深度，一个天真的方法是计算打开花括号的数量。但是，这种方法的一个缺点是，只有在输入正确的情况下，它才会起作用。

```py
# Python3 Program to find depth of a dictionary
def dict_depth(dic, level = 1):

    str_dic = str(dic)
    counter = 0
    for i in str_dic:
        if i == "{":
            counter += 1
    return(counter)

# Driver code 
dic = {1:'Geek', 2: {3: {4: {}}}}
print(dict_depth(dic))
```

**Output:**

```py
4

```

**方法 2:** 使用递归

在这种方法中，我们使用带有 [max()](https://www.geeksforgeeks.org/python-string-max/) 函数的递归，该函数在每个级别上为当前正在检查的字典选择最大深度。

```py
# Python3 Program to find depth of a dictionary
def dict_depth(dic, level = 1):

    if not isinstance(dic, dict) or not dic:
        return level
    return max(dict_depth(dic[key], level + 1)
                               for key in dic)

# Driver code 
dic = {1:'a', 2: {3: {4: {}}}}

print(dict_depth(dic))
```

**Output:**

```py
4

```

递归解决方案的另一个版本是使用 [map()](https://www.geeksforgeeks.org/python-map-function/) 函数，通过该函数将内部字典的值映射到被调用的函数。

```py
# Python3 Program to find depth of a dictionary
def dict_depth(my_dict):
    if isinstance(my_dict, dict):

        return 1 + (max(map(dict_depth, my_dict.values()))
                                    if my_dict else 0)

    return 0

# Driver code 
my_dict = {1:'a', 2: {3: {4: {}}}}
print(dict_depth(my_dict))
```

**Output:**

```py
4

```

**方法#3:** 迭代解

在这种方法中，我们将嵌套键及其初始深度保存在一个变量中，比如`p_dict`。现在，为`p_dict`开始一个循环，在深入挖掘嵌套字典的同时不断弹出值。

```py
# Python3 Program to find depth of a dictionary
def dict_depth(myDict):

    Ddepth = 1
    obj = [(k, Ddepth + 1) for k in myDict.values()
                          if isinstance(k, dict)]
    max_depth = 0

    while(obj):
        n, Ddepth = obj.pop()
        max_depth = max(max_depth, Ddepth)

        obj = obj + [(k, Ddepth + 1) for k in n.values()
                                 if isinstance(k, dict)]

    return max_depth

# Driver code 
myDict = {1:'a', 2: {3: {4:{}}}}
print(dict_depth(myDict))
```

**Output:**

```py
4

```