# 用 Python 检测热词

> 原文:[https://www . geesforgeks . org/hotword-detection-with-python/](https://www.geeksforgeeks.org/hotword-detection-with-python/)

我们大多数人都听说过 Alexa、Ok google 或 hey Siri，可能都想过用自己最喜欢的名字创建自己的虚拟个人助理，比如: ***嘿，灭霸！*** 。所以这里有一个最简单的方法可以做到不弄脏你的手。
**要求:**

1.  带工作麦克风的 Linux 电脑(我在 Arch Linux 上测试过)。
2.  用你的包管理器安装 python3、pyaudio、sox(也适用于 Arch Linux)。:

```
sudo apt-get update
sudo apt-get install python3 python3-pip
sudo apt-get install python-pyaudio python3-pyaudio sox
```

1.  从[这里](http://ftp5.gwdg.de/pub/linux/archlinux/community/os/x86_64//python-snowboy-1.3.0-1-x86_64.pkg.tar.xz)领取雪球包裹。该文件适用于所有基于 Linux 的操作系统。
    雪球也支持树莓 Pi 的所有版本(1、2、3 和零)。支持的操作系统是 Raspbian 8.0。
2.  当你用一个名为 usr 的文件夹解压时。现在导航到 usr/lib/python 3.7/site-packages。
3.  使用文件管理器或 cp -r 命令将两个文件夹(snow oy 和 snow oy-1 . 2 . 0 B1-py 3.7 . egg-info)复制到/usr/lib/python 3 . 7/site-packages。

```
cd Downloads
tar -xf python-snowboy-1.3.0-1-x86_64.pkg.tar.xz
cd usr/lib/python3.7/site-packages
sudo cp -r snowboy /usr/lib/python3.7/site-packages
sudo cp -r snowboy-1.2.0b1-py3.7.egg-info
```

现在你可以检查雪球是否工作了。启动你的终端，输入 python 获取 Python 外壳。

## 蟒蛇 3

```
from snowboy import snowboydecode
```