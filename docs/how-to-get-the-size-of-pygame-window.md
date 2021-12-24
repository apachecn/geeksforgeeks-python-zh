# 如何获取 PyGame 窗口的大小？

> 原文:[https://www . geeksforgeeks . org/如何获得 pygame 大小的窗口/](https://www.geeksforgeeks.org/how-to-get-the-size-of-pygame-window/)

在本文中，我们将学习如何获得一个 [PyGame](https://www.geeksforgeeks.org/introduction-to-pygame/) 窗口的大小。

游戏编程现在非常有价值，它也可以用于广告和作为教学工具。游戏开发包括数学、逻辑、物理、人工智能等等，非常有趣。在 python 中，游戏编程是在 *pygame* 中完成的，它是这样做的最佳模块之一。

**安装:**

可以使用以下命令安装该库:

```py
pip install pygame 
```

**分步方法:**

1.  进口〔t0〕pygame。
2.  初始化〔t0〕pygame。
3.  使用*pygame . display . set _ mode()*方法形成屏幕。
4.  使用 *screen.get_size()* 方法获取成型屏幕的尺寸。
5.  退出 *pygame。*

以下是基于上述方法的一些示例:

**例 1:**

## 蟒蛇 3

```py
# import package pygame
import pygame

# initialize pygame
pygame.init()

# Form screen
screen = pygame.display.set_mode()

# get the default size
x, y = screen.get_size()

# quit pygame
pygame.display.quit()

# view size (width x height)
print(x, y)
```

**输出:**

```py
1536 864
```

**例 2:**

## 蟒蛇 3

```py
# import package pygame
import pygame

# initialize pygame
pygame.init()

# Form screen
screen = pygame.display.set_mode((500, 500))

# get the size
x, y = screen.get_size()

# quit pygame
pygame.display.quit()

# view size (width x height)
print(x, y)
```

**输出:**

```py
500 500
```