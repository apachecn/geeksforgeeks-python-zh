# 电影-预览视频剪辑

> 原文:[https://www . geesforgeks . org/moviepy-preview-a-video-clip/](https://www.geeksforgeeks.org/moviepy-previewing-a-video-clip/)

在本文中，我们将看到如何在 MoviePy 中预览视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。clip.show 和 clip.preview 方法使您能够在 Pygame 窗口中将剪辑可视化。它们是最快的预览方式，因为剪辑是同时生成和显示的，它们对于获取像素的坐标或颜色非常有用。这些方法需要安装 PyGame，并使用 moviepy.editor 模块。

> 为此，我们将对视频文件剪辑对象使用`preview`方法
> 
> **语法:**剪辑.预览(fps)
> 
> **参数:**以 fps 为可选参数
> 
> **返回:**返回无

如果我们在正在预览的视频剪辑的帧中单击某处，它将打印所单击像素的位置和颜色。按退出中止预览。

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# previewing the clip at fps = 20
clip.preview(fps = 20)
```

**输出:**

<video class="wp-video-shortcode" id="video-462414-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730185555/135.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200730185555/135.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730185555/135.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# previewing the clip at fps = 20
clip.preview(fps = 20)
```

**输出:**

<video class="wp-video-shortcode" id="video-462414-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730185608/229.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200730185608/229.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730185608/229.mp4)</video>