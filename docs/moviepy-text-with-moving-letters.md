# 移动-带移动字母的文本

> 原文:[https://www . geesforgeks . org/moviepy-带移动字母的文本/](https://www.geeksforgeeks.org/moviepy-text-with-moving-letters/)

在本文中，我们将看到如何移动文本剪辑的字母。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。视频剪辑是 MoviePy 中所有其他视频剪辑的基类。带有移动字母的文字，就像字母在自我扩散和重新排列，创造出一种移动的效果。

> 为了做到这一点，我们必须做到以下几点:
> 1。导入 numpy 和 moviepy 模块
> 2。创建一个文本剪辑并设置其各种属性
> 3。从文本剪辑创建一个复合视频剪辑
> 4。创建移动字母效果的方法
> 5。使用这些方法逐个创建剪辑
> 6。组合剪辑以获得最终视频剪辑
> 7。将 fps 设置为最终剪辑
> 8。显示最终剪辑

**示例:**下面是实现

## 蟒蛇 3

```py
# importing Numpy
import numpy as np

# importing moviepy module
from moviepy.editor import * from moviepy.video.tools.segmenting import findObjects

# screen size
screensize = (720, 460)

# creating a text clip of color green, font is Arial and size is 80
txtClip = TextClip('GeeksforGeeks', color = 'lightgreen', font = "Arial",
                   kerning = 5, fontsize = 80)

# creating a composite video of given size
cvc = CompositeVideoClip( [txtClip.set_pos('center')],
                        size = screensize)

# helper function
rotMatrix = lambda a: np.array( [[np.cos(a), np.sin(a)],
                                 [-np.sin(a), np.cos(a)]] )

# creating a effect 1 method
def effect1(screenpos, i, nletters):

    # damping
    d = lambda t : 1.0/(0.3 + t**8)
    # angle of the movement
    a = i * np.pi / nletters

    # using helper function
    v = rotMatrix(a).dot([-1, 0])

    if i % 2 : v[1] = -v[1]

    # returning the function
    return lambda t: screenpos + 400 * d(t)*rotMatrix(0.5 * d(t)*a).dot(v)

# method for effect 2
def effect2(screenpos, i, nletters):

    # numpy array
    v = np.array([0, -1])

    d = lambda t : 1 if t<0 else abs(np.sinc(t)/(1 + t**4))

    # returning the function
    return lambda t: screenpos + v * 400 * d(t-0.15 * i)

# a list of ImageClips
letters = findObjects(cvc)

# method to move letters
def moveLetters(letters, funcpos):

    return [ letter.set_pos(funcpos(letter.screenpos, i, len(letters)))
              for i, letter in enumerate(letters)]

# adding clips with specific effect
clips = [ CompositeVideoClip( moveLetters(letters, funcpos),
                              size = screensize).subclip(0, 5)
          for funcpos in [effect1, effect2] ]

# comping all the clips
final_clip = concatenate_videoclips(clips)

# setting fps of the final clip
final_clip.fps = 24

# showing video clip
final_clip.ipython_display()
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-469947-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200817001858/1st1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200817001858/1st1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200817001858/1st1.mp4)</video>

另一个例子

## 蟒蛇 3

```py
# importing Numpy
import numpy as np

# importing moviepy module
from moviepy.editor import * from moviepy.video.tools.segmenting import findObjects

# screen size
screensize = (1080, 720)

# creating a text clip of color red, font is Arial and size is 80
txtClip = TextClip('GeeksforGeeks', color = 'red', font = "Arial",
                   kerning = 5, fontsize = 80)

# creating a composite video of given size
cvc = CompositeVideoClip( [txtClip.set_pos('center')],
                        size = screensize)

# helper function
rotMatrix = lambda a: np.array( [[np.cos(a), np.sin(a)],
                                 [-np.sin(a), np.cos(a)]] )

# method for effect 3
def effect3(screenpos, i, nletters):

    v = np.array([-1, 0])

    d = lambda t : max(0, 3-3 * t)

    # returning the function
    return lambda t: screenpos-400 * v*d(t-0.2 * i)

# method for effect 4
def effect4(screenpos, i, nletters):

    # damping
    d = lambda t : max(0, t)

     # angle of the movement
    a = i * np.pi / nletters

    v = rotMatrix(a).dot([-1, 0])

    if i % 2 : v[1] = -v[1]

    # returning the function
    return lambda t: screenpos + 400 * d(t-0.1 * i)*rotMatrix(-0.2 * d(t)*a).dot(v)

# a list of ImageClips
letters = findObjects(cvc)

# method to move letters
def moveLetters(letters, funcpos):

    return [ letter.set_pos(funcpos(letter.screenpos, i, len(letters)))
              for i, letter in enumerate(letters)]

# adding clips with specific effect
clips = [ CompositeVideoClip( moveLetters(letters, funcpos),
                              size = screensize).subclip(0, 5)
          for funcpos in [effect3, effect4] ]

# comping all the clips
final_clip = concatenate_videoclips(clips)

# setting fps of the final clip
final_clip.fps = 24

# showing video clip
final_clip.ipython_display()
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-469947-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200817002316/2nd1.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200817002316/2nd1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200817002316/2nd1.mp4)</video>