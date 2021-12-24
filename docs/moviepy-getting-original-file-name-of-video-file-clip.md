# 影片–获取视频文件剪辑的原始文件名

> 原文:[https://www . geesforgeks . org/moviepy-get-original-file-name-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-getting-original-file-name-of-video-file-clip/)

在本文中，我们将看到如何在 MoviePy 中获取视频文件的原始文件名。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。原始文件名是最初存在的原始视频的名称，即加载的视频，即使在更改和编辑视频后，我们也可以获得文件的原始名称。

借助下面给出的命令，我们可以加载视频文件剪辑

```
clip = VideoFileClip(file_name)
```

> 为了做到这一点，我们将使用视频文件剪辑对象的`filename`属性
> 
> **语法:**剪辑.文件名
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.webm")

# getting subclip from it
clip1 = clip.subclip(0, 10)

# resizing the clip1
clip1 = clip1.resize(0.5)

# rotating the clip1
clip1 = clip1.rotate(180)

# getting original file name of the clip
name = clip1.filename

# printing the name
print("File Name  : " + name)

print("---------------------------------------")

# showing final clip
clip1.ipython_display()
```

**输出:**

```
File Name  : dsa_geek.webm
---------------------------------------
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457241-1" width="427" height="240" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722010753/118.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722010753/118.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722010753/118.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip1 = clip.subclip(0, 7)

# getting original file name of the clip
name = clip1.filename

# printing the name
print("File Name  : " + name)

print("---------------------------------------")

# showing final clip
clip1.ipython_display()
```

**输出:**

```
File Name  : geeks.mp4
---------------------------------------
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457241-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722010826/211.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722010826/211.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722010826/211.mp4)</video>