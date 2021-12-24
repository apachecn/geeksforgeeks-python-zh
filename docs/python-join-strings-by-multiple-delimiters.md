# Python–通过多个分隔符连接字符串

> 原文:[https://www . geesforgeks . org/python-通过多个分隔符连接字符串/](https://www.geeksforgeeks.org/python-join-strings-by-multiple-delimiters/)

给定两个字符串，任务是编写一个 python 程序，通过分隔符列表中的每个分隔符将它们连接起来。

> **输入:** test_str1 = 'Geeksforgeeks '，test _ str 2 = ' Best '，join_list = ["+"，" * "，"-"，" { content } # x201D, ",", "@"]
> 
> **输出:** [“极客 forgeeks+Best”，“极客 forgeeks*Best”，“极客 forgeeks-Best”，“极客 forgeeks$Best”，“极客 forgeeks，Best”，“极客 forgeeks @ Best”]
> 
> **解释:**元素与所有需要的分隔符连接在一起。
> 
> **输入:** test_str1 = 'Geeksforgeeks '，test _ str 2 = ' Best '，join_list = ["+"，" * "，"-"，" { content } # x201D]
> 
> **输出:** ['极客 forgeeks+Best '，'极客 forgeeks*Best '，'极客 forgeeks-Best '，'极客 forgeeks$Best']
> 
> **解释:**元素与所有需要的分隔符连接在一起。

**方法一:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用循环内部列表理解和+运算符执行连接任务来迭代列表中的所有分隔符。

**示例:**

## 蟒蛇 3

```
# initializing strings
test_str1 = 'Geeksforgeeks'
test_str2 = "Best"

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing join list
join_list = ["+", "*", "-", "{content}quot;, ",", "@"]

# + operator used for concatenations
res = [test_str1 + delim + test_str2 for delim in join_list]

# printing result
print("All delimiters concatenations : " + str(res))
```

**输出:**

> 原来的字符串 1 是:Geeksforgeeks
> 
> 最初的字符串 2 是:最佳
> 
> 所有分隔符串联:['极客 forgeeks+Best '，'极客 forgeeks*Best '，'极客 forgeeks-Best '，'极客 forgeeks$Best '，'极客 forgeeks，Best '，'极客 forgeeks@Best']

**方法二:** *使用* [*加入()*](https://www.geeksforgeeks.org/join-function-python/) *和* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

与上述方法类似，区别在于连接任务是使用 join()而不是+运算符执行的。

**示例:**

## 蟒蛇 3

```
# initializing strings
test_str1 = 'Geeksforgeeks'
test_str2 = "Best"

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing join list
join_list = ["+", "*", "-", "{content}quot;, ",", "@"]

# join() operator used for concatenations
res = [delim.join([test_str1, test_str2]) for delim in join_list]

# printing result
print("All delimiters concatenations : " + str(res))
```

**输出:**

> 原来的字符串 1 是:Geeksforgeeks
> 
> 最初的字符串 2 是:最佳
> 
> 所有分隔符串联:['极客 forgeeks+Best '，'极客 forgeeks*Best '，'极客 forgeeks-Best '，'极客 forgeeks$Best '，'极客 forgeeks，Best '，'极客 forgeeks@Best']