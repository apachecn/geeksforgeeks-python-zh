# Pafy–获取流的 https 网址

> 原文:[https://www . geesforgeks . org/pafy-get-https-URL-of-stream/](https://www.geeksforgeeks.org/pafy-getting-https-url-of-stream/)

在本文中，我们将看到如何在 pafy 中获得给定 youtube 视频流的安全 url。Pafy 是一个 python 库，用于下载 YouTube 内容和检索元数据。Pafy 对象是包含给定视频所有信息的对象。流基本上是可用的分辨率的视频是可以在 youtube 上获得的。网址代表统一资源定位符，用于指定万维网上的地址。网址是连接到网络的任何资源(例如，超文本页面、图像和声音文件)的基本网络标识。该协议规定了如何传输来自链路的信息。Https 是安全的 url。

借助`new`方法，我们可以得到 pafy 对象，借助`allstreams`属性，我们可以得到视频可用的所有流，下面是获取给定视频的 pafy 对象的命令

```py
video = pafy.new(url)
streams = video.allstreams

```

视频网址应该存在于 youtube 上，因为它获得了那些在 youtube 上出现的视频的信息。YouTube 是一个美国在线视频分享平台。

为此，我们对视频的 pafy 流对象使用`url_https`属性

> **语法:** stream.url_https
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

下面是实现

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = vG2PNdI8axo"

# getting video
video = pafy.new(url) 

# getting all the available streams
streams = video.allstreams

# selecting one stream
stream = streams[1]

# getting https url of stream
value = stream.url_https

# printing the value
print("URL Htttps : " + str(value))
```

**输出:**

```py
URL Htttps : https://r7---sn-ci5gup-pmj6.googlevideo.com/videoplayback?expire=1594861438&ei=HlMPX-nrNayuz7sP_bGqkAo&ip=171.61.220.239&id=o-AJfFxmBn3FJ12CzPKBH36Nm9uavpac34Biht02INP8B9&itag=250&source=youtube&requiressl=yes&mh=rM&mm=31%2C29&mn=sn-ci5gup-pmj6%2Csn-ci5gup-qxae7&ms=au%2Crdu&mv=m&mvi=7&pl=19&initcwndbps=491250&vprv=1&mime=audio%2Fwebm&gir=yes&clen=554085&dur=65.521&lmt=1590825392886674&mt=1594839691&fvip=7&keepalive=yes&c=WEB&txp=5431432&sparams=expire%2Cei%2Cip%2Cid%2Citag%2Csource%2Crequiressl%2Cvprv%2Cmime%2Cgir%2Cclen%2Cdur%2Clmt&sig=AOq0QJ8wRgIhANgTWTY-4ju_s8pnFzJy4gWHZ6QFUuG0jxpiNNzAB3j6AiEA5aykKDegON8rNiRVL6Frr4if8YmYiD5n-9eY0iaovDA%3D&lsparams=mh%2Cmm%2Cmn%2Cms%2Cmv%2Cmvi%2Cpl%2Cinitcwndbps&lsig=AG3C_xAwRgIhAJH2KIEr4_SwK2k4TmhZiqJgHSHbpognkeTApr8jk3xFAiEAwuH5fERHVoT5bTCC7faXjxRXECMBf3umqpwEMCUdrbs%3D&ratebypass=yes

```

另一个例子

```py
# importing pafy
import pafy 

# url of video 
url = "https://www.youtube.com / watch?v = i6rhnSoK_gc"

# getting video
video = pafy.new(url) 

# getting all the available streams
streams = video.allstreams

# selecting one stream
stream = streams[4]

# getting https url of stream
value = stream.url_https

# printing the value
print("URL Htttps : " + str(value))
```

**输出:**

```py
URL Htttps : https://r3---sn-ci5gup-pmjk.googlevideo.com/videoplayback?expire=1594861433&ei=GVMPX9yKBs-uwgPV2LHICA&ip=171.61.220.239&id=o-AMJ8u2W9CWH0eQFEr34g3qSXbDvUh5UJp_qaEwhdv4PH&itag=278&aitags=133%2C134%2C135%2C136%2C137%2C160%2C242%2C243%2C244%2C247%2C248%2C278&source=youtube&requiressl=yes&mh=x9&mm=31%2C29&mn=sn-ci5gup-pmjk%2Csn-ci5gup-qxae7&ms=au%2Crdu&mv=m&mvi=3&pcm2cms=yes&pl=19&initcwndbps=585000&vprv=1&mime=video%2Fwebm&gir=yes&clen=8125774&dur=701.933&lmt=1594573565579581&mt=1594839691&fvip=3&keepalive=yes&c=WEB&txp=5535432&sparams=expire%2Cei%2Cip%2Cid%2Caitags%2Csource%2Crequiressl%2Cvprv%2Cmime%2Cgir%2Cclen%2Cdur%2Clmt&sig=AOq0QJ8wRgIhAP6QlYxQyQnl7Z34mTkbO5PrMgpy-JhTRU_2z8kVtyxQAiEAxE2yYZYMTNGdMsTqyp_JX4P1ruo-Ceubi0zGYKisaqE%3D&lsparams=mh%2Cmm%2Cmn%2Cms%2Cmv%2Cmvi%2Cpcm2cms%2Cpl%2Cinitcwndbps&lsig=AG3C_xAwRgIhAIY99OO_F3qWdoBbuKkVmK-j4moo6A_o6ToHV_0SjMe3AiEAm7w-BZIe_BPosyMCfyCINJLViYEKQwyPlW_L8UXchkU%3D&ratebypass=yes

```