# 如何在 Python3 中使用街机在屏幕上显示计时器？

> 原文:[https://www . geeksforgeeks . org/如何使用街机游戏在屏幕上显示计时器 3/](https://www.geeksforgeeks.org/how-to-show-a-timer-on-screen-using-arcade-in-python3/)

**先决条件:** [街机库](https://www.geeksforgeeks.org/arcade-library-in-python/)

街机是一个现代的框架，用来制作 2D 的电子游戏。在这篇文章中，您将学习如何使用 Python 的街机模块显示屏幕计时器。在屏幕上显示计时器并不困难，只需遵循以下步骤:-

**第一步:**首先导入 Python 的街机模块

## 蟒蛇 3

```
import arcade
```

**步骤 2:** 定义输出屏幕所需的参数。

## 蟒蛇 3

```
WIDTH = 800
HEIGHT = 600
TITLE = "Timer"
```

**第三步:**定义一个类 MYTimer，在该类下设置背景色和开始时间。

## 蟒蛇 3

```
class MyTimer(arcade.Window):

    def setup(self):
        arcade.set_background_color(arcade.color.WHITE)
        self.total_time = 0.0
```

**第 4 步:**在 MyTimer 类下，定义一个函数来计算分和秒。

## 蟒蛇 3

```
def on_draw(self):

    # Start the render.
    arcade.start_render()

    # Calculate minutes
    minutes = int(self.total_time) // 60

    # Calculate seconds by using a modulus
    seconds = int(self.total_time) % 60

    # Figure out your output
    output = f"Time: {minutes:02d}:{seconds:02d}"

    # Output the timer text.
    arcade.draw_text(output, 300, 300, arcade.color.BOTTLE_GREEN, 45)
```

**第 5 步:**现在，定义一个 on_update 函数，随着分钟和秒钟的增加来更新时间。

## 蟒蛇 3

```
def on_update(self, delta_time):
    self.total_time += delta_time
```

**第六步:**最后也是最重要的一步是定义 main()并在最后调用它。

## 蟒蛇 3

```
def main():
    window = MyTimer()
    window.setup()
    arcade.run()

main()
```

**完整代码**

## 蟒蛇 3

```
#import module
import arcade

# screen parameters
SCREEN_WIDTH = 800
SCREEN_HEIGHT = 600
SCREEN_TITLE = "Timer "

# define class

class MyTimer(arcade.Window):

    def setup(self):
        arcade.set_background_color(arcade.color.WHITE)
        self.total_time = 0.0

    def on_draw(self):

        # Start the render.
        arcade.start_render()

        # Calculate minutes
        minutes = int(self.total_time) // 60

        # Calculate seconds by using a modulus
        seconds = int(self.total_time) % 60

        # Figure out your output
        output = f"Time: {minutes:02d}:{seconds:02d}"

        # Output the timer text.
        arcade.draw_text(output, 300, 300, arcade.color.BOTTLE_GREEN, 45)

    # update
    def on_update(self, delta_time):
        self.total_time += delta_time

# main function
def main():
    window = MyTimer()
    window.setup()
    arcade.run()

# call main function
main()
```

**输出:**

<video class="wp-video-shortcode" id="video-497442-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201011133204/TIMEER.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201011133204/TIMEER.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201011133204/TIMEER.mp4)</video>