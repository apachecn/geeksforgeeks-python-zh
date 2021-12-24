# Python |连续布尔范围

> 原文:[https://www . geesforgeks . org/python-continental-boolean-range/](https://www.geeksforgeeks.org/python-contiguous-boolean-range/)

有时，我们会遇到一个问题，在这个问题中，我们在一个列表中有很多真值和假值形式的数据，这种问题在机器学习领域很常见，有时我们需要知道在特定的位置存在哪个布尔值。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`enumerate() + zip() + list comprehension`**
通过使用以上三个功能的组合，可以轻松完成该任务。枚举函数处理迭代的角色，zip 函数分组相似的值，逻辑部分由列表理解处理。

```py
# Python3 code to demonstrate
# Contiguous Boolean Ranging
# using enumerate() + zip() + list comprehension

# initializing list 
test_list = [True, True, False, False, True,
             True, True, True, False, True]

# printing the original list 
print ("The original list is : " + str(test_list))

# using enumerate() + zip() + list comprehension
# for Contiguous Boolean Ranging
res = [x for x, (i , j) in enumerate(zip( [2]
        + test_list, test_list + [2])) if i != j]

# printing result
print ("The boolean range list is : " + str(res))
```

**Output:**

> 原始列表为:【真、真、假、假、真、真、真、假、真】
> 布尔范围列表为:【0、2、4、8、9、10】