# Python |自定义循环列表

> 原文:[https://www.geeksforgeeks.org/python-custom-cycle-list/](https://www.geeksforgeeks.org/python-custom-cycle-list/)

在使用 Python 列表时，我们可能会遇到一个问题，即我们需要执行列表循环。这个问题看起来很直接，前面已经讨论过了。但有时，我们需要执行它的变化，因此使任务具有挑战性。我们可以进行自定义，例如循环开始的元素和循环列表中的元素数量。让我们讨论这些变化解决方案。

**方法:使用`dropwhile() + cycle() + islice()`**
该任务可以使用以上功能的组合来执行。在这种情况下，使用`dropwhile()`将元素放置到 K，然后可以使用`cycle()`和`islice()`来限制列表中元素的数量。

```
# Python3 code to demonstrate working of
# Custom Cycle list
# using dropwhile() + cycle() + islice()
import itertools

# initialize list
test_list = [3, 4, 5, 7, 1]

# printing original list
print("The original list is : " + str(test_list))

# initialize element for start cycle
K = 7

# initialize size of cycle list 
N = 12

# Custom Cycle list
# using dropwhile() + cycle() + islice()
res = list(itertools.islice(itertools.dropwhile(lambda i: i != K, itertools.cycle(test_list)),  N))

# printing result
print("The cycled list is : " + str(res))
```

**Output :**

```
The original list is : [3, 4, 5, 7, 1]
The cycled list is : [7, 1, 3, 4, 5, 7, 1, 3, 4, 5, 7, 1]

```