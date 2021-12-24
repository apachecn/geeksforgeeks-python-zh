# Python |生成连续元素差异列表

> 原文:[https://www . geesforgeks . org/python-generate-sequence-element-difference-list/](https://www.geeksforgeeks.org/python-generate-successive-element-difference-list/)

在使用 python 时，我们通常会遇到许多我们需要在日常工作和开发中解决的问题。特别是在开发中，python 的小任务希望只在一行中执行。我们讨论了一些计算列表的方法，该列表由列表中连续不同的元素组成。

**方法#1:使用列表理解**
天真的方法可以用来执行，但是由于本文讨论了这个特定问题的一个线性解决方案，我们从列表理解作为执行这个任务的方法开始。

```
# Python3 code to demonstrate 
# to generate successive difference list 
# using list comprehension

# initializing list 
test_list = [1, 4, 5, 3, 6]

# printing original list 
print ("The original list is : " + str(test_list))

# using list comprehension
# generate successive difference list
res = [test_list[i + 1] - test_list[i] for i in range(len(test_list)-1)]

# printing result
print ("The computed successive difference list is : " + str(res))
```

**输出:**

```
The original list is : [1, 4, 5, 3, 6]
The computed successive difference list is : [3, 1, -2, 3]

```

**方法 2:使用`zip()`**
`zip()`也可以用于执行类似的任务，并使用负指数的幂将指数元素与其下一个元素进行 `zip()`，从而计算差异。

```
# Python3 code to demonstrate 
# to generate successive difference list 
# using zip()

# initializing list 
test_list = [1, 4, 5, 3, 6]

# printing original list 
print ("The original list is : " + str(test_list))

# using zip()
# generate successive difference list
res = [j - i for i, j in zip(test_list[: -1], test_list[1 :])]

# printing result
print ("The computed successive difference list is : " + str(res))
```

输出:

```
The original list is : [1, 4, 5, 3, 6]
The computed successive difference list is : [3, 1, -2, 3]

```

**方法三:使用`map() + operator.sub`**
`map()`可以配合减法运算符来执行这个特定的任务。这会将元素与其下一个元素进行映射，并执行减法运算。可以传递其他运算符来执行所需的操作。

```
# Python3 code to demonstrate 
# to generate successive difference list 
# using map() + operator.sub
import operator

# initializing list 
test_list = [1, 4, 5, 3, 6]

# printing original list 
print ("The original list is : " + str(test_list))

# using map() + operator.sub
# generate successive difference list
res = list(map(operator.sub, test_list[1:], test_list[:-1]))

# printing result
print ("The computed successive difference list is : " + str(res))
```

**输出:**

```
The original list is : [1, 4, 5, 3, 6]
The computed successive difference list is : [3, 1, -2, 3]

```