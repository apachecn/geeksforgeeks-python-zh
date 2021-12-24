# 使用 imghdr 确定 Python 中图像的类型

> 原文:[https://www . geesforgeks . org/decision-type-image-python-using-imghdr/](https://www.geeksforgeeks.org/determine-type-image-python-using-imghdr/)

假设给你一个图像类型的文件，你需要确定该文件的类型。简单地说，你需要得到那个图像类型文件的扩展名。这可以在项目中用于验证您请求的图像是否确实是图像，以及它附带了哪个扩展。

img HDR 模块

**使用以下命令进行安装:**

```
npm install imghdr
```

**描述:**
imghdr 模块确定文件或字节流中包含的图像类型。imghdr 模块定义了以下功能:

```
imghdr.what(filename[, h])
```

测试文件名命名的文件中包含的图像数据，并返回描述图像类型的字符串。如果提供了可选的 h，则忽略文件名，并假设 h 包含要测试的字节流。

注意:文件的路径必须正确，名称必须正确。如果图像文件和代码文件在同一个目录中，则不需要指定整个路径。就像我在下一个示例中所做的那样传递文件的名称

模块中可以识别的扩展名有-'rgb '，' gif '，' pbm '，' pgm '，' ppm '，' tiff '，' rast '，' xbm '，' jpeg '，' bmp '，' png '，' webp '，' exr '。在 Python 3.5 中，还添加了扩展“exr”和“webp”。

| 价值 | 图像格式 |
| --- | --- |
| ' rgb ' | 通用图形文件 |
| gif ' | GIF 87a 和 89a 文件 |
| pbm ' | 可移植位图文件 |
| ' pgm ' | 便携式灰度映射文件 |
| ppm ' | 可支持的位图文件 |
| tiff ' | 敌我识别文件 |
| 拉斯特 | 太阳光栅文件 |
| ' xbm ' | x 位图文件 |
| ' jpeg ' | JFIF 或 Exif 格式的 JPEG 数据 |
| bmp ' | BMP 文件 |
| 巴布亚新几内亚 | 便携式网络图形 |
| webp ' | 网络文件 |
| exr ' | OpenEXR 文件 |

**示例:**

```
Input : picture.gif
Output : gif

Input: picture.jpeg
Output : jpeg

```

```
import imghdr
x = imghdr.what("picture.gif") 
#path of image as parameter

print(x)
```

输出:

```
gif

```

这是一个简单的程序，但用于解决现实生活项目中的大问题。

本文由**里沙布·班萨尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。