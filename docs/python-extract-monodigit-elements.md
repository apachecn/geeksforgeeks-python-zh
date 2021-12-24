# Python–提取一位数元素

> 原文:[https://www . geesforgeks . org/python-extract-mono digital-elements/](https://www.geeksforgeeks.org/python-extract-monodigit-elements/)

给定数字列表，提取所有只有相似数字的数字。

> **输入** : test_list = [463，888，123，' aaa '，112，111，' gfg '，939，4，' ccc']
> **输出** : [888，' aaa '，111，4，' ccc']
> **解释**:所有元素都有一个唯一的数字或字符。
> 
> **输入**:test _ list =【463，“GFG”，8838，43，991】
> **输出**:【】
> **解释**:未发现仅有一位数的元素。

**方法一:使用列表理解+ all()**

在这种情况下，我们使用列表理解迭代所有元素， *all()* 用于检查所有数字与第一个数字的相等性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Monodigit elements
# Using list comprehension + all()

# initializing list
test_list = [463, 888, 123, "aaa", 112, 111, "gfg", 939, 4, "ccc"]

# printing original lists
print("The original list is : " + str(test_list))

# all() checks for all similar digits
res = [sub for sub in test_list if all(
    str(ele) == str(sub)[0] for ele in str(sub))]

# printing result
print("Extracted Numbers : " + str(res))
```

**输出:**

> 原列表为:【463，888，123，' aaa '，112，111，' gfg '，939，4，' ccc '】
> 抽取号码:【888，' aaa '，111，4，' CCC '】

**方法 2:使用滤镜()+ lambda + all()**

在这种情况下，我们使用*λ*功能执行过滤任务，*过滤器()*，再次使用 *all()* 检查所有数字的相等性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Monodigit elements
# Using filter() + lambda + all()

# initializing list
test_list = [463, 888, 123, "aaa", 112, 111, "gfg", 939, 4, "ccc"]

# printing original lists
print("The original list is : " + str(test_list))

# all() checks for all similar digits
# filter() used for filtering
res = list(filter(lambda sub: all(str(ele) == str(
    sub)[0] for ele in str(sub)), test_list))

# printing result
print("Extracted Numbers : " + str(res))
```

**输出:**

> 原列表为:【463，888，123，' aaa '，112，111，' gfg '，939，4，' ccc '】
> 抽取号码:【888，' aaa '，111，4，' CCC '】