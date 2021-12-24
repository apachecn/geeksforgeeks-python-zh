# 在 Python 中以不同的概率从列表中选择元素

> 原文:[https://www . geesforgeks . org/从 python 中不同概率列表中选择元素/](https://www.geeksforgeeks.org/choose-elements-from-list-with-different-probability-in-python/)

你有没有想过在 Python 中如何从不同概率的列表中选择随机元素？在本文中，我们将讨论如何做到这一点。让我们首先考虑下面的例子。

T2T4

```
import random

sam_Lst = [10, 20, 3, 4, 100]
ran = random.choice(sam_Lst)
print(ran)
```

T5

在上面的例子中，从列表中获得任何元素的概率是相等的。但是我们想要这样的方法，其中从列表中选择一个元素的概率是不同的。这在 Python 中被称为加权随机选择。为了在 Python 中找到加权随机选择，存在两种方式:

1.  **[relative weight]**
2.  **Cumulative weight**

在这种情况下对我们有帮助的函数是[](https://www.geeksforgeeks.org/random-choices-method-in-python/)****。**该功能允许在 python 中进行带替换的加权随机选择。**

****语法:****

> **随机选择(人口，权重=无，* cum _ weights =无，k=1)**

**这里，“重量”参数起着重要的作用。**

****情况 1:使用相对重量****

**分配给元素的权重称为相对权重。**

****例 1:****

 **## 蟒 3

```
import random

# Creating a number list
num_lst = [1, 22, 43, 19, 13, 29]

print(random.choices(num_lst, weights=(
  14, 25, 30, 45, 55, 10), k=6))
```** 

****输出:****

```
[19, 19, 13, 22, 13, 13] 
```

**在上面的例子中，我们给列表的每个元素分配**权重**。**13′**元素的权重最高，为 55，因此其出现的概率最大。正如我们在输出中看到的，元素 13 出现了 3 次，19 出现了 2 次，以此类推。所以，现在从列表中选择一个元素的概率是不同的。**

****例 2:****

 **## 蟒 3

```
import random

# Creating a name list
name_lst = ['October', 'November', 'December',
            'January', 'March', 'June']

print(random.choices(name_lst, weights=(
    40, 25, 30, 5, 15, 80), k=3))
```** 

****输出:****

```
['June', 'October', 'June']
```

**在上面的例子中，元素' **June'** 的权重最大，因此它的选择概率最大。这里，k=3，这意味着我们只选择列表中的前 3 个元素。**

****例 3:****

 **## 蟒 3

```
import random

# Creating a name list
name_lst = ['Fit', 'Infected', 'Recovered', 'Danger']

# Using FOR loop
# to choose the element from list with
# different probability
for i in range(6):
    print("Random choice", i+1)

    randomele = random.choices(name_lst, weights=(
      50, 80, 10, 5), k=1)

    print(randomele[0])
```** 

****输出:****

```
Random choice 1
Recovered
Random choice 2
Danger
Random choice 3
Infected
Random choice 4
Infected
Random choice 5
Infected
Random choice 6
Fit 
```

**在上面的例子中，我们使用 FOR 循环以不同的概率从列表中选择一个元素。**

****案例 2:使用累计权重****

**一个元素的累积权重是通过将它的前一个元素的权重和它自己的权重相加来确定的。**

****例 1:****

 **## 蟒 3

```
import random

# Creating a number list
num_lst = [1, 22, 93, 19, 13, 25]

print(random.choices(num_lst, cum_weights=(
    7, 13, 15, 20, 25, 20), k=6))
```** 

****输出:****

```
[1, 22, 93, 22, 19, 1] 
```

**在上面的例子中，元素'**19 '**的累计权重最大，所以它被选择的概率也会最大。**

****例 2:****

 **## 蟒 3

```
import random

# Creating a name list
name_lst = ['October', 'November', 'December',
            'January', 'March', 'June']

print(random.choices(name_lst, cum_weights=(
  40, 20, 3, 7, 15, 15), k=3))
```** 

****输出:****

```
['January', 'March', 'January'] 
```

**在上面的例子中，我们选择 k=3，所以我们得到了选择概率最大的前 3 个元素。**

****例 3:****

 **## 蟒 3

```
import random

# Creating a name list 
name_lst = ['October', 'November', 'December', 
            'January', 'March', 'June']

# Using FOR loop
# to choose the element from list with
# different probability
for i in range(6):
    print("Random choice", i+1)

    randomele = random.choices(name_lst, cum_weights=(
      7, 13, 15, 20, 25, 20), k=1)

    print(randomele[0])
```** 

****输出:****

```
Random choice 1
November
Random choice 2
January
Random choice 3
October
Random choice 4
December
Random choice 5
November
Random choice 6
January 
```

**在上面的例子中，我们使用 FOR 循环以不同的概率从列表中选择一个元素。**

****注:**T2 k 的值取决于用户，由于其相对权重，所以**权重的总和**可以**超过 100。****