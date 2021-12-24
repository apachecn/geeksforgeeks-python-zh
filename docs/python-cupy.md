# Python CuPy

> 原文:[https://www.geeksforgeeks.org/python-cupy/](https://www.geeksforgeeks.org/python-cupy/)

`NumPy` 无疑是任何 pythonic 代码处理`numpy.ndarray` (n 维矩阵数组)形式的大量数据最兼容的库。然而，一旦我们将处理的数据量增加到相当大的程度，多核 CPU 就无法按照要求高效地处理数据，因为 Numpy 仅运行在并行处理能力有限的 CPU(消费者端大多有 4-8 个内核)上。

这是一个新的不错的 python 库出现的地方`**CuPy**`。CuPy 是一个兼容 GPU 的 NumPy 库。

## 库皮

`CuPy` 是用 NVIDIA CUDA 加速的开源矩阵库。它还使用 cuBLAS、cuDNN、cuRand、cuSolver、cuSPARSE、cuFFT 和 NCCL 等 CUDA 相关库来充分利用 GPU 架构。

它是一个兼容 NumPy 的多维数组在 CUDA 上的实现。CuPy 由`cupy.ndarray`组成，核心多维数组类，上面有很多函数。它支持`numpy.ndarray` 接口的子集。并且还可以通过 GPU 和 CUDA 库加速现有的 NumPy 代码。

#### 硬件和软件设置

*   点
*   蟒蛇 3
*   蟒蛇（可选）
*   CUDA X.0(取决于硬件)
*   CPU:2 个英特尔至强 E5–2698v 4 @ 2.20 GHz
*   主内存:1 TB
*   GPU: NVIDIA Tesla V100 32 GB
*   OS–windows/Linux

**安装**
在你的设备上下载兼容版本的 CUDA 设置并安装。要安装它，请打开终端并输入

```
pip install cupy-cuda(version)
```

其中版本将是您设备上安装的 CUDA 版本。例如-
(对于 CUDA 10.0)

```
pip install cupy-cuda100
```

如果你的设备不支持 CUDA，那么你可以在 Anaconda 安装 CuPy，并将其用于基于 CPU 的计算。或者，Anaconda 也可以很好地使用 CUDA。

**将其安装在蟒蛇身上**–

1.  Open the Anaconda prompt and enter

    ```
    conda install -c anaconda cupy
    ```

    或者

2.  使用 Anaconda 导航器(GUI)直接安装 cupy 库。

**杯状排列基础**

1.  导入–在下面的代码中，cp 是 cupy 的缩写，因为 np 是 numpy，这是惯例。

    ```
    import numpy as np
    import cupy as cp

    ```

2.  Just like Numpy, CuPy also have a `ndarray` class `cupy.ndarray` which is compatible GPU alternative of `numpy.ndarray`.

    ```
    x_gpu = cp.array([1, 2, 3])

    ```

    上例中的`x_gpu`是`cupy.ndarray`的一个实例。你可以看到它的创作与 numpy 的一模一样，只是 NumPy 被 cupy 取代了。

**示例**–以欧几里德范数(也称为 L2 范数)为例。

```
import cupy as cp
import numpy as np

x_cpu = np.array([1, 2, 3])
x_gpu = cp.array([1, 2, 3])

l2_cpu = np.linalg.norm(x_cpu)
l2_gpu = cp.linalg.norm(x_gpu)

print("Using Numpy: ", l2_cpu)
print("\nUsing Cupy: ", l2_gpu)
```

```
Using Numpy: 3.7416573867739413

Using Cupy: array(3.74165739)
```

#### 努比 vs 丘比

CuPy 是一个兼容 GPU 的 NumPy 库。与 numpy 相比，它更高效，因为使用 NVIDIA GPUs 的阵列操作可以比 CPU 计算提供相当大的加速。

**注-** 这里使用的配置是 CPU 为英特尔 i7-7700 HQ，GPU 为 Geforce GTX 1050 4GB 使用 CUDA 9.0。

```
# Python program to 
# demonstrate speed comparison
# between cupy and numpy

# Importing modules
import cupy as cp
import numpy as np
import time

# NumPy and CPU Runtime
s = time.time()
x_cpu = np.ones((1000, 1000, 100))
e = time.time()
print("Time consumed by numpy: ", e - s)

# CuPy and GPU Runtime
s = time.time()
x_gpu = cp.ones((1000, 1000, 100))
e = time.time()
print("\nTime consumed by cupy: "e - s)
```

```
Time consumed by numpy: 0.4238910675048828
Time consumed by cupy: 0.0010099411010742188

```

在这里，我们可以看到 CuPy 可以比 NumPy 工作得更快。

CuPy 在 cupy.ndarray 对象上实现了许多功能。支持的 NumPy API 子集见[参考](https://docs-cupy.chainer.org/en/stable/reference/index.html#cupy-reference)。理解 NumPy 可能有助于利用 CuPy 的大部分功能。因此，建议您阅读 [NumPy 文档](https://docs.scipy.org/doc/numpy/)。

参考资料-https://cupy.chainer.org/