# 给定 Python 列表中的二元模型形成

> 原文:[https://www . geeksforgeeks . org/python-bigram-formation-from-给定-list/](https://www.geeksforgeeks.org/python-bigram-formation-from-given-list/)

当我们处理文本分类时，有时我们需要进行某种自然语言处理，因此有时需要形成单词的二元模型进行处理。在没有合适的库的情况下，这是很困难的，必须做同样的事情总是很有用的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `enumerate() + split()`**
以上三个功能的组合可以用来实现这个特定的任务。枚举函数执行可能的迭代，拆分函数用于配对，列表理解用于组合逻辑。

```
# Python3 code to demonstrate
# Bigram formation
# using list comprehension + enumerate() + split()

# initializing list 
test_list = ['geeksforgeeks is best', 'I love it']

# printing the original list 
print ("The original list is : " + str(test_list))

# using list comprehension + enumerate() + split()
# for Bigram formation
res = [(x, i.split()[j + 1]) for i in test_list 
       for j, x in enumerate(i.split()) if j < len(i.split()) - 1]

# printing result
print ("The formed bigrams are : " + str(res))
```

**输出:**

> 原列表为:[' geesforgeeks 是最好的'，'我爱它']
> 形成的二元模型为:[(' geesforgeeks '，' is ')，(' is '，' best ')，(' I '，' love ')，(' love '，' it')]

**方法#2:使用`zip() + split() + list comprehension`**
上述方法中执行的枚举任务也可以通过使用迭代器由 zip 函数执行，因此速度更快。让我们讨论一下实现这一点的某些方法。

```
# Python3 code to demonstrate
# Bigram formation
# using zip() + split() + list comprehension

# initializing list 
test_list = ['geeksforgeeks is best', 'I love it']

# printing the original list 
print ("The original list is : " + str(test_list))

# using zip() + split() + list comprehension
# for Bigram formation
res = [i for j in test_list 
       for i in zip(j.split(" ")[:-1], j.split(" ")[1:])]

# printing result
print ("The formed bigrams are : " + str(res))
```

**输出:**

> 原列表为:[' geesforgeeks 是最好的'，'我爱它']
> 形成的二元模型为:[(' geesforgeeks '，' is ')，(' is '，' best ')，(' I '，' love ')，(' love '，' it')]