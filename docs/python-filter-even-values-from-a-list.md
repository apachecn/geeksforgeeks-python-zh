# Python |从列表中过滤偶数值

> 原文:[https://www . geesforgeks . org/python-filter-even-values-from-a-list/](https://www.geeksforgeeks.org/python-filter-even-values-from-a-list/)

给定一个数字列表，任务是创建一个只包含偶数的新列表。

**示例:**

```
Input: list = [1, 2, 3, 4, 5]
Output: [2, 4]

Input: list = [12, 14, 95, 3]
Output: [12, 14]

```

**方法#1 :** 使用 for 循环
使用 For 循环迭代列表中的每个元素，并检查 num % 2 == 0。如果条件满足，则将其追加到输出列表中。

```
# Python code to filter even values from a list

# Initialisation of list
lis = [1,2,3,4,5]

# Output list initialisation
out = []

for num in lis: 

    # checking condition 
    if num % 2 == 0: 
        out.append(num)

# printing output
print(out)
```

**Output:**

```
[2, 4]

```

**方法 2 :** 使用 While 循环

```
# Python code to filter even values from a list

# Initialisation of list
lis = [1,2,3,4,5]
num = 0

# Output list initialisation
out = []
while(num < len(lis)): 

    # checking condition 
    if lis[num] % 2 == 0: 
        out.append(lis[num])
    # increment num 
    num += 1

# printing output
print(out)
```

**Output:**

```
[2, 4]

```

**方法 3 :** 使用列表理解

```
# Python code to filter even values from a list

# Initialisation of list
lis = [1,2,3,4,5]

lis2 = [i for i in lis if i%2 == 0]

# Printing output
print(lis2)
```

**Output:**

```
[2, 4]

```

**方法#4 :** 使用`filter()`

```
# Python code to filter even values from a list

# Initialisation of list
lis1 = [1,2,3,4,5]

is_even = lambda x: x % 2 == 0

# using filter
lis2 = list(filter(is_even, lis1))

# Printing output
print(lis2)
```

**Output:**

```
[2, 4]

```