# Python–检查列表是否包含特定数字

> 原文:[https://www . geesforgeks . org/python-检查列表是否包含特定数字/](https://www.geeksforgeeks.org/python-check-if-list-contain-particular-digits/)

给定一个列表和一些数字，任务是编写一个 python 程序来检查列表是否只包含某些数字。

```
Input : test_list = [435, 133, 113, 451, 134], digs = [1, 4, 5, 3]
Output : True
Explanation : All elements are made out of 1, 4, 5 or 3 only.

Input : test_list = [435, 133, 113, 451, 134], digs = [1, 4, 5]
Output : False
Explanation : 3 as a digit is required in allowed digits.
```

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)**+**[**str()**](https://www.geeksforgeeks.org/python-str-function/)**+**[**连接()**](https://www.geeksforgeeks.org/join-function-python/)

在这种情况下，我们迭代列表中的每个元素，并通过连接所有数字、转换为字符串并检查转换为字符串的元素的所有数字中的每一个来检查每个元素是否具有所有数字。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if list contain particular digits
# Using loop + str() + join()

# initializing lists
test_list = [435, 133, 113, 451, 134]

# printing original list
print("The original list is : " + str(test_list))

# initializing digits
digs = [1, 4, 5, 3]

digt_str = ''.join([str(ele) for ele in digs])
all_ele = ''.join([str(ele) for ele in test_list])

res = True
for ele in all_ele:

    # checking for all digits in element string
    for el in ele:
        if el not in digt_str:
            res = False
            break

# printing result
print("Are all elements made from required digits? : " + str(res))
```

**输出:**

```
The original list is : [435, 133, 113, 451, 134]
Are all elements made from required digits? : True
```

**方法二:使用** [**任意()**](https://www.geeksforgeeks.org/python-any-function/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们使用 any()和 not 操作来标记任何不是来自数字串的数字。在列表理解中使用迭代扩展的一个线性替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if list contain particular digits
# Using any() + list comprehension

# initializing lists
test_list = [435, 133, 113, 451, 134]

# printing original list
print("The original list is : " + str(test_list))

# initializing digits
digs = [1, 4, 5, 3]

digt_str = ''.join([str(ele) for ele in digs])
all_ele = ''.join([str(ele) for ele in test_list])

# any() checks if any element is not part of digit
res = not any(ele not in digt_str for ele in all_ele)

# printing result
print("Are all elements made from required digits? : " + str(res))
```

**输出:**

```
The original list is : [435, 133, 113, 451, 134]
Are all elements made from required digits? : True
```