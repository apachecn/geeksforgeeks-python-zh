# 电影-在视频中插入文本

> 原文:[https://www . geesforgeks . org/moviepy-在视频中插入文本/](https://www.geeksforgeeks.org/moviepy-inserting-text-in-the-video/)

在本文中，我们将了解如何在 MoviePy 中向视频剪辑插入文本。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。视频剪辑是 MoviePy 中所有其他视频剪辑的基类。为了做到这一点，我们需要安装 ImageMagick，否则它将无法工作。向视频添加文本类似于创建复合视频。

> 为了做到这一点，我们必须做到以下几点:
> 1。导入电影模块
> 2。加载视频文件
> 3。创建一个文本剪辑并设置其位置和持续时间
> 4。使用视频文件和文本剪辑创建复合视频剪辑。
> 5。播放最后一段视频。

下面是实现

```py
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# clipping of the video  
# getting video for only starting 10 seconds 
clip = clip.subclip(0, 10) 

# Reduce the audio volume (volume x 0.8) 
clip = clip.volumex(0.8) 

# Generate a text clip 
txt_clip = TextClip("GeeksforGeeks", fontsize = 75, color = 'black') 

# setting position of text in the center and duration will be 10 seconds 
txt_clip = txt_clip.set_pos('center').set_duration(10) 

# Overlay the text clip on the first video clip 
video = CompositeVideoClip([clip, txt_clip]) 

# showing video 
video.ipython_display(width = 280) 
```

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-469945-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200816232243/1st.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200816232243/1st.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200816232243/1st.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video file clip
clip = VideoFileClip("geeks.mp4") 

# clipping of the video  
# getting video for only starting 10 seconds 
clip = clip.subclip(0, 5) 

# Reduce the audio volume (volume x 0.5) 
clip = clip.volumex(0.5) 

# Generate a text clip 
txt_clip = TextClip("GfG-MoviePy", fontsize = 75, color = 'green') 

# setting position of text in the center and duration will be 5 seconds 
txt_clip = txt_clip.set_pos('bottom').set_duration(5) 

# Overlay the text clip on the first video clip 
video = CompositeVideoClip([clip, txt_clip]) 

# showing video 
video.ipython_display(width = 280) 
```

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-469945-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200816232427/2nd.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200816232427/2nd.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200816232427/2nd.mp4)</video>