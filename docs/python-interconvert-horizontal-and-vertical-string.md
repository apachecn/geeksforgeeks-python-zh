# Python–相互转换水平和垂直字符串

> 原文:[https://www . geesforgeks . org/python-interconvert-横纵字符串/](https://www.geeksforgeeks.org/python-interconvert-horizontal-and-vertical-string/)

给定一个字符串，如果是水平的就转换成垂直的，反之亦然。

> **输入**:test _ str = ' geeksforgeeks '
> **输出**:g
> e
> e
> k
> s
> **说明**:横线转换为竖线。
> 
> **输入**:test _ str = g
> e
> e
> k
> s
> **输出**:【极客】
> **解释**:竖线转换为横线。

**方法#1:【水平到垂直】使用循环+ "\n"**

在这种情况下，我们在每个字符后添加换行符，以便每个元素在下一行呈现。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Interconvert Horizontal and Vertical String
# using [Horizontal to Vertical] using loop + "\n"

# initializing string
test_str = 'geeksforgeeks'

# printing original String
print("The original string is : " + str(test_str))

# using loop to add "\n" after each character 
res = ''
for ele in test_str:
    res  += ele + "\n" 

# printing result 
print("The converted string : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The converted string : g
e
e
k
s
f
o
r
g
e
e
k
s

```

**方法 2:[垂直到水平]使用 replace() + "\n"**

在这种情况下，我们通过用空字符串替换来删除“\n”来执行转换任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Interconvert Horizontal and Vertical String
# using [Vertical to Horizontal] using replace() + "\n"

# initializing string
test_str = 'g\ne\ne\nk\ns\nf\no\nr\ng\ne\ne\nk\ns\n'

# printing original String
print("The original string is : " + str(test_str))

# using replace() + "\n" to solve this problem
res = test_str.replace("\n", "")

# printing result 
print("The converted string : " + str(res)) 
```

**Output**

```
The original string is : g
e
e
k
s
f
o
r
g
e
e
k
s

The converted string : geeksforgeeks

```