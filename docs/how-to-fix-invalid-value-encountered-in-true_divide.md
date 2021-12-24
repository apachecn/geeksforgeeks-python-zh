# 如何修复:true_divide

中遇到无效值

> 原文:[https://www . geeksforgeeks . org/如何修复在 true_divide/](https://www.geeksforgeeks.org/how-to-fix-invalid-value-encountered-in-true_divide/) 中遇到的无效值

在本文中，我们将修复 Python 中 true_divide 中遇到的无效值。true_divide 中遇到的无效值是一个运行时警告，当我们在 NumPy 数组的元素之间执行无效的除法运算时会出现该警告。无效除法的一个例子是 0/0。

**注意:**由于它只是一个警告，代码不会停止执行，**返回一个非数值**，即 nan(或)inf(无穷大)。

NumPy 数组之间的除法运算可以使用 NumPy 包中的 **divide()** 来完成，该包允许 2 个数组的对应元素之间的除法运算。

## 蟒蛇 3

```
# import necessary packages
import numpy as np

# Create 2 Numpy arrays
Array1 = np.array([6, 2, 0])
Array2 = np.array([3, 2, 0])

# divide the values in Array1 by the
# values in Array2
np.divide(Array1, Array2)
```

**输出:**

> c:\ ProgramData \ anaconda 3 \ lib \ site-packages \ ipykernel _ launcher . py:9:RuntimeWarning:true _ divide 中遇到无效值
> 
> if __name__ == '__main__ ':
> 
> **结果-** 数组(【2。, 1.，nan])

### 解释:

这里我们将数组 1 的元素除以数组 2 的元素。所以它返回商值。

*   6/3=2(有效操作)
*   2/2=1(有效操作)
*   0/0，这是一个无效的操作，因此会引发警告，并将结果作为 Not Number(nan)返回。

### 解决方案:

我们可以通过使用 seterr 方法来修复这个运行时警告，该方法将 invalid 作为参数，并将 ignore 作为值赋给它。这样，它可以隐藏包含无效的警告消息。

> **语法:**num py . set err(invalid =‘ignore’)

## 蟒蛇 3

```
# import necessary packages
import numpy as np

# Create 2 Numpy arrays
Array1 = np.array([6, 2, 0])
Array2 = np.array([3, 2, 0])

# Supress/hide the warning
np.seterr(invalid='ignore')

# divide the values in Array1 by the 
# values in Array2
np.divide(Array1, Array2)
```

**输出:**

```
array([ 2.,  1., nan])
```