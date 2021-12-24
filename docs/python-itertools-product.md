# python—http 工具。产品()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-product/

在数学术语中，两个集合的笛卡尔乘积被定义为所有有序对(A，b)的集合，其中 A 属于 A，b 属于 b。为了更好地理解，考虑下面的例子。
**例:**

> **输入:**arr 1 =【1，2，3】
> arr 2 =【5，6，7】
> **输出:**【(1，5)、(1，6)、(1，7)、(2，5)、(2，6)、(2，7)、(3，5)、(3，6)、(3，7)】
> **输入:**arr 1 =【10，12】
> arr 2 =【8，9，10】
> **输出:【T11**

上面的解决方案可以通过循环来完成，但是我们将使用一个特殊的 Python 库 **itertools.product()** 来查找笛卡尔乘积。让我们看一下这个 Python 库的工作和用例。

#### Python 中的 Itertools 是什么？

[Python Itertools](https://www.geeksforgeeks.org/python-itertools/) 是 Python 中的一个库，它由多个方法组成，这些方法用于各种迭代器中，以计算快速且代码高效的解决方案。

> *itertools.product()属于 Python itertools 库的名为* [*组合迭代器*](https://www.geeksforgeeks.org/python-itertools/#combine) *的类别。*

**注:**更多信息请参考[Python Itertools](https://www.geeksforgeeks.org/python-itertools/#combine)T4】

#### itertools.product()是做什么的？

itertools.product()用于从给定的迭代器中找到笛卡尔乘积，输出是字典顺序的。itertools.product()有两种不同的用法:

*   **ITER tools . product(* iterables，repeat=1):**
    它返回所提供的 ITER able 与其自身的笛卡尔乘积，次数由可选关键字“repeat”指定。例如，乘积(arr，repeat=3)与乘积(arr，arr，arr)意思相同。
*   **ITER tools . product(* iterables):**
    它返回作为参数提供的所有 ITER able 的笛卡尔乘积。例如，产品(arr1、arr2、arr3)。

**示例:**

## 蟒蛇 3

```
from itertools import product

def cartesian_product(arr1, arr2):

    # return the list of all the computed tuple
    # using the product() method
    return list(product(arr1, arr2))

# Driver Function
if __name__ == "__main__":
    arr1 = [1, 2, 3]
    arr2 = [5, 6, 7]
    print(cartesian_product(arr1, arr2))
```

**输出:**

> [(1, 5), (1, 6), (1, 7), (2, 5), (2, 6), (2, 7), (3, 5), (3, 6), (3, 7)]