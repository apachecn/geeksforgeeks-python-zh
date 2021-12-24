# Python–字符串中自定义连续字符重复

> 原文:[https://www . geesforgeks . org/python-自定义-连续字符-字符串重复/](https://www.geeksforgeeks.org/python-custom-consecutive-character-repetition-in-string/)

给定一个字符串，通过字典中映射的数字连续重复字符。

> **输入** : test_str = 'Geeks4Geeks '，test _ dict = {“G”:3，“e”:1，“4”:3，“k”:5，“s”:3 }
> T3】输出:gggeekkksss 444 ggeekkkss
> T6】解释:每个字母按照字典中的值重复。
> 
> **输入** : test_str = 'Geeks4Geeks '，test _ dict = {“G”:3，“e”:1，“4”:3，“k”:5，“s”:1 }
> **输出**:gggeekkks 444 ggeekkks
> **解释**:每个字母按照字典中的值重复。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代每个字符，并检查其重复映射，并重复该数量。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Custom Consecutive character repetition in String
# Using loop

# initializing string
test_str = 'Geeks4Geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing dictionary 
test_dict = {"G" : 3, "e" : 2, "4" : 4, "k" : 5, "s" : 3}

res = ""
for ele in test_str:

    # using * operator for repetition
    # using + for concatenation
    res += ele * test_dict[ele]

# printing result 
print("The filtered string : " + str(res)) 
```

**Output**

```py
The original string is : Geeks4Geeks
The filtered string : GGGeeeekkkkksss4444GGGeeeekkkkksss

```

**方法 2:使用列表理解+连接()**

这是执行这项任务的另一种方式。在这种情况下，我们执行与上述功能类似的任务。唯一的区别是我们使用 join()来合并创建的重复列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Custom Consecutive character repetition in String
# Using list comprehension + join()

# initializing string
test_str = 'Geeks4Geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing dictionary 
test_dict = {"G" : 3, "e" : 2, "4" : 4, "k" : 5, "s" : 3}

# using join to perform concatenation of strings
res = "".join([ele * test_dict[ele] for ele in test_str])

# printing result 
print("The filtered string : " + str(res)) 
```

**Output**

```py
The original string is : Geeks4Geeks
The filtered string : GGGeeeekkkkksss4444GGGeeeekkkkksss

```