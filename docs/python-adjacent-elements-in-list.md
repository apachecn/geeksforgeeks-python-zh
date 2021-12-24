# Python–列表中的相邻元素

> 原文:[https://www . geesforgeks . org/python-相邻元素列表/](https://www.geeksforgeeks.org/python-adjacent-elements-in-list/)

给定一个列表，为每个元素提取下一个和上一个元素。

> **输入** : test_list = [3，7，9，3]
> **输出** : [(无，7)，(3，9)，(7，3)，(9，无)]
> **解释**:7 左边元素为 3，右边为 9。
> 
> **输入**:test _ list =【3，7，3】
> **输出**:【(无，7)、(3，3)、(7，无)】
> **解释**:7 左边元素为 3，右边为 3。

**方法:使用循环**

在这种情况下，我们迭代每个元素，并使用元素访问获得下一个和上一个元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Adjacent elements in List
# Using loop

# Function to find adjacent
# elements in List
def findAdjacentElements(test_list):
    res = []
    for idx, ele in enumerate(test_list):

        # Checking for all cases to append
        if idx == 0:
            res.append((None, test_list[idx + 1]))
        elif idx == len(test_list) - 1:
            res.append((test_list[idx - 1], None))
        else:
            res.append((test_list[idx - 1], test_list[idx + 1]))
    return res

# Initializing list
input_list = [3, 7, 8, 2, 1, 5, 8, 9, 3]

# Printing original list
print("The original list is:", input_list)

# printing result
print("The Adjacent elements list:", findAdjacentElements(input_list))
```

**输出:**

> 原列表为:【3、7、8、2、1、5、8、9、3】
> 相邻元素列表:[(无、7)、(3、8)、(7、2)、(8、1)、(2、5)、(1、8)、(5、9)、(8、3)、(9、无)]