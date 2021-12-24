# Python–删除重复元素时的交叉列表同步

> 原文:[https://www . geesforgeks . org/python-交叉列表-重复元素上的同步-删除/](https://www.geeksforgeeks.org/python-cross-list-sync-on-duplicate-elements-removal/)

给定两个列表，当移除第一个列表中的重复元素时，执行列表的所有元素与其他列表的同步。

> **输入** : test_list1 = [1，1，2，2，3，3]，test_list2 = [8，3，7，5，4，1]
> **输出** : [1，2，3]，[8，7，4]
> **说明:**删除重复项(1，2，3)后，从第二个列表中删除相应的元素，从而映射(8，7，4)。
> **输入** : test_list1 = [1，2，2，2，2]，test_list2 = [8，3，7，5，4，1]
> **输出** : [1，2]，[8，3]
> **解释**:移除的元素是(2，2，2)，[1，2]按照预期映射到[8，3]。

**方法#1:使用 loop + dict()**
以上函数提供了蛮力的方式来解决这个问题。在这种情况下，我们使用字典和循环条件来记忆与它对应的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cross List Sync on duplicate elements removal
# Using loop + dict()

# initializing lists
test_list1 = [2, 2, 3, 4, 4, 4, 5, 5, 6, 6]
test_list2 = [8, 3, 7, 5, 4, 1, 0, 9, 4, 2]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Cross List Sync on duplicate elements removal
temp = dict()
a = []
for idx in range(len(test_list1)):
    if test_list1[idx] not in a:
        a.append(test_list1[idx])

        # performing memoize using dictionary
        temp[test_list1[idx]] = test_list2[idx]

res2 = list(temp.values())
res1 = a

# printing result
print("List 1 : " + str(res1))
print("Sync List : " + str(res2))
```

**Output : **

```py
The original list 1 : [2, 2, 3, 4, 4, 4, 5, 5, 6, 6]
The original list 2 : [8, 3, 7, 5, 4, 1, 0, 9, 4, 2]
List 1 : [2, 3, 4, 5, 6]
Sync List : [8, 7, 5, 0, 4]
```

**方法#2:使用 loop + zip()**
这是可以执行此任务的另一种方式。在本例中，我们使用 zip()同步两个列表。类似的存储逻辑被实现为上述任务，并且相应的有效的其他列表元素被附加到结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cross List Sync on duplicate elements removal
# Using loop + zip()

# initializing lists
test_list1 = [2, 2, 3, 4, 4, 4, 5, 5, 6, 6]
test_list2 = [8, 3, 7, 5, 4, 1, 0, 9, 4, 2]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Cross List Sync on duplicate elements removal
res1 = []
res2 = []

# both lists are combined index wise using zip()
for a, b in zip(test_list1, test_list2):
    if a not in res1:
        res1.append(a)
        res2.append(b)

# printing result
print("List 1 : " + str(res1))
print("Sync List : " + str(res2))
```

**Output : **

```py
The original list 1 : [2, 2, 3, 4, 4, 4, 5, 5, 6, 6]
The original list 2 : [8, 3, 7, 5, 4, 1, 0, 9, 4, 2]
List 1 : [2, 3, 4, 5, 6]
Sync List : [8, 7, 5, 0, 4]
```