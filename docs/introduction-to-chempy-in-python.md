# Python 中的 Chempy 简介

> 原文:[https://www . geesforgeks . org/introduction-to-chempy-in-python/](https://www.geeksforgeeks.org/introduction-to-chempy-in-python/)

**ChemPy** 是一个 python 包，主要用于解决分析、物理和无机化学方面的问题。这是一个免费的开源 Python 工具包，用于化学、化学工程和材料科学应用。

ChemPy 包括用于表示物质、反应和反应系统的类。它还包括来自物理化学的成熟公式，以及化学动力学中常见的一些微分方程的解析解。

它的目标受众主要是需要执行建模工作的研究人员和工程师。但是由于例如微分方程系统和非线性方程组的中间表示是象征性可用的，ChemPy 也可以用于教育环境。

**安装:**可以通过在命令提示符/终端中运行以下脚本来安装 ChemPy:

```py
pip install chempy
```

以下是应用 ChemPy 模块的一些示例:
**示例 1 :** 打印元素列表及其质量。

## 蟒蛇 3

```py
# importing the module
from chempy.util import periodic

# number of elements to be fetched
n = 10

# displaying the information
print("Atomic No.\tName\t\tSymbol\t\tMass")

# fetching the information for
# the first 10 elements
for i in range(1, n + 1):

    # displaying the atomic number
    print(i, end = "\t\t")

    # displaying the name
    if len(periodic.names[i]) > 7:
        print(periodic.names[i], end = "\t")
    else:
        print(periodic.names[i], end = "\t\t")

    # displaying the symbol
    print(periodic.symbols[i], end = "\t\t")

    # displaying the mass
    print(periodic.relative_atomic_masses[i])
```

**输出:**

```py
Atomic No.    Name        Symbol        Mass
1        Helium        He        4.002602
2        Lithium        Li        6.94
3        Beryllium    Be        9.0121831
4        Boron        B        10.81
5        Carbon        C        12.011
6        Nitrogen    N        14.007
7        Oxygen        O        15.999
8        Fluorine    F        18.998403163
9        Neon        Ne        20.1797
10        Sodium        Na        22.98976928
```

**例 2 :** 我们来看看如何在 ChemPy 中表示化学反应。考虑水的形成。在反应中，两个 H2 分子与一个 O2 分子结合形成两个 H2 分子。在 ChemPy 中，将使用 chempy.chemistry 模块的 reaction()函数创建反应。

## 蟒蛇 3

```py
# importing the module
from chempy import chemistry

# creating the reaction
reaction = chemistry.Reaction({'H2': 2, 'O2': 1},
                              {'H2O': 2})

# displaying the reaction
print(reaction)

# displaying the reaction order
print(reaction.order())
```

**输出:**

```py
2 H2 + O2 -> 2 H2O
3
```