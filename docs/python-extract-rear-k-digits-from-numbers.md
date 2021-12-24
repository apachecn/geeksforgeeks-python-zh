# Python–从数字中提取后 K 位数字

> 原文:[https://www . geesforgeks . org/python-extract-rear-k-digits-from-numbers/](https://www.geeksforgeeks.org/python-extract-rear-k-digits-from-numbers/)

给定一个整数列表，从中提取后面的 K 个数字。

> **输入** : test_list = [5645，23567，34543，87652，2342]，K = 2
> **输出**:【45，67，43，52，42】
> **解释**:提取后 2 位数字。
> 
> **输入**:test _ list =【5645，23567，34543，87652，2342】，K = 4
> **输出**:【5645，3567，4543，7652，2342】
> **解释**:提取后 4 位数字。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+ %运算符**

在这种技术中，我们用 10^K 对每个数字取模，得到每个数字的最后 k 个数字。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Rear K digits from Numbers
# Using list comprehension + % operator 

# initializing list
test_list = [5645, 23567, 34543, 87652, 2342]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# Getting remainder for each element
res = [ele % (10 ** K) for ele in test_list]

# printing result 
print("Rear K digits of elements ? : " + str(res))
```

**Output**

```py
The original list is : [5645, 23567, 34543, 87652, 2342]
Rear K digits of elements ? : [645, 567, 543, 652, 342]

```

**方法二:使用** [**str()**](https://www.geeksforgeeks.org/python-str-function/) **+切片**

在本例中，我们使用列表切片执行获取后面元素的任务，并且 str()用于将每个元素转换为字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Rear K digits from Numbers
# Using str() + slicing 

# initializing list
test_list = [5645, 23567, 34543, 87652, 2342]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# getting integer using int() after slicing string
res = [int(str(idx)[-K:]) for idx in test_list]

# printing result 
print("Rear K digits of elements ? : " + str(res))
```

**Output**

```py
The original list is : [5645, 23567, 34543, 87652, 2342]
Rear K digits of elements ? : [645, 567, 543, 652, 342]

```