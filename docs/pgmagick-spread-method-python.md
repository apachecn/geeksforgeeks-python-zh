# Pmagick spread()方法–Python

> 原文:[https://www . geesforgeks . org/pgmagick-spread-method-python/](https://www.geeksforgeeks.org/pgmagick-spread-method-python/)

**spread()** 函数是 Pgmagick 库中的一个内置函数，用于随机替换图像像素。该函数在成功时返回真值。

> **语法:**
> 
> ```
> spread(thresholdLevel)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，如下所述:
> 
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。
> 
> **输入图像:**
> ![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)
> 
> **例 1:**
> 
> ```
> from pgmagick import Image, DrawableCircle, DrawableText
> from pgmagick import Geometry, Color
>   
> # draw the image of dimension 600 * 600
> img = Image('input.png')
>   
> # invoke spread function with factor as 5
> img.spread(5)
>   
> # invoke write function along with filename
> img.write('2_a.png')
> ```
> 
> **输出:**
> ![](img/5dc17873e97595da4acd5454304f6dd1.png)
> **例 2:**
> 
> ```
> # import library
> from pgmagick import Image, DrawableCircle, DrawableText
> from pgmagick import Geometry, Color
>   
> # Draw image of dimension 600 * 600 having background green
> im = Image(Geometry(600, 600), Color("# 32CD32"))
>   
> # invoke DrawableCircle() function
> circle = DrawableCircle(100, 100, 300, 20)
>   
> # invoke draw() function
> im.draw(circle)
>   
> # set font size to 40px
> im.fontPointsize(40)
>   
> # invoke DrawableText() function
> text = DrawableText(250, 450, "GeeksForGeeks")
>   
> # invoke draw() function
> im.draw(text)
>   
> # invoke spread function with factor as 4
> im.spread(4)
>   
> # invoke write function along with filename
> im.write('1_b.png')
> ```
> 
> **输出:**
> ![](img/51eb89e71e355554672df9c2d461bb87.png)