# Python–检查列表元素的元素索引是否相等

> 原文:[https://www . geesforgeks . org/python-check-if-elements-index-is-equal-for-list-elements/](https://www.geeksforgeeks.org/python-check-if-elements-index-are-equal-for-list-elements/)

给定两个列表和检查列表，测试对于检查列表中的每个元素，元素是否出现在两个列表中的相似索引中。

> **输入** : test_list1 = [2，6，9，7，8]，test_list2 = [2，7，9，4，8]，check_list = [9，8，7]
> **输出** : False
> **解释** : 7 在两个列表中都排在第 4 和第 2 位，因此为 False。
> 
> **输入** : test_list1 = [2，6，9，7，8]，test_list2 = [2，6，9，4，8]，check_list = [9，8，6]
> **输出**:真
> **解释**:均来自相似索引的检查表，因此为真。

**方法#1:使用循环**

在这种情况下，我们对列表中的所有元素进行迭代，如果元素不同并且出现在检查列表中，则返回 False。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if elements index are equal for list elements
# Using loop

# initializing lists
test_list1 = [2, 6, 9, 7, 8]
test_list2 = [2, 7, 9, 4, 8]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# initializing check_list
check_list = [9, 8, 2]

res = True 
for idx, ele in enumerate(test_list1):

    # check for indifference and containment
    if test_list1[idx] != test_list2[idx] and ele in check_list:
        res = False 
        break

# printing result 
print("Are elements at same index for required instances ?:  " + str(res))
```

**Output**

```
The original list 1 : [2, 6, 9, 7, 8]
The original list 2 : [2, 7, 9, 4, 8]
Are elements at same index for required instances ?:  True

```

**方法 2:使用 zip() + all() +生成器表达式**

在这种情况下，我们使用 zip()对相似的索引进行配对，然后使用 all()检查所有索引，生成器表达式用于迭代逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if elements index are equal for list elements
# Using zip() + all() + generator expression

# initializing lists
test_list1 = [2, 6, 9, 7, 8]
test_list2 = [2, 7, 9, 4, 8]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# initializing check_list
check_list = [9, 8, 2]

# checking for all elements equal in check list using all()
res = all(a == b for a, b in zip(test_list1, test_list2) if a in check_list)

# printing result 
print("Are elements at same index for required instances ?:  " + str(res))
```

**Output**

```
The original list 1 : [2, 6, 9, 7, 8]
The original list 2 : [2, 7, 9, 4, 8]
Are elements at same index for required instances ?:  True

```