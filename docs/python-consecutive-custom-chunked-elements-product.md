# Python |连续定制分块元素产品

> 原文:[https://www . geesforgeks . org/python-continuous-custom-chunked-elements-product/](https://www.geeksforgeeks.org/python-consecutive-custom-chunked-elements-product/)

有许多方法可以在列表中列出产品和元素，但有时，需要以切片的方式找到列表中带有数字的产品。这可以是定制的，因此这方面的知识可以派上用场。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+ `enumerate()` +循环**
列表理解可以做可能的迭代部分，枚举可以帮助逻辑部分，检查列表中需要的有效元素。循环用于执行产品。

```py
# Python3 code to demonstrate 
# Consecutive Custom Chunked elements Product
# using list comprehension + enumerate() + loop

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing lists
test_list = list(range(1, 50))

# printing original list
print ("The original list is : " + str(test_list))

# interval elements
N = 5

# interval difference
K = 15

# using list comprehension + enumerate() + loop
# Consecutive Custom Chunked elements Product
res = prod([i for j, i in enumerate(test_list) if j % K < N ])

# printing result 
print ("The modified range product list : " + str(res))
```

**Output :**

> 原来的名单是:[1、2、3、4、5、6、7、8、9、10、11、12、13、14、15、16、17、18、19、20、21、22、23、24、25、26、27、28、29、30、31、32、33、34、35、36、37、38、39、40、41、42、43、44