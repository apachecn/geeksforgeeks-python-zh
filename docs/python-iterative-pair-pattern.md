# Python–迭代配对模式

> 原文:[https://www . geesforgeks . org/python-iterative-pair-pattern/](https://www.geeksforgeeks.org/python-iterative-pair-pattern/)

有时，在使用 Python 时，我们可能会遇到这样的问题，即我们需要执行模式构造或迭代对字符串，其中第二个元素不断增加。这类问题在日常编程和学校编程中都有应用。让我们讨论执行这项任务的某些方法。
**方法#1:使用循环**
这是可以执行这个任务的蛮力方式。在这种情况下，我们手动检查第二个元素，并在每次迭代和存储时执行增量。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Iterative Pair Pattern
# Using loop

# initializing 1st element
frst_ele = 'G'

# initializing 2nd element
secnd_ele = '*'

# initializing N
N = 4

# Iterative Pair Pattern
# Using loop
res = frst_ele + secnd_ele
for idx in range(1, N):
    res += frst_ele + secnd_ele * (idx + 1)

# printing result
print("The constructed pattern is : " + str(res))
```

**Output : **

```py
The constructed pattern is : G*G**G***G****

```

**方法#2:使用 join() +生成器表达式**
以上方法的组合可以用来执行这个任务。在本文中，我们在生成器表达式的一个线性逻辑中执行增量和模式构造任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Iterative Pair Pattern
# Using join() + generator expression

# initializing 1st element
frst_ele = 'G'

# initializing 2nd element
secnd_ele = '*'

# initializing N
N = 4

# Iterative Pair Pattern
# Using join() + generator expression
res = frst_ele.join(secnd_ele * idx for idx in range(N + 1))

# printing result
print("The constructed pattern is : " + str(res))
```

**Output : **

```py
The constructed pattern is : G*G**G***G****

```