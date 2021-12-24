# Python–将列表转换为分隔符分隔的字符串

> 原文:[https://www . geesforgeks . org/python-convert-list-to-delimiter-separated-string/](https://www.geeksforgeeks.org/python-convert-list-to-delimiter-separated-string/)

给定元素列表，将其转换为分隔符分隔的字符串。

> **输入** : test_list = [7，“Gfg”，“best”，9]，delim =“*”
> **输出** : 7*Gfg*best*9*
> **解释**:所有元素以连接符的形式用“*”连接。
> 
> **输入** : test_list = [7，“Gfg”，“best”，9]，delim = "#"
> **输出** : 7#Gfg#best#9#
> **解释**:所有元素都以“#”作为连接符串联。

**方法#1:使用 loop + str()**

这是执行这项任务的方法之一。在这种情况下，我们运行一个循环，在将每个元素转换为字符串后，在每个元素的末尾添加分隔符。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert List to delimiter separated String
# Using loop + str()

# initializing list
test_list = [7, "Gfg", 8, "is", "best", 9] 

# printing original list
print("The original list is : " + str(test_list))

# initializing delim 
delim = "*"

res = '' 

# using loop to add string followed by delim 
for ele in test_list:
    res = res + str(ele) + delim

# printing result 
print("The resultant string : " + str(res))
```

**Output**

```
The original list is : [7, 'Gfg', 8, 'is', 'best', 9]
The resultant string : 7*Gfg*8*is*best*9*

```

**方法 2:使用 join() + str()**

这是执行这项任务的另一种方式。在本例中，我们使用 join()通过 delim 连接每个元素，并使用 str()转换成字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert List to delimiter separated String
# Using join() + str()

# initializing list
test_list = [7, "Gfg", 8, "is", "best", 9] 

# printing original list
print("The original list is : " + str(test_list))

# initializing delim 
delim = "*"

# using map to convert each element to string 
temp = list(map(str, test_list))

# join() used to join with delimiter
res = delim.join(temp)

# printing result 
print("The resultant string : " + str(res))
```

**Output**

```
The original list is : [7, 'Gfg', 8, 'is', 'best', 9]
The resultant string : 7*Gfg*8*is*best*9

```