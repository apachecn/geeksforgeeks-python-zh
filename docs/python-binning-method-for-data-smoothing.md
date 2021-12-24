# 数据平滑的 Python |宁滨方法

> 原文:[https://www . geeksforgeeks . org/python-宁滨-数据平滑方法/](https://www.geeksforgeeks.org/python-binning-method-for-data-smoothing/)

**先决条件:** [ML |宁滨或离散化](https://www.geeksforgeeks.org/ml-binning-or-discretization/)

宁滨方法用于平滑数据或处理有噪声的数据。在这种方法中，首先对数据进行排序，然后将排序后的值分配到多个桶或箱中。由于宁滨方法参考了值的邻域，所以它们执行局部平滑。

**有三种方法来执行平滑–**

> **通过面元手段平滑:**在通过面元手段平滑中，面元中的每个值都被面元的平均值所代替。
> **按箱中值平滑:**在此方法中，每个箱值都被其箱中值替换。
> **按面元边界平滑:**在按面元边界平滑中，给定面元中的最小值和最大值被标识为面元边界。然后，每个箱值被最接近的边界值替换。

**进场:**

1.  给定数据集的数组排序。
2.  将范围划分为 N 个区间，每个区间包含大致相同数量的样本(等深度划分)。
3.  在每行中存储平均值/中间值/边界。

**示例:**

```
Sorted data for price (in dollars): 4, 8, 9, 15, 21, 21, 24, 25, 26, 28, 29, 34

Smoothing by bin means:
      - Bin 1: 9, 9, 9, 9
      - Bin 2: 23, 23, 23, 23
      - Bin 3: 29, 29, 29, 29

Smoothing by bin boundaries:
      - Bin 1: 4, 4, 4, 15
      - Bin 2: 21, 21, 25, 25
      - Bin 3: 26, 26, 26, 34

Smoothing by bin median:
      - Bin 1: 9 9, 9, 9
      - Bin 2: 24, 24, 24, 24
      - Bin 3: 29, 29, 29, 29

```

以下是上述算法的 Python 实现–

```
import numpy as np  
import math
from sklearn.datasets import load_iris
from sklearn import datasets, linear_model, metrics 

# load iris data set
dataset = load_iris()   
a = dataset.data
b = np.zeros(150)

# take 1st column among 4 column of data set 
for i in range (150):
    b[i]=a[i,1]   

b=np.sort(b)  #sort the array

# create bins
bin1=np.zeros((30,5)) 
bin2=np.zeros((30,5))
bin3=np.zeros((30,5))

# Bin mean
for i in range (0,150,5):
    k=int(i/5)
    mean=(b[i] + b[i+1] + b[i+2] + b[i+3] + b[i+4])/5
    for j in range(5):
        bin1[k,j]=mean
print("Bin Mean: \n",bin1)

# Bin boundaries
for i in range (0,150,5):
    k=int(i/5)
    for j in range (5):
        if (b[i+j]-b[i]) < (b[i+4]-b[i+j]):
            bin2[k,j]=b[i]
        else:
            bin2[k,j]=b[i+4]       
print("Bin Boundaries: \n",bin2)

# Bin median
for i in range (0,150,5):
    k=int(i/5)
    for j in range (5):
        bin3[k,j]=b[i+2]
print("Bin Median: \n",bin3)
```