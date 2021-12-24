# 如何初始化 PyGame 中所有导入的模块？

> 原文:[https://www . geesforgeks . org/如何初始化 pygame 中所有导入的模块/](https://www.geeksforgeeks.org/how-to-initialize-all-the-imported-modules-in-pygame/)

[**PyGame**](https://www.geeksforgeeks.org/introduction-to-pygame/) 是专为游戏开发设计的 Python 库。PyGame 是建立在 **SDL** 库之上的，所以它提供了用 Python 开发游戏的全部功能。Pygame 有许多模块来执行它的操作，在使用这些模块之前，它们必须被初始化。所有模块可以单独初始化，也可以一次初始化一个。这篇文章描述了如何一次初始化所有导入的模块。

**使用的方法:**

*   **pygame . init()**–初始化所有模块。它不接受任何参数，并返回一个 tuble (numpass，numfail)，指示成功初始化的模块数和失败的模块数。

*   **pygame . get _ init()**–此方法用于检查 pygame 模块是否初始化。

**示例 1:** 本示例初始化所有 pygame 模块，并打印成功初始化的模块数量。

## 蟒蛇 3

```py
# importing the library
import pygame

# initializing all the imported
# pygame modules
(numpass,numfail) = pygame.init()

# printing the number of modules
# initialized successfully
print('Number of modules initialized successfully:',
      numpass)
```

**输出:**

```py
Number of modules initialized successfully: 6
```

**例 2:** 本例使用 pygame.get_init()函数检查 pygame 模块是否初始化。

## 蟒蛇 3

```py
# importing the library
import pygame

# initializing the modules
pygame.init()

# checking the initialization
is_initialized = pygame.get_init()

# printing the result
print('Is pygame modules initialized:',
      is_initialized)
```

**输出:**

```py
Is pygame modules initialized: True
```