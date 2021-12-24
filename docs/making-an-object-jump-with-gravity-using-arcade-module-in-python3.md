# 使用 Python3 中的街机模块利用重力使物体跳跃

> 原文:[https://www . geeksforgeeks . org/利用重力制造物体-跳跃-使用街机-模块-in-python3/](https://www.geeksforgeeks.org/making-an-object-jump-with-gravity-using-arcade-module-in-python3/)

[街机库](https://www.geeksforgeeks.org/arcade-library-in-python/)是一个现代 Python 模块，广泛用于开发具有引人注目的图形和声音的 2D 视频游戏。街机是一个面向对象的库。它可以像任何其他 Python 包一样安装。现在，这取决于开发人员的需要，他/她想使用这个工具包使用什么类型的游戏、图形和声音。因此，在这篇文章中，我们将学习如何使用 Python 中的 Arcade 库使一个对象在重力作用下跳跃。为了理解这个概念，让我们举一个结实的球的例子。

以下是步骤:

**第一步:**导入街机模块。

```
import arcade
```

**步骤 2:** 定义输出屏幕的参数。

```
# Size of the screen
WIDTH = 600
HEIGHT = 600
TITLE = "Robust Ball "
```

**第三步:**定义球的半径。

```
# Size of the ball.
BALL_RADIUS = 50
```

**第四步:**定义引力常数的值。

```
#  gravity 
GRAVITATIONAL_CONSTANT = 0.3
```

**第五步:**定义球的弹跳速度。

```
# Percent of velocity maintained on a bounce.
BOUNCE = 0.9
```

**第六步:**定义一个使用 arcade.draw_circle_filled()绘制球的函数。

## 蟒 3

```
def draw(_delta_time):

    # Start the render.
    arcade.start_render()

    # Draw ball
    arcade.draw_circle_filled(draw.x, draw.y, BALL_RADIUS,
                              arcade.color.RED)

    draw.x += draw.delta_x
    draw.y += draw.delta_y
    draw.delta_y -= GRAVITATIONAL_CONSTANT
```

**第七步:**定义一个函数，计算出我们是击中了左边还是右边，这样我们就可以反转了。

## 蟒 3

```
# Figure out if we hit the left or 
# right edge and need to reverse.
if draw.x < BALL_RADIUS and draw.delta_x < 0:
     draw.delta_x *= -BOUNCE
  elif draw.x > WIDTH - BALL_RADIUS and draw.delta_x > 0:
    draw.delta_x *= -BOUNCE
```