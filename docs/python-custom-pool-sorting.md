# Python–自定义池排序

> 原文:[https://www.geeksforgeeks.org/python-custom-pool-sorting/](https://www.geeksforgeeks.org/python-custom-pool-sorting/)

给定列表和优先级列表，根据列表元素在优先级列表中的出现对列表元素进行排序，即出现在列表 1 中的元素应该首先出现，而出现在其他列表中的元素应该在其后出现。

> **输入** : test_list = [5，6，3，7]，prio1_list = [6，3]，prio2_list = [5，7]
> **输出** : [6，3，5，7]
> **解释** : 6，3 出现在 p1 列表中，后面是位于 p2 列表中的 5 和 7。
> 
> **输入** : test_list = [5，6]，prio1_list = [6]，prio2_list = [5]
> **输出** : [6，5]
> **解释**:第 1 优先级列表中出现 6 个而不是 5 个。

**方法:使用`sort()` +比较器按键功能**
可以使用通用排序()执行该任务。真正的算法在于传递给它的比较器函数。适当返回值的赋值及其顺序被用来解决这个问题。

```
# Python3 code to demonstrate working of 
# Custom Pool Sorting
# Using sort() + comparator key function

# comparator function
def func(ele):

    # Returning 1 or 2 ro assign priority
    if ele in prio1_list:
        return  1
    elif ele in prio2_list:
        return  2

# initializing list
test_list = [5, 6, 3, 7, 4, 2, 9, 10] 

# printing original list
print("The original list is : " + str(test_list))

# initializing priority lists
prio1_list = [4, 6, 3, 8, 10]
prio2_list = [5, 7, 1, 2, 9]

# Using sort() + comparator key function
# key passed with function to manage priority
test_list.sort(key = func)

# printing result 
print("List after sorting : " + str(test_list))
```

**Output :**

```
The original list is : [5, 6, 3, 7, 4, 2, 9, 10]
List after sorting : [6, 3, 4, 10, 5, 7, 2, 9]

```