# Python |以百分比计算连续折扣中的等价折扣

> 原文:[https://www . geeksforgeeks . org/python-查找等值折扣-连续折扣-百分比/](https://www.geeksforgeeks.org/python-find-the-equivalent-discount-in-successive-discounts-in-percentages/)

你会得到 n 个连续的百分比折扣。你的任务是找到等价的百分比折扣。输入将包含一个列表，列表中的每个元素将以百分比折扣，符号为负。
**例:**

```
Input :  a = [-10, -35, -60, -75]
Output :  -94.14

Input :  a = [-5, -20, -10.-23]
Output :  -49.08
```

逐次变化= A + B + (A*B) / 100
**这个公式是如何工作的？**
设 x 为初始值。A%变化后，x 的值变为(x + x*A/100)。连续 B%变化后，x 的值变为(x + x*A/100) + (x + x*A/100)*B/100。所以 x 值的增量是 x*(A + B + A*B/100)/100。百分比方面，我们可以说数值增加了(A+b+ A * B/100%)%
**趋近:**

*   简单地说，在 arr[0]和 arr[1]之间应用连续的变化公式，并将结果存储在结果变量中。
*   现在，使用上述公式计算结果和 arr[2]之间的连续变化，并将结果存储在结果变量中，以此类推。

**代码:Python 程序，用于在百分比形式的连续折扣中查找等价折扣。**

## 蟒蛇 3

```
# Function to find the equivalent discount in
# successive discounts in percentages
def equivalentdis(a):
    if(len(a)== 1):
        return(a[0])
    else:
        # successive change from two = a[0] + a[1]+ (a[0]*a[1])/100
        change =(a[0] + a[1]+ (a[0]*a[1])/100)
        for i in range(2, len(a)):
            # iterating a[0] + a[1]+ (a[0]*a[1])/100
            # len(a)-2 times
            change = (change + a[i]+(change * a[i]) / 100)
        return change;
# Driver code
print(equivalentdis([-10, -20, -30, -40]))

```

**输出:**

```
-69.75999999999999
```