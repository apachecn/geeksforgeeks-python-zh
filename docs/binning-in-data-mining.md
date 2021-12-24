# 数据挖掘中的宁滨

> 原文:[https://www.geeksforgeeks.org/binning-in-data-mining/](https://www.geeksforgeeks.org/binning-in-data-mining/)

数据宁滨，**分时段**是一种数据预处理方法，用于最小化小观测误差的影响。原始数据值被划分为称为箱的小间隔，然后它们被为该箱计算的一般值代替。这将对输入数据产生平滑效果，并且还可能减少在小数据集的情况下过度拟合的机会
有两种方法将数据划分为面元:

1.  **等频宁滨:**仓具有相同的频率。
2.  **等宽宁滨:**仓具有等宽，每个仓的范围定义为[min + w]，[min + 2w] …。[最小+西北]其中 **w =(最大–最小)/(箱数)。**

**等频:**

```py
Input:[5, 10, 11, 13, 15, 35, 50, 55, 72, 92, 204, 215] 

Output:
[5, 10, 11, 13]
[15, 35, 50, 55]
[72, 92, 204, 215]
```

**等宽:**

```py
Input: [5, 10, 11, 13, 15, 35, 50, 55, 72, 92, 204, 215]

Output:
[5, 10, 11, 13, 15, 35, 50, 55, 72]
[92]
[204, 215]
```

**代码:比宁技术实现:**

## 巴拉圭

```py
# equal frequency
def equifreq(arr1, m):   
    a = len(arr1)
    n = int(a / m)
    for i in range(0, m):
        arr = []
        for j in range(i * n, (i + 1) * n):
            if j >= a:
                break
            arr = arr + [arr1[j]]
        print(arr)

# equal width
def equiwidth(arr1, m):
    a = len(arr1)
    w = int((max(arr1) - min(arr1)) / m)
    min1 = min(arr1)
    arr = []
    for i in range(0, m + 1):
        arr = arr + [min1 + w * i]
    arri=[]

    for i in range(0, m):
        temp = []
        for j in arr1:
            if j >= arr[i] and j <= arr[i+1]:
                temp += [j]
        arri += [temp]
    print(arri)

# data to be binned
data = [5, 10, 11, 13, 15, 35, 50, 55, 72, 92, 204, 215]

# no of bins
m = 3

print("equal frequency binning")
equifreq(data, m)

print("\n\nequal width binning")
equiwidth(data, 3)
```

**输出:**

```py
equal frequency binning
[5, 10, 11, 13]
[15, 35, 50, 55]
[72, 92, 204, 215]

equal width binning
[[5, 10, 11, 13, 15, 35, 50, 55, 72], [92], [204, 215]] 
```