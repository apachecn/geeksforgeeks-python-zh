# Python |将异构类型字符串转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-异类-类型-字符串到列表/](https://www.geeksforgeeks.org/python-convert-heterogeneous-type-string-to-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要将字符串中的数据转换为列表，而字符串包含来自不同数据类型的元素，如布尔值。这个问题可能发生在使用大量数据类型的域中。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+拆分()+剥离()**
以上方法的组合可以用来解决这个问题。在这种情况下，我们执行元素的分割，然后剥离杂散字符以转换数据类型，并使用列表理解编译列表构建的整个逻辑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert String of Heterogeneous types to List
# using list comprehension + split() + strip()

# initializing string 
test_str = "'gfg', 'is', True, 'best', False"

# printing original string 
print("The original string is : " + test_str)

# Convert String of Heterogeneous types to List
# using list comprehension + split() + strip()
res = [ele.strip() if ele.strip().startswith("'") else ele == 'True'
      for ele in test_str.split(', ')]

# printing result
print("List after conversion from string : " + str(res))
```

**Output : **

```py
The original string is : 'gfg', 'is', True, 'best', False
List after conversion from string : ["'gfg'", "'is'", True, "'best'", False]
```

**方法 2:使用 eval()**
这个内置函数自动检测数据类型并执行转换。这是一种单短语解决方案，即使整数是字符串也能提供解决方案，因此推荐使用这种解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert String of Heterogeneous types to List
# using eval()

# initializing string 
test_str = "'gfg', 'is', True, 'best', False, 1, 2"

# printing original string 
print("The original string is : " + test_str)

# Convert String of Heterogeneous types to List
# using eval()
res = list(eval(test_str))

# printing result
print("List after conversion from string : " + str(res))
```

**Output : **

```py
The original string is : 'gfg', 'is', True, 'best', False, 1, 2
List after conversion from string : ["'gfg'", "'is'", True, "'best'", False, 1, 2]
```