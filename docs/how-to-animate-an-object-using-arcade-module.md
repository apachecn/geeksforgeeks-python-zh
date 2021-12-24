# 如何使用 Arcade 模块制作物体动画？

> 原文:[https://www . geesforgeks . org/如何使用街机模块制作物体动画/](https://www.geeksforgeeks.org/how-to-animate-an-object-using-arcade-module/)

**先决条件:** [街机图书馆](https://www.geeksforgeeks.org/arcade-library-in-python/)

编程的世界非常广阔，动画是它的关键灵魂。在本教程中，您将学习如何使用街机模块在 Python 中制作对象动画。街机是当今的编程模块，用于开发具有扣人心弦的声音和图形的 2D 游戏。

在开始这篇文章之前，您必须修改您对街机 Python 模块的概念。为了解释动画对象的整个概念，让我们举个例子来完全理解它。大家一定都知道嵌套循环在 C、Python 或 Java 中，并且可能已经使用它创建了很多模式。在这里，我们将借助*街机* Python 库制作一个盒子的动画。

**分步方法:**

**步骤 1)** 导入*街机*库。

## 蟒蛇 3

```py
# Import required module 
import arcade
```

**Step2)** 这里我们将指定一些参数，我们稍后将在程序中使用这些参数来声明屏幕的宽度、高度和标题。

## 蟒蛇 3

```py
# Set up the constants

# Size of the screen
SCREEN_WIDTH = 720
SCREEN_HEIGHT = 480
SCREEN_TITLE = "Bouncing Box"

# Size of the rectangle
RECT_WIDTH = 50
RECT_HEIGHT = 50
```

**步骤 3)** 定义绘制方块街机的函数，draw_rectangle_filled()根据增量向量修改矩形位置。

## 蟒蛇 3

```py
# Explicilt function generate animated bouncing box
def on_draw(delta_time):

    # Start the render.
    arcade.start_render()

    arcade.draw_rectangle_filled(on_draw.center_x, on_draw.center_y,
                                 RECT_WIDTH, RECT_HEIGHT,
                                 arcade.color.GREEN)

    on_draw.center_x += on_draw.delta_x * delta_time
    on_draw.center_y += on_draw.delta_y * delta_time

    # Figure out if we hit the edge and need to reverse.
    if on_draw.center_x < RECT_WIDTH // 2 \
            or on_draw.center_x > SCREEN_WIDTH - RECT_WIDTH // 2:
        on_draw.delta_x *= -1
    if on_draw.center_y < RECT_HEIGHT // 2 \
            or on_draw.center_y > SCREEN_HEIGHT - RECT_HEIGHT // 2:
        on_draw.delta_y *= -1
```

**步骤 4:**-现在，定义函数特定的变量。另外，我们需要给它们初始值。那么这些值将在函数调用之间保持不变。

## 蟒蛇 3

```py
# Set initial positions
on_draw.center_x = 100
on_draw.center_y = 50
on_draw.delta_x = 115
on_draw.delta_y = 130
```

**步骤 5)** 现在，最后一步是定义主功能。在这种情况下，您需要定义背景颜色。

## 蟒蛇 3

```py
# Driver code

# Open up our window
arcade.open_window(SCREEN_WIDTH, SCREEN_HEIGHT, SCREEN_TITLE)
arcade.set_background_color(arcade.color.WHITE)

# Tell the computer to call the draw command at the specified interval.
arcade.schedule(on_draw, 1 / 80)

# Run the program
arcade.run()
```

**以下是上述方法的完整程序:**

## 蟒蛇 3

```py
# Import required module
import arcade

# Set up the constants

# Size of the screen
SCREEN_WIDTH = 720
SCREEN_HEIGHT = 480
SCREEN_TITLE = "Bouncing Box"

# Size of the rectangle
RECT_WIDTH = 50
RECT_HEIGHT = 50

# Explicilt function generate animated bouncing box
def on_draw(delta_time):

    # Start the render.
    arcade.start_render()

    arcade.draw_rectangle_filled(on_draw.center_x, on_draw.center_y,
                                 RECT_WIDTH, RECT_HEIGHT,
                                 arcade.color.GREEN)

    on_draw.center_x += on_draw.delta_x * delta_time
    on_draw.center_y += on_draw.delta_y * delta_time

    # Figure out if we hit the edge and need to reverse.
    if on_draw.center_x < RECT_WIDTH // 2 \
            or on_draw.center_x > SCREEN_WIDTH - RECT_WIDTH // 2:
        on_draw.delta_x *= -1
    if on_draw.center_y < RECT_HEIGHT // 2 \
            or on_draw.center_y > SCREEN_HEIGHT - RECT_HEIGHT // 2:
        on_draw.delta_y *= -1

# Set initial positions
on_draw.center_x = 100
on_draw.center_y = 50
on_draw.delta_x = 115
on_draw.delta_y = 130

# Driver code

# Open up our window
arcade.open_window(SCREEN_WIDTH, SCREEN_HEIGHT, SCREEN_TITLE)
arcade.set_background_color(arcade.color.WHITE)

# Tell the computer to call the draw command at the specified interval.
arcade.schedule(on_draw, 1 / 80)

# Run the program
arcade.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-495737-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201006231620/Bouncing-Box.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201006231620/Bouncing-Box.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201006231620/Bouncing-Box.mp4)</video>