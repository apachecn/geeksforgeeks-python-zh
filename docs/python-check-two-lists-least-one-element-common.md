# Python |检查两个列表是否至少有一个公共元素

> 原文:[https://www . geesforgeks . org/python-check-two-list-最少一个元素-common/](https://www.geeksforgeeks.org/python-check-two-lists-least-one-element-common/)

给定两个列表 a、b，检查两个列表中是否至少有一个公共元素。

**示例:**

```py
Input : a = [1, 2, 3, 4, 5]
        b = [5, 6, 7, 8, 9]
Output : True

Input : a=[1, 2, 3, 4, 5]
        b=[6, 7, 8, 9]
Output : False

```

**方法 1:遍历列表**

使用*遍历两个列表中的*，我们可以检查它们中是否至少存在一个公共元素。遍历两个列表时，如果我们发现其中有一个元素是公共的，那么我们返回 true。在完成遍历和检查之后，如果没有相同的元素，那么我们返回 false。

```py
# Python program to check 
# if two lists have at-least 
# one element common
# using traversal of list

def common_data(list1, list2):
    result = False

    # traverse in the 1st list
    for x in list1:

        # traverse in the 2nd list
        for y in list2:

            # if one common
            if x == y:
                result = True
                return result 

    return result

# driver code
a = [1, 2, 3, 4, 5]
b = [5, 6, 7, 8, 9]
print(common_data(a, b))

a = [1, 2, 3, 4, 5]
b = [6, 7, 8, 9]
print(common_data(a, b))
```

**输出:**

```py
True 
False

```

**方法二:使用集合和属性**

使用*集合的 and 属性*，如果至少存在一个公共元素，则集合(a) &集合(b)返回一个正整数，如果不包含任何正整数，则返回 0。所以我们在 set_a 中插入 a，在 set_b 中插入 b，然后检查 set_a & set_b 是否为正整数。

```py
# Python program to check 
# if two lists have at-least 
# one element common
# using set and property

def common_member(a, b):
    a_set = set(a)
    b_set = set(b)
    if (a_set & b_set):
        return True 
    else:
        return False

a = [1, 2, 3, 4, 5]
b = [5, 6, 7, 8, 9]
print(common_member(a, b))

a =[1, 2, 3, 4, 5]
b =[6, 7, 8, 9]
print(common_member(a, b))
```

**输出:**

```py
True 
False

```

**方法三:使用集合交集**

使用*设置的交集*内置功能。a_set.intersection(b_set)如果至少有一个公共元素，则返回正整数，否则返回 0。所以我们在 set_a 中插入 a，在 set_b 中插入 b，然后检查 a_set.intersection(b_set)，并根据值返回。

```py
# Python program to check 
# if two lists have at-least 
# one element common
# using set intersection

def common_member(a, b):
    a_set = set(a)
    b_set = set(b)
    if len(a_set.intersection(b_set)) > 0:
        return(True) 
    return(False)   

a = [1, 2, 3, 4, 5]
b = [5, 6, 7, 8, 9]
print(common_member(a, b))

a =[1, 2, 3, 4, 5]
b =[6, 7, 8, 9]
print(common_member(a, b))
```

**输出:**

```py
True 
False

```