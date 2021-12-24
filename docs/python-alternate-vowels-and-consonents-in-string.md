# Python |字符串中的交替元音和同音

> 原文:[https://www . geesforgeks . org/python-交替元音-和-conconsonents-in-string/](https://www.geeksforgeeks.org/python-alternate-vowels-and-consonents-in-string/)

有时，在 Python 中处理字符串时，我们可能会遇到一个问题，我们可能需要重组字符串，在其中添加替代元音和辅音。这是一个很受欢迎的学校层面的问题，解决这个问题可能会很有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 loop + `join() + zip_longest()`**
以上功能的组合可以用来执行这个任务。在本文中，我们首先在单独的列表中分离元音和清音。然后使用`zip_longest()`和`join()`交替加入。

```py
# Python3 code to demonstrate working of
# Alternate vowels and consonents in String
# using zip_longest() + join() + loop
from itertools import zip_longest

# initializing string 
test_str = "gaeifgsbou"

# printing original string 
print("The original string is : " + test_str)

# Alternate vowels and consonents in String
# using zip_longest() + join() + loop
vowels = ['a', 'e', 'i', 'o', 'u']
test_vow = []
test_con = []
for ele in test_str:
   if ele in vowels:
       test_vow.append(ele)
   elif ele not in vowels:
       test_con.append(ele)
res = ''.join(''.join(ele) for ele in zip_longest(test_vow, test_con, fillvalue =''))

# printing result
print("Alternate consonents vowels are: " + res)
```

**Output :**

```py
The original string is : gaeifgsbou
Alternate consonents vowels are: agefigosub

```