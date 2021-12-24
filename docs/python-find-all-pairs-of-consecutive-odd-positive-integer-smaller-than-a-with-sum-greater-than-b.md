# Python–查找所有小于 a 且和大于 b 的连续奇数正整数对

> 原文:[https://www . geeksforgeeks . org/python-查找所有连续奇数正整数对-大于 b 的和小于 a/](https://www.geeksforgeeks.org/python-find-all-pairs-of-consecutive-odd-positive-integer-smaller-than-a-with-sum-greater-than-b/)

给定两个正整数 *a* 和 *b* ，任务是用 python 编写一个程序，找出所有小于第一个数 *a* 的连续奇数对，它们的和应该大于第二个数 *b* 。

**示例:**

```
Input:
a = 60
b = 100
Output:
Pairs of consecutive number are:
51 , 53
53 , 55
55 , 57
57 , 59

Input:
a = 20
b = 200
Output:
None
```

**进场:**

给出两个数字，然后检查它们是否为正整数，并检查第一个数字是否大于第二个数字的一半。然后我们将检查奇数正整数，并在变量 *a.* 中赋值。在*而*语句中，找到并打印奇数连续整数对。

**例 1:**

## 蟒蛇 3

```
# input first and second number
a = 60
b = 100

print('a =', a)
print('b =', b)

# check the first number should be greater
# than the half of second number and both number
# should be positive integer
if(a > 0 and b > 0 and a > b/2):

    # to ensure value in firstNum variable
    # must be odd positive integer
    if(a % 2 == 0):
        a -= 1
    else:
        a -= 2

    b //= 2
    print("Pairs of consecutive number are:")

    # find the pairs of odd
    # consecutive positive integer
    while(b <= a):
        if(b % 2 != 0):
            x = b
            if(x + 2 <= a):
                print(x, ',', x+2)

        b += 1
else:
  print("None")
```

**输出:**

```
a = 60
b = 100
Pairs of consecutive number are:
51 , 53
53 , 55
55 , 57
57 , 59
```

**例 2:**

## 蟒蛇 3

```
# input first and second number
a = 20
b = 200

print('a =', a)
print('b =', b)

# check the first number should be greater
# than the half of second number and both number
# should be positive integer
if(a > 0 and b > 0 and a > b/2):

    # to ensure value in firstNum variable
    # must be odd positive integer
    if(a % 2 == 0):
        a -= 1
    else:
        a -= 2

    b //= 2
    print("Pairs of consecutive number are:")

    # find the pairs of odd
    # consecutive positive integer
    while(b <= a):
        if(b % 2 != 0):
            x = b
            if(x + 2 <= a):
                print(x, ',', x+2)

        b += 1
else:
    print("None")
```

**输出:**

```
a = 20
b = 200
None
```