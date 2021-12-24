# 任意数量集合的笛卡尔乘积

> 原文:[https://www . geeksforgeeks . org/cartesian-任意数量集合的乘积/](https://www.geeksforgeeks.org/cartesian-product-of-any-number-of-sets/)

给定 N 个集合。任务是编写一个程序，以给定的顺序执行所有集合的笛卡尔乘积。
**例** :

```
Input:
1st set: 1 2
2nd set: A 
3rd set: x 
4th set: 5 6
Output:
[['1', 'A', 'x', '5'],
 ['1', 'A', 'x', '6'],
 ['2', 'A', 'x', '5'],
 ['2', 'A', 'x', '6']]

Input:
1st set: 1 2
2nd set: A 
3rd set: x y z 
Output:
[['1', 'A', 'x'],
 ['1', 'A', 'y'],
 ['1', 'A', 'z'],
 ['2', 'A', 'x'],
 ['2', 'A', 'y'],
 ['2', 'A', 'z']]
```

**方法:**该方法是在开始时计算集-1 和集-2 的乘积，然后集-1 和集-2 的结果将具有集-3 的乘积，然后集-1、集-2、集-3 的结果将具有集-4 的笛卡尔乘积，以此类推，直到集-n。
下面是上述方法的实现。

## 蟒蛇 3

```
# Python program for cartesian
# product of N-sets

# function to find cartesian product of two sets
def cartesianProduct(set_a, set_b):
    result =[]
    for i in range(0, len(set_a)):
        for j in range(0, len(set_b)):

            # for handling case having cartesian
            # product first time of two sets
            if type(set_a[i]) != list:        
                set_a[i] = [set_a[i]]

            # coping all the members
            # of set_a to temp
            temp = [num for num in set_a[i]]

            # add member of set_b to
            # temp to have cartesian product    
            temp.append(set_b[j])            
            result.append(temp) 

    return result

# Function to do a cartesian
# product of N sets
def Cartesian(list_a, n):

    # result of cartesian product
    # of all the sets taken two at a time
    temp = list_a[0]

    # do product of N sets
    for i in range(1, n):
        temp = cartesianProduct(temp, list_a[i])

    print(temp)

# Driver Code
list_a = [[1, 2],          # set-1
          ['A'],          # set-2
          ['x', 'y', 'z']]   # set-3

# number of sets
n = len(list_a)

# Function is called to perform
# the cartesian product on list_a of size n
Cartesian(list_a, n)
```

**Output:** 

```
[[1, 'A', 'x'],
 [1, 'A', 'y'],
 [1, 'A', 'z'], 
 [2, 'A', 'x'], 
 [2, 'A', 'y'], 
 [2, 'A', 'z']]
```