# Python–用特定字符串过滤元组

> 原文:[https://www . geesforgeks . org/python-filter-tuples-with-strings-specific-characters/](https://www.geeksforgeeks.org/python-filter-tuples-with-strings-of-specific-characters/)

给定元组列表，提取元组，元组具有由特定字符组成的字符串。

> **输入** : test_list = [('gfg '，' best ')，(' gfg '，' good ')，(' fest '，' gfg')]，char_str = 'gfestb'
> **输出** : [('gfg '，' best ')，(' fest '，' gfg')]
> **解释**:所有元组都包含 char_str 的字符。
> 
> **输入** : test_list = [('gfg '，' best ')，(' gfg '，' good ')，(' fest '，' gfg')]，char_str = 'gfstb'
> **输出** : []
> **解释**:没有给定字符的元组。

**方法#1:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本文中，我们检查字符串中的字符，使用 In 运算符和 all()来检查元组中的所有元素是否都有由某些字符组成的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Tuples with Strings of specific characters
# Using all() + list comprehension

# initializing lists
test_list = [('gfg', 'best'), ('gfg', 'good'), ('fest', 'gfg')]

# printing original lists
print("The original list is : " + str(test_list))

# initializing char_str
char_str = 'gfestb'

# nested all(), to check for all characters in list, 
# and for all strings in tuples
res = [sub for sub in test_list if all(
    all(el in char_str for el in ele) for ele in sub)]

# printing result
print("The filtered tuples : " + str(res))
```

**输出:**

> 原始列表为:[('gfg '，' best ')，(' gfg '，' good ')，(' fest '，' gfg')]
> 过滤后的元组:[('gfg '，' best ')，(' fest '，' gfg')]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/) **+ lambda + all()**

与上述方法类似，使用差值为 filter() + lambda 来执行过滤任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Tuples with Strings of specific characters
# Using filter() + lambda + all()

# initializing lists
test_list = [('gfg', 'best'), ('gfg', 'good'), ('fest', 'gfg')]

# printing original lists
print("The original list is : " + str(test_list))

# initializing char_str
char_str = 'gfestb'

# nested all(), to check for all characters in list, 
# and for all strings in tuples filter() is used 
# to extract tuples
res = list(filter(lambda sub: all(all(el in char_str for el in ele)
                                  for ele in sub), test_list))

# printing result
print("The filtered tuples : " + str(res))
```

**输出:**

> 原始列表为:[('gfg '，' best ')，(' gfg '，' good ')，(' fest '，' gfg')]
> 过滤后的元组:[('gfg '，' best ')，(' fest '，' gfg ')