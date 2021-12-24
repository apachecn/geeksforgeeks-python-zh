# Python–字符串中包含所有字符的键

> 原文:[https://www . geesforgeks . org/python-全字符串键/](https://www.geeksforgeeks.org/python-key-with-all-characters-in-string/)

有时，在使用 Python Strings 时，我们可能会遇到这样的问题，即需要提取字符值列表中包含所有字符的所有键。这种问题有应用有很多领域，比如日常编程。让我们讨论一下解决这个问题的方法。

**方法:使用`all()` +词典理解**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 all()来执行整个字典的检查，并使用 items()来提取项目。

```py
# Python3 code to demonstrate working of 
# Key with all Characters in String
# Using all() + dictionary comprehension

# initializing dictionary
test_dict = { 'gfg' : ['a', 'b', 'c', 'd', 'g'],
              'is' : ['b', 'f', 'e'],
              'best' : ['c', 'd', 'g'],
              'for' : ['n', 'z'],
              'CS' : ['g', 'd'] }

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing keys 
test_str = 'gd'

# Key with all Characters in String
# Using all() + dictionary comprehension
res = list({key for key, val in test_dict.items() 
            if all(chr in val for chr in test_str)})

# printing result 
print("The keys list : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': ['b '，' f '，' e']，' best': ['c '，' d '，' g']，' for': ['n '，' z']，' CS': ['g '，' d']，' gfg': ['a '，' b '，' c '，' d '，' g']}
> 键列表:['best '，' CS '，' gfg']