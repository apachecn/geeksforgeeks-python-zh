# 使用 Python 生成验证码

> 原文:[https://www . geeksforgeeks . org/generate-captcha-using-python/](https://www.geeksforgeeks.org/generate-captcha-using-python/)

在这篇文章中，我们将看到如何使用 Python 包验证码生成一个验证码，以图片形式生成我们自己的**验证码**(完全自动化的公共图灵测试来区分计算机和人类)。验证码是一种挑战-响应认证安全机制。验证码阻止自动系统读取图片中扭曲的字符。

### 安装:

```
pip install captcha
```

### **生成图像验证码:**

这里我们将生成一个图像验证码:

#### 逐步实施:

**步骤 1:** 导入模块并创建 **ImageCaptcha()的实例。**

```
image = ImageCaptcha(width = 280, height = 90)
```

**步骤 2:** 用**图像创建图像对象。生成(验证码 _ 文本)。**

```
data = image.generate(captcha_text)  
```

**步骤 3:** 将图像保存到文件 **image.write()。**

```
image.write(captcha_text, 'CAPTCHA.png')
```

**以下是完整实现:**

## 蟒蛇 3

```
# Import the following modules
from captcha.image import ImageCaptcha

# Create an image instance of the given size
image = ImageCaptcha(width = 280, height = 90)

# Image captcha text
captcha_text = 'GeeksforGeeks' 

# generate the image of the given text
data = image.generate(captcha_text) 

# write the image on the given file and save it
image.write(captcha_text, 'CAPTCHA.png')
```

**输出:**

![](img/465e5d710bb8f11a5bbfadad01be0751.png)

**图像验证码**

### 生成音频验证码:

这里我们将生成一个音频验证码:

#### 逐步实施:

**步骤 1:** 导入模块并创建一个**音频验证码的实例()。**

```
image = audioCaptcha(width = 280, height = 90)
```

**步骤 2:** 用**音频创建一个音频对象。**

```
data = audio.generate(captcha_text)  
```

**第三步:**将图像保存到文件**中。**

```
audio.write(captcha_text, audio_file)
```

**以下是完整实现:**

## 蟒蛇 3

```
# Import the following modules
from captcha.audio import AudioCaptcha

# Create an audio instance
audio = AudioCaptcha() 

# Audio captcha text
captcha_text = "5454"

# generate the audio of the given text
audio_data = audio.generate(captcha_text)

# Give the name of the audio file
audio_file = "audio"+captcha_text+'.wav'

# Finally write the audio file and save it
audio.write(captcha_text, audio_file)
```

**输出:**

<video class="wp-video-shortcode" id="video-629767-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210625225334/Audio.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210625225334/Audio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210625225334/Audio.mp4)</video>