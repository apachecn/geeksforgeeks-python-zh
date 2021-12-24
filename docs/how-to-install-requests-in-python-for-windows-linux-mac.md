# 如何在 Python 中安装请求–对于 windows、linux、mac

> 原文:[https://www . geesforgeks . org/how-install-requests-in-python-for-windows-Linux-MAC/](https://www.geeksforgeeks.org/how-to-install-requests-in-python-for-windows-linux-mac/)

Requests 是一个优雅而简单的 Python HTTP 库，是为人类构建的。全世界开发人员使用的最著名的 python 库之一。本文围绕如何在 Windows/ Linux/ macOS 等环境中安装 python 请求库展开。

## 装置

#### Windows 操作系统

要在 windows 中安装请求，需要 python(最好是最新版本)，所以如果您没有安装 Python，请前往–[如何在 Windows 上下载并安装 Python 最新版本](https://www.geeksforgeeks.org/how-to-download-and-install-python-latest-version-on-windows/)。现在从窗口打开命令提示符，并运行以下命令–

```py
python -m pip install requests
```

Booom..！！现在完成，请求库已成功下载。

#### Linux 操作系统

对于在 linux 中安装请求，需要 python(最好是最新版本)和 pip 最新版本，所以如果您没有安装 Python，请前往–[如何在 Linux 上下载和安装 Python 最新版本](https://www.geeksforgeeks.org/how-to-download-and-install-python-latest-version-on-linux/)。要在 linux 中安装 pip–[如何在 Linux 中安装 PIP？](https://www.geeksforgeeks.org/how-to-install-pip-in-linux/)。现在快跑，

```py
pip install requests
```

#### 苹果电脑

要在 mac 中安装请求，需要 python(最好是最新版本)和 pip 最新版本，所以如果您没有安装 Python，请前往–[如何在 mac 上下载和安装 Python 最新版本](https://www.geeksforgeeks.org/how-to-download-and-install-python-latest-version-on-macos-mac-os-x/)。要安装 pip mac Os。快跑，

```py
sudo easy_install pip
sudo pip install --upgrade pip 
```

现在要安装请求，

```py
pip install requests
```

#### 替代通用方法

在任何操作系统上安装请求的最后一种方法是抓取基础文件并手动安装请求，requests 是在 GitHub 上主动开发的，代码总是可用的。代码–[请访问此处](https://github.com/psf/requests)。
您可以克隆公共存储库:

```py
git clone git://github.com/psf/requests.git
```

或者，下载 tarball:

```py
curl -OL https://github.com/psf/requests/tarball/master
# optionally, zipball is also available (for Windows users).
```

一旦您有了源代码的副本，您就可以将其嵌入到您自己的 Python 包中，或者轻松地将其安装到您的站点包中:

```py
cd requests
pip install .
```

有关请求库的文档–[请访问此处](https://requests.readthedocs.io/en/latest/)