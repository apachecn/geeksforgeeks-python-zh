# 使用 Python 中的 Arcade Library 绘制一张开心的脸

> 原文:[https://www . geesforgeks . org/draw-a-happy-face-use-arcade-library-in-python/](https://www.geeksforgeeks.org/draw-a-happy-face-using-arcade-library-in-python/)

街机是一个用于开发 2D 游戏的 Python 模块。要画一张快乐的脸，步骤如下:

*   导入街机库。

```
import arcade
```

*   打开窗户。

```
arcade.open_window(SCREEN_WIDTH, SCREEN_HEIGHT, SCREEN_TITLE)
```

街机使用的功能是 open_window。该命令打开一个给定大小的窗口，即宽度和高度以及屏幕标题。

*   指定使用 open_window 定义的参数值。

```
SCREEN_WIDTH = 600
SCREEN_HEIGHT = 600
SCREEN_TITLE = "Happy Face GfG "
```

*   选择输出背景屏幕的颜色。

```
arcade.set_background_color(arcade.color.BLACK)
```

*   这个命令会告诉街机库你开始画画了。

```
arcade.start_render()
```

*   编写一个函数，使用内置函数 draw_circle_filled()函数为面的底部绘制圆。

```
x = 300
y = 300
radius = 200
arcade.draw_circle_filled(x, y, radius, arcade.color.YELLOW)
```

*   同样，使用 draw_circle_filled()函数编写用于绘制脸部右眼和左眼的函数。

```
# Draw the right eye
x = 370
y = 350
radius = 20
arcade.draw_circle_filled(x, y, radius, arcade.color.BLACK)
# Draw the left eye
x = 230
y = 350
radius = 20
arcade.draw_circle_filled(x, y, radius, arcade.color.BLACK)
```

*   对于幸福的脸来说，微笑是最重要的部分。使用 draw_arc_outline()函数绘制微笑。

```
# Draw the smile
x = 300
y = 280
width = 120
height = 100
start_angle = 190
end_angle = 350
arcade.draw_arc_outline(x, y, width, height,
                       arcade.color.BLACK, 
                       start_angle, end_angle, 10)
```

*   这个命令会告诉街机库你已经画好了。

```
# Finish drawing
arcade.finish_render()
```

*   这个命令是保持窗户打开。

```
# Keep the window open until the user
# hits the 'close' button
arcade.run()
```

**完整源代码:**

## 蟒蛇 3

```
import arcade

# specify the parameters
SCREEN_WIDTH = 600
SCREEN_HEIGHT = 600
SCREEN_TITLE = "Happy Face GfG "

# Open the window. Set the window title and dimensions
arcade.open_window(SCREEN_WIDTH, SCREEN_HEIGHT, SCREEN_TITLE)

# Set the background color
arcade.set_background_color(arcade.color.BLACK)

# start render process
arcade.start_render()

# Draw the face
x = 300
y = 300
radius = 200
arcade.draw_circle_filled(x, y, radius, arcade.color.YELLOW)

# Draw the right eye
x = 370
y = 350
radius = 20
arcade.draw_circle_filled(x, y, radius, arcade.color.BLACK)

# Draw the left eye
x = 230
y = 350
radius = 20
arcade.draw_circle_filled(x, y, radius, arcade.color.BLACK)

# Draw the smile
x = 300
y = 280
width = 120
height = 100
start_angle = 190
end_angle = 350
arcade.draw_arc_outline(x, y, width, height, arcade.color.BLACK,
                        start_angle, end_angle, 10)

# Finish drawing
arcade.finish_render()

# Keep the window open until the user hits 
# the 'close' button
arcade.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-492752-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200926225402/Happy-Face.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200926225402/Happy-Face.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200926225402/Happy-Face.mp4)</video>