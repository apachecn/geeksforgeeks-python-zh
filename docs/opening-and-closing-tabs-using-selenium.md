# 使用硒打开和关闭拉环

> 原文:[https://www . geeksforgeeks . org/开合标签-使用-selenium/](https://www.geeksforgeeks.org/opening-and-closing-tabs-using-selenium/)

[Selenium](https://www.geeksforgeeks.org/browser-automation-using-selenium/) 是一个用于自动执行浏览器指令的工具。它对所有程序都很实用，处理所有重要的操作系统，其内容用不同的语言编写，即 Python、Java、C#等。

在本文中，我们使用 **Python** 作为语言， **Chrome** 作为网络驱动程序。

### 装置

可以使用以下命令安装 Python selenium 模块:

```py
pip install selenium
```

Chrome 驱动可以从 [Chrome 驱动](https://chromedriver.storage.googleapis.com/index.html?path=87.0.4280.88/)下载(版本== 87.0.4)。

## 使用硒打开标签

为了打开选项卡，需要一个 web 驱动程序。在这种情况下，我们使用的是 Chrome Webdriver。提供驱动程序路径后，使用**。get(URL)** 方法打开一个标签页。

## 蟒蛇 3

```py
# Import module
from selenium import webdriver

# Create object
driver = webdriver.Chrome()

# Assign URL
url = "https://www.geeksforgeeks.org/"

# Fetching the Url
driver.get(url)
```

**输出:**

<video class="wp-video-shortcode" id="video-542369-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210115194409/bandicam-2021-01-15-19-36-34-776.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210115194409/bandicam-2021-01-15-19-36-34-776.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210115194409/bandicam-2021-01-15-19-36-34-776.mp4)</video>

## 使用硒打开新标签页

为了打开一个新的标签页，可以使用 javascript 函数在一个新窗口中打开一个标签页。为了使用 javascript 的功能。 **executescript()** 可以使用硒的方法。执行完脚本后，我们可以使用**切换到窗口。switch_to_window()** 方法。

## 蟒蛇 3

```py
# import module
from selenium import webdriver

# Create object
driver = webdriver.Chrome()

# Assign URL
url = "https://www.geeksforgeeks.org/"

# New Url
new_url = "https://www.facebook.com/"

# Opening first url
driver.get(url)

# Open a new window
driver.execute_script("window.open('');")

# Switch to the new window and open new URL
driver.switch_to.window(driver.window_handles[1])
driver.get(new_url)
```

**输出:**

<video class="wp-video-shortcode" id="video-542369-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210115194412/bandicam-2021-01-15-19-39-16-121.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210115194412/bandicam-2021-01-15-19-39-16-121.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210115194412/bandicam-2021-01-15-19-39-16-121.mp4)</video>

## 使用硒关闭标签:

要关闭选项卡，**。使用 close()** 方法。

## 蟒蛇 3

```py
# Import module
from selenium import webdriver

# Create object
driver = webdriver.Chrome()

# Fetching the Url
url = "https://www.geeksforgeeks.org/"

# Opening first url
driver.get(url)

# Closing the tab
driver.close()
```

**输出:**

<video class="wp-video-shortcode" id="video-542369-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210115194414/bandicam-2021-01-15-19-40-51-839.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210115194414/bandicam-2021-01-15-19-40-51-839.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210115194414/bandicam-2021-01-15-19-40-51-839.mp4)</video>

## 使用 Selenium 关闭选项卡并切换到新的选项卡:

在多个标签的情况下，使用**关闭标签后。close()** 方法我们可以使用**切换到未关闭的标签页。switch_to_window()** 方法。

## 蟒蛇 3

```py
# Import module
from selenium import webdriver

# Create object
driver = webdriver.Chrome()

# Fetching the Url
url = "https://www.geeksforgeeks.org/"

# New Url
new_url = "https://www.facebook.com/"

# Opening first url
driver.get(url)

# Open a new window
driver.execute_script("window.open('');")

# Switch to the new window and open new URL
driver.switch_to.window(driver.window_handles[1])
driver.get(new_url)

# Closing new_url tab
driver.close()

# Switching to old tab
driver.switch_to.window(driver.window_handles[0])
```

**输出:**

<video class="wp-video-shortcode" id="video-542369-4" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210115194416/bandicam-2021-01-15-19-42-19-582.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20210115194416/bandicam-2021-01-15-19-42-19-582.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210115194416/bandicam-2021-01-15-19-42-19-582.mp4)</video>