# Python–将类似值列表分组到字典中

> 原文:[https://www . geesforgeks . org/python-group-相似值-列表-字典/](https://www.geeksforgeeks.org/python-group-similar-value-list-to-dictionary/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要将相似的值列表索引分组到一个字典中。这在我们需要分组字典作为成对列表输出的领域有很好的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用字典理解**
这是执行这个任务的方法。在这种情况下，我们将一个列表与另一个列表一起迭代，并使用一个列表中的相似关键字和另一个列表中的对应值不断构建字典。这是一个线性解决方案。

```
# Python3 code to demonstrate 
# Group similar value list to dictionary
# using dictionary comprehension

# Initializing lists
test_list1 = [4, 4, 4, 5, 5, 6, 6, 6, 6]
test_list2 = ['G', 'f', 'g', 'i', 's', 'b', 'e', 's', 't']

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Group similar value list to dictionary
# using dictionary comprehension
res = {key : [test_list2[idx] 
      for idx in range(len(test_list2)) if test_list1[idx]== key]
      for key in set(test_list1)}

# printing result 
print ("Mapped resultant dictionary : " + str(res))
```

**Output :**

> 原始列表 1 为:[4，4，4，5，5，6，6，6，6，6]
> 原始列表 2 为:['G '，' f '，' G '，' I '，' s '，' b '，' e '，' s '，' t']
> 映射结果词典:{4: ['G '，' f '，' G '，' 5: ['i '，' s']，6: ['b '，' e '，' s '，' t']