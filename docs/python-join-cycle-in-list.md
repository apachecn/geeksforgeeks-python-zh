# Python |加入列表中的循环

> 原文:[https://www.geeksforgeeks.org/python-join-cycle-in-list/](https://www.geeksforgeeks.org/python-join-cycle-in-list/)

有时，在处理竞争性编程中的图形问题时，我们有一个对的列表，我们需要找到其中是否有可能的循环，并打印该循环中的所有元素。让我们讨论一下解决这个问题的某些方法。

**方法:使用 yield + loop + generator**
要执行的蛮力方法是使用一个生成器，如果我们知道元素肯定会形成一个循环，就一直打印值，这是通过无限循环并在没有找到更多匹配时停止来完成的。

```
# Python3 code to demonstrate working of
# Join cycle in list
# Using yield + loop + generator

# helper function to perform this task 
def cycle(test_list, val, stop = None):
    temp = dict(test_list)
    stop = stop if stop is not None else val
    while True:
        yield (val)
        val = temp.get(val, stop)
        if val == stop: break

# initializing list
test_list = [[6, 7], [9, 6], [7, 9]]

# printing original list
print("The original list is : " + str(test_list))

# Join cycle in list
# Using yield + loop + generator
# printing result
print("The cycle elements are : ")
for ele in cycle(test_list, 6):
    print(ele)
```

**Output :**

```
The original list is : [[6, 7], [9, 6], [7, 9]]
The cycle elements are : 
6
7
9

```