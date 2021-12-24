# 如何破解 Python 中的多个循环？

> 原文:[https://www . geesforgeks . org/如何破解 python 中的多个循环/](https://www.geeksforgeeks.org/how-to-break-out-of-multiple-loops-in-python/)

在本文中，我们将看到如何在 Python 中打破多个循环。例如，给我们一个列表 arr 和一个整数 x 的列表。任务是按顺序遍历每个嵌套列表，并一直显示元素，直到找到一个等于 x 的元素。如果找到这样的元素，将显示一条适当的消息，代码必须停止显示任何更多的元素。

```
Input: arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]], x = 6
Output:
1
2
3
Element found
Input: arr = [[10, 20, 30], [40, 50, 60, 70]], x = 50
Output:
10
20
30
40
Element found
```

解决这个问题的直接方法是使用 for 循环遍历 arr 的所有元素，并使用嵌套的 for 循环遍历 arr 中每个嵌套列表的所有元素，并继续打印它们。如果遇到一个等于 x 的元素，将显示适当的消息，代码必须从两个循环中断开。

但是，如果我们只使用一个 break 语句，代码将只终止内部循环，外部循环将继续运行，这是我们不希望发生的。

## 蟒蛇 3

```
def elementInArray(arr, x):

    # Iterating through all
    # lists present in arr:
    for i in arr:

        # Iterating through all the elements
        # of each of the nested lists in arr:
        for j in i:

            # Checking if any element in the
            # nested list is equal to x:
            if j == x:
                print('Element found')
                break
            else:
                print(j)

# Driver Code:
arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
x = 4
elementInArray(arr, x)
```

**输出:**

```
1
2
3
Element found
7
8
9
```

在上面的例子中，一旦找到 4，break 语句就终止了内部循环，并且相同嵌套列表(5，6)的所有其他元素都被跳过，但是代码没有终止外部循环，然后外部循环继续到下一个嵌套列表，并且还打印了它的所有元素。

**方法 1:使用** **返回语句**

定义一个函数，并在该函数中放置循环。使用 return 语句可以直接结束函数，从而打破所有的循环。

## 蟒蛇 3

```
# Python code to break out of
# multiple loops by defining a
# function and using return statement

def elementInArray(arr, x):

    # Iterating through all
    # lists present in arr:
    for i in arr:

        # Iterating through all the elements
        # of each of the nested lists in arr:
        for j in i:

            # Checking if any element in the
            # nested list is equal to x and returning
            # the function if such element is found
            # else printing the element:
            if j == x:
                print('Element found')
                return
            else:
                print(j)

# Driver Code:
arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
x = 4
elementInArray(arr, x)
```

**输出:**

```
1
2
3
Element found
```

**方法 2:使用 else:继续**

更简单的方法是在内部循环之后使用包含 continue 语句的 else 块，然后在外部循环中的 else 块之后添加 break 语句。如果内部循环由于内部循环中给出的 break 语句而终止，那么内部循环之后的 else 块将不会被执行，else 块之后的 break 语句也将终止外部循环。另一方面，如果内部循环完成而没有遇到任何 break 语句，那么包含 continue 语句的 else 块将被执行，而外部循环将继续运行。即使循环的数量增加，想法也是一样的。

## 蟒蛇 3

```
# Python code to break out of multiple
# loops by using an else block

def elementInArray(arr, x):

    # Iterating through all
    # lists present in arr:
    for i in arr:

        # Iterating through all the elements
        # of each of the nested lists in arr:
        for j in i:

            # Checking if any element in the
            # nested list is equal to x:
            if j == x:
                print('Element found')
                break
            else:
                print(j)

        # If the inner loop completes without encountering
        # the break statement then the following else
        # block will be executed and outer loop will
        # continue to the next value of i:
        else:
            continue

        # If the inner loop terminates due to the
        # break statement, the else block will not
        # be executed and the following break
        # statement will terminate the outer loop also:
        break

# Driver Code:
arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
x = 4
elementInArray(arr, x)
```

**输出:**

```
1
2
3
Element found
```

**方法 3:使用标志变量**

打破多个循环的另一种方法是用 False 值初始化标志变量。就在脱离内部循环之前，可以为变量分配一个真值。外部循环必须在内部循环之后包含 if 块。if 块必须检查标志变量的值，并包含一个 break 语句。如果标志变量为真，则 If 块将被执行，并且也将脱离内部循环。否则，外环将继续。

## 蟒蛇 3

```
# Python code to break out of multiple
# loops by using a flag variable

def elementInArray(arr, x):
    flag = False  # Defining the flag variable

    # Iterating through all
    # lists present in arr:
    for i in arr:

        # Iterating through all the elements
        # of each of the nested lists in arr:
        for j in i:

            # Checking if any element in the
            # nested list is equal to x
            # and assigning True value to
            # flag if the condition is met
            # else printing the element j:
            if j == x:
                flag = True
                print('Element found')
                break
            else:
                print(j)

        # If the inner loop terminates due to
        # the break statement and flag is True
        # then the following if block will
        # be executed and the break statement in it
        # will also terminate the outer loop. Else,
        # the outer loop will continue:
        if flag == True:
            break

# Driver Code:
arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
x = 4
elementInArray(arr, x)
```

**输出:**

```
1
2
3
Element found
```