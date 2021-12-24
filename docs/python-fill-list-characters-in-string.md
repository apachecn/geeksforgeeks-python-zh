# Python–在字符串中填充列表字符

> 原文:[https://www . geesforgeks . org/python-fill-list-字符串中的字符/](https://www.geeksforgeeks.org/python-fill-list-characters-in-string/)

给定字符串和列表，构造一个只填充列表值的字符串。

> **输入** : test_str = "geeksforgeeks "，fill_list = ['g '，' s '，' f '，' k]
> **输出** : g__ksf__g__ks
> **解释**:所有出现都填充在 g，s，f，k 的位置。
> 
> **输入** : test_str = "geeksforgeeks "，fill_list = ['g '，' s']
> **输出** : g___s___g___s
> **解释**:所有出现都填充在 g 和 s 的位置。

**方法#1:使用循环**

这是解决这个问题的暴力方法。在这种情况下，我们迭代字符串中的所有元素，如果它在列表中，我们填充它，否则填充“空格”值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Fill list characters in String 
# Using loop

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing fill list 
fill_list = ['g', 's', 'f']

# loop to iterate through string 
res = ""
for chr in test_str:

    # checking for presence
    if chr in fill_list:
        temp = chr
    else:
        temp = "_"
    res += temp

# printing result 
print("The string after filling values : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The string after filling values : g___sf__g___s

```

**方法 2:使用 join() +列表理解**

上述功能的组合可以用来解决这个问题。在本文中，我们使用列表理解来表述逻辑，并使用 join()使用条件来执行所需值的连接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Fill list characters in String 
# Using join() + list comprehension

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing fill list 
fill_list = ['g', 's', 'f']

# join() used to concatenate result 
# using conditionals in list comprehension
res = "".join([chr if chr in fill_list else "_" 
               for chr in list(test_str)])

# printing result 
print("The string after filling values : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The string after filling values : g___sf__g___s

```