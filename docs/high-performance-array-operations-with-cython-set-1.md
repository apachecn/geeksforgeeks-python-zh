# 利用 Cython 进行高性能阵列操作|第 1 集

> 原文:[https://www . geesforgeks . org/高性能-阵列-操作-with-cython-set-1/](https://www.geeksforgeeks.org/high-performance-array-operations-with-cython-set-1/)

虽然像 NumPy 这样的库可以执行高性能的数组处理功能来操作数组。但是 Cython 也可以做得很好。但是怎么做呢？

**代码#1 : Cython 函数，用于裁剪简单的 1D 双精度数组中的值**

```
# work.pyx (Cython file)
cimport cython

@cython.boundscheck(False)
@cython.wraparound(False)

cpdef clip(double[:] a, double min, double max, double[:] out):

    '''
    Clip the values in a to be between 
    min and max. Result in out
    '''
    if min > max:
        raise ValueError("min must be <= max")

    if a.shape[0] != out.shape[0]:
        raise ValueError("input and output arrays must be the same size")

    for i in range(a.shape[0]):
        if a[i] < min:
            out[i] = min
        elif a[i] > max:
            out[i] = max
        else:
            out[i] = a[i]
```

**`work.py`** 文件需要编译和构建扩展名。

**代码#2 :**

```
# importing libraries
from distutils.core import setup
from distutils.extension import Extension
from Cython.Distutils import build_ext

ext_modules = [Extension(
        'sample', 
        ['sample.pyx'])]

setup(name = 'Sample app', 
      cmdclass = {'build_ext': build_ext}, 
      ext_modules = ext_modules)
```

执行完上面的任务，现在我们可以检查结果函数 clips 数组的工作情况了，有很多不同种类的数组对象。

**代码#3:裁剪数组的工作。**

```
# array module example
import work
import array
import numpy

arr = array.array('d', [1, -3, 4, 7, 2, 0])
print ("Array : ", arr)

# Clipping the array
work.clip(arr, 1, 4, arr)
print ("\nClipping array : ", arr)

# numpy example
arr2 = numpy.random.uniform(-10, 10, size = 1000000)
print ("\narr2 : \n", arr2)

arr3 = numpy.zeros_like(arr2)
print ("\narr3 : \n", arr3)

work.clip(arr2, -5, 5, arr3)
print ("\nClipping arr3 : \n", ar3)
print ("\nMinimum in arr3 : ", min(arr3))
print ("\nMaximum in arr3 : ", min(arr3))
```

**输出:**

```
Array : array('d', [1.0, -3.0, 4.0, 7.0, 2.0, 0.0])

Clipping array : array('d', [1.0, 1.0, 4.0, 4.0, 2.0, 1.0])

arr2 : 
[-9.55546017, 7.45599334, 0.69248932, ..., 0.69583148, -3.86290931, 2.37266888]

arr3 : array([ 0., 0., 0., ..., 0., 0., 0.])

Clipping arr3 : 
[-5., 5., 0.69248932, ..., 0.69583148, -3.86290931, 2.37266888]

Minimum in arr3 : 5.0

Maximum in arr3 : 5.0

```