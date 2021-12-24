# 科尔莫戈罗夫-斯米尔诺夫试验(KS 试验)

> 原文:[https://www . geeksforgeeks . org/Kolmogorov-Smirnov-test-ks-test/](https://www.geeksforgeeks.org/kolmogorov-smirnov-test-ks-test/)

**Kolmogorov–Smirnov 测试**是一种非常有效的方法，可以确定两个样本是否存在显著差异。它通常用于检查随机数的一致性。均匀性是任何随机数发生器最重要的特性之一，可以使用 Kolmogorov-Smirnov 测试来测试它。

科尔莫戈罗夫-斯米尔诺夫检验也可以用来检验两个潜在的一维概率分布是否不同。这是一种非常有效的方法，可以确定两个样本是否存在显著差异。

Kolmogorov-Smirnov 统计量量化了样本的经验分布函数和参考分布的累积分布函数之间的距离，或者两个样本的经验分布函数之间的距离。

为了使用检验随机数一致性的测试，我们使用了 U[0，1]的 CDF(累积分布函数)。

```py
F(x)= x for 0<=x<=1
```

经验 CDF，`Sn(x)= (number of R1, R2…Rn < x)/N array of random numbers`，随机数必须在[0，1]范围内。

#### 使用的假设–

**H0(零假设):**零假设假设数字在 0-1 之间均匀分布。如果我们能够拒绝零假设，这意味着数字不是均匀分布在 0-1 之间。未能拒绝零假设，虽然不一定意味着数字遵循均匀分布。

**算法:**

```py
-> Rank the N random numbers in ascending order.
-> Calculate D+ as max(i/N-Ri) for all i in(1, N)
-> Calculate D- as max(Ri-((i-1)/N)) for all i in(1, N)
-> Calculate D as max(sqrt(N) * D+, sqrt(N) * D-)
-> If D>D(alpha) 
    Rejects Uniformity
   else
    It fails to reject the Null Hypothesis.
```

下面是上面算法的 Python 实现:

```py
import random

N = int(input("Enter the size of random numbers to be produced : "))
D_plus =[]
D_minus =[]
_random =[]

# Rank the N random numbers
for i in range(0, N):
    _random.append(random.random())
    _random.sort()

# Calculate max(i/N-Ri)
for i in range(1, N + 1):
    x = i / N - _random[i-1]
    D_plus.append(x)

# Calculate max(Ri-((i-1)/N))
for i in range(1, N + 1):
    y =(i-1)/N
    y =_random[i-1]-y
    D_minus.append(y)

# Calculate max(D+, D-)
ans = max(sqrt(N) * D_plus, sqrt(N) * D_minus)
print("Value of D is :")
print(ans)
```

参考–[https://dl.acm.org/doi/pdf/10.1145/355719.355724](https://dl.acm.org/doi/pdf/10.1145/355719.355724)