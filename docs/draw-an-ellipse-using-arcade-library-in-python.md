# 使用 Python 中的 Arcade 库绘制椭圆

> 原文:[https://www . geesforgeks . org/绘制椭圆-使用-街机-python 中的库/](https://www.geeksforgeeks.org/draw-an-ellipse-using-arcade-library-in-python/)

**先决条件:** [街机图书馆](https://www.geeksforgeeks.org/arcade-library-in-python/)

*街机*库是一个现代 Python 模块，用于开发具有迷人图形和声音的 2D 视频游戏。这是一个面向对象的库。它可以像集成开发环境中的任何其他 Python 包一样安装。

*街机*模块有两个内置的椭圆绘制功能，即 *街机. drawing 椭圆 _ 轮廓()*和  街机. drawing 椭圆 _ 填充() 。这是*街机*模块中的一个加分点，不然你一定注意到了，在*龟*这样的 Python 模块中，你需要创建一个函数来绘制任何原始设计。

![](img/8973513a46134e9d029dec5bd3624c20.png)

**1)arcade . draw _ ellipse _ outline():**此方法用于绘制椭圆的轮廓。

> **语法:**arcade . draw _ ellipse _ outline(center _ x，centre _ y，宽度，高度，颜色，边框 _ 宽度，倾斜 _ 角度，num_segments)
> 
> **1。centre_x:** 作为椭圆中心的 x 位置。
> T3】2。中心 y: 椭圆中心的 y 位置。
> **3。宽度:**椭圆的宽度。
> **4。高度:**椭圆的高度。
> **5。颜色:**用于定义借助 arcade.color 功能制作椭圆轮廓的颜色。
> **6。border_width:** 椭圆轮廓的宽度，以像素为单位。
> **7。tilt_angle:** 倾斜椭圆的角度，单位为度。
> T21【8】。num_segments: 组成此椭圆的三角形线段数。默认值为-1，这显然意味着 arcade 将根据椭圆的大小计算线段的数量。

**上述方法的实施:**

## 蟒蛇 3

```
# Import required modules
import arcade

# Specify Parameters
SCREEN_WIDTH = 600
SCREEN_HEIGHT = 800
SCREEN_TITLE = "Welcome to GeeksForGeeks "

# Open the window
arcade.open_window(SCREEN_WIDTH, SCREEN_HEIGHT, SCREEN_TITLE)

# Set the background color
arcade.set_background_color(arcade.color.BABY_BLUE)

# Start drawing
arcade.start_render()

# Draw ellipse
arcade.draw_ellipse_outline(
    400, 363, 250, 130, arcade.color.AMBER, 10, 180, -1)

# Finish drawing
arcade.finish_render()

# Display everything
arcade.run()
```

**输出:**

![](img/48bc527e04d19b3c37f7cf4884a87b75.png)

**2)****arcade . draw _ ellipse _ filled():**此方法用于绘制填充椭圆。

> **语法:**arcade . draw _ ellipse _ filled(center _ x，centre _ y，宽度，高度，颜色，倾斜角，线段数)
> 
> **1。centre_x:** 作为椭圆中心的 x 位置。
> T3】2。中心 y: 椭圆中心的 y 位置。
> **3。宽度:**椭圆的宽度。
> **4。高度:**椭圆的高度。
> **5。颜色:**用于定义借助 arcade.color 功能制作椭圆轮廓的颜色。
> **6。border_width:** 椭圆轮廓的宽度，以像素为单位。
> **7。tilt_angle:** 倾斜椭圆的角度，单位为度。
> T21【8】。num_segments: 组成此椭圆的三角形线段数。默认值为-1，这显然意味着 arcade 将根据椭圆的大小计算线段的数量。

除了*边框宽度*外，其他参数均与*arcade . draw _ ellipse _ outline()*相同。在*街机中，我们不需要边框宽度。*

**上述方法的实施:**

## 蟒蛇 3

```
# Import required modules
import arcade

# Specify Parameters
SCREEN_WIDTH = 600
SCREEN_HEIGHT = 800
SCREEN_TITLE = "Welcome to GeeksForGeeks "

# Open the window
arcade.open_window(SCREEN_WIDTH, SCREEN_HEIGHT, SCREEN_TITLE)

# Set the background color
arcade.set_background_color(arcade.color.BABY_BLUE)

# start drawing
arcade.start_render()

# Draw ellipse
arcade.draw_ellipse_filled(400, 363, 250, 130, arcade.color.AMBER, 180, -1)

# Finish drawing
arcade.finish_render()

# Display everything
arcade.run()
```

**输出:**

![](img/2e1c2fcf115a37db485834cba10e3f64.png)