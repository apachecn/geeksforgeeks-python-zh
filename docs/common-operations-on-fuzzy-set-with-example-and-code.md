# 带示例和代码的模糊集常见运算

> 原文:[https://www . geesforgeks . org/common-operations-on-fuzzy-set-with-example-and-code/](https://www.geeksforgeeks.org/common-operations-on-fuzzy-set-with-example-and-code/)

**什么是模糊集？**

模糊是指不清楚或模糊的东西。因此，模糊集是一个集合，其中每个键都与值相关联，基于确定性，该值在 0 到 1 之间。该值通常称为隶属度。模糊集在正常的集合符号上用波浪符号表示。

**对带编码的模糊集的运算:**

**1。联合:**

考虑由 A 和 B 表示的 2 个模糊集，然后让我们考虑 Y 是它们的并集，那么对于 A 和 B 的每个成员，Y 将是:

```
 degree_of_membership(Y)= max(degree_of_membership(A), degree_of_membership(B)) 

```

**示例:**

## 蟒蛇 3

```
# Example to Demonstrate the 
# Union of Two Fuzzy Sets
A = dict()
B = dict()
Y = dict()

A = {"a": 0.2, "b": 0.3, "c": 0.6, "d": 0.6}
B = {"a": 0.9, "b": 0.9, "c": 0.4, "d": 0.5}

print('The First Fuzzy Set is :', A)
print('The Second Fuzzy Set is :', B)

for A_key, B_key in zip(A, B):
    A_value = A[A_key]
    B_value = B[B_key]

    if A_value > B_value:
        Y[A_key] = A_value
    else:
        Y[B_key] = B_value

print('Fuzzy Set Union is :', Y)
```

**Output**

```
The First Fuzzy Set is : {'a': 0.2, 'b': 0.3, 'c': 0.6, 'd': 0.6}
The Second Fuzzy Set is : {'a': 0.9, 'b': 0.9, 'c': 0.4, 'd': 0.5}
Fuzzy Set Union is : {'a': 0.9, 'b': 0.9, 'c': 0.6, 'd': 0.6}

```

**2。路口:**

考虑由 A 和 B 表示的 2 个模糊集，然后让我们考虑 Y 是它们的交集，那么对于 A 和 B 的每个成员，Y 将是:

```
degree_of_membership(Y)= min(degree_of_membership(A), degree_of_membership(B)) 

```

**示例:**

## 蟒蛇 3

```
# Example to Demonstrate
# Intersection of Two Fuzzy Sets
A = dict()
B = dict()
Y = dict()

A = {"a": 0.2, "b": 0.3, "c": 0.6, "d": 0.6}
B = {"a": 0.9, "b": 0.9, "c": 0.4, "d": 0.5}

print('The First Fuzzy Set is :', A)
print('The Second Fuzzy Set is :', B)

for A_key, B_key in zip(A, B):
    A_value = A[A_key]
    B_value = B[B_key]

    if A_value < B_value:
        Y[A_key] = A_value
    else:
        Y[B_key] = B_value
print('Fuzzy Set Intersection is :', Y)
```

**Output**

```
The First Fuzzy Set is : {'a': 0.2, 'b': 0.3, 'c': 0.6, 'd': 0.6}
The Second Fuzzy Set is : {'a': 0.9, 'b': 0.9, 'c': 0.4, 'd': 0.5}
Fuzzy Set Intersection is : {'a': 0.2, 'b': 0.3, 'c': 0.4, 'd': 0.5}

```