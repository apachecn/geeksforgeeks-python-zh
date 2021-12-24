# 使用 Python 中的硒检查第 12 类结果

> 原文:[https://www . geesforgeks . org/check-12-class-result-use-selenium in-python/](https://www.geeksforgeeks.org/check-12th-class-result-using-selenium-in-python/)

我们将用以下信息收集 CSV 文件中的第 12 类数据:

1.  候选人姓名
2.  通过或失败状态
3.  分开
4.  获得分数

这个任务将使用 Python 的[硒库](https://www.geeksforgeeks.org/selenium-python-tutorial/)来完成。

**要求:**

你需要安装 chrome 驱动程序并设置路径。[点击此处](https://sites.google.com/a/chromium.org/chromedriver/downloads)下载。更多信息请点击[链接](https://www.geeksforgeeks.org/how-to-install-selenium-in-python/)。

**进场:**

1.  先去第 12 个网站，然后点击[链接](https://results.upmsp.edu.in/ResultIntermediate.aspx)(这是为了第 12 个结果)。
2.  然后通过紧急 ctrl + shift + i 或进入浏览器设置并手动点击调查细节来点击调查元素。
3.  然后导航到选择地区的框，然后复制 x_path。
4.  然后导航到填充辊号的框，然后复制 x_path。
5.  然后导航查看结果按钮，然后复制 x_path。
6.  我想将结果存储在 CSV 文件中，然后还导航学生姓名、不及格状态、部门、获得分数。然后通过脚本自动填写卷号，转到下一页找到学生姓名的 x_path，不及格状态，除法，获得分数。

**借助截图按部就班，复制元素的 x_path 放入代码:**

**第一步:**

![](img/474139dbd06808438800c3f1d83e3e92.png)

**第二步:**

![](img/6288063e296172c81a7b9d40f0047372.png)

**第三步:**

![](img/ff4296cd2809cfa4d2ecc57767bcbc68.png)

**第四步:**

![](img/2a468bc240889c6aafe4b9730ab66fee.png)

**第五步:**

![](img/c13fdbdba03eb2ce29dce29f69d82f1c.png)

**第六步:**

![](img/ebea683014cd95b4c655f799665d899a.png)

**第七步:**

![](img/99dda73a5abafbb3ab02a7b5fc83fa68.png)

**第八步:**

![](img/9d613dcdf731efb4a7ef35721d6db87e.png)

**第九步:**

![](img/a28501cdc7b3642fa004e243812785a8.png)

**第十步:**

![](img/1130773402cc7f12687a805c6a2db550.png)

**第 11 步:**

![](img/e15ac4efc5aefa35e1bb2bcebbaddd61.png)

**第 12 步:**

![](img/df338cc017a6c5d5f51bb7cfcb2b14b1.png)

下面是实现:

## 蟒蛇 3

```
# import required libraries
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import Select
from selenium.common.exceptions import NoSuchElementException
import csv 
import time

# give name of csv file
filename = "abc.csv"

# open file in write mode
f = open(filename, 'w')

# creat header in file
header = "NAME,STATUS,DIV,NUM\n"

# write into the file
f.write(header)

# put rollnumber without zero like
# your number 0477593 then
# put 477593 upto XXXXX.
start_rollNum = 926840
end_rollNum = 926841

# put range of rollnumber
for i in range(start_rollNum, end_rollNum ):

    # use try and except because if any rollnumber
    # is invalid then whole program is not stop.
    try:
        driver = webdriver.Chrome()

        # link is given above copy and paste
        driver.get("https://results.upmsp.edu.in/ResultIntermediate.aspx")

        # add zero in rollnumber in starting
        t = '0' + str(i)

        # district xpath
        state = driver.find_element_by_xpath('//*[@id="ctl00_cphBody_ddl_districtCode"]')
        drp1 = Select(state)

        # select district
        drp1.select_by_visible_text('LUCKNOW')

        # put rollnumber
        driver.find_element_by_xpath('//*[@id="ctl00_cphBody_txt_RollNumber"]').send_keys(t)

        # view result xpath
        driver.find_element_by_xpath('//*[@id="ctl00_cphBody_btnSubmit"]').click()

        # student name
        name = driver.find_element_by_xpath('//*[@id="ctl00_cphBody_lbl_C_NAME"]').text

        # status pass or fail
        status = driver.find_element_by_xpath('//*[@id="ctl00_cphBody_lbl_RESULT"]').text

        # division
        div = driver.find_element_by_xpath('//*[@id="ctl00_cphBody_lbl_DIVISION"]').text

        # obatin marks
        num = driver.find_element_by_xpath('//*[@id="ctl00_cphBody_lbl_MRK_OBT"]').text

        # all details fill into csv file
        f.write(name + "," + status + "," + 
                div[1 : ] + "," + num + "\n")

        # close the driver
        driver.close()

    except NoSuchElementException as exception:
        continue

# close and save the file
f.close()
```

**输出:**

![](img/39b6a781030970aa3d4493203025bd82.png)

CSV 屏幕快照文件

**注意:**如果你想找到一个 topper，那么在 CSV 文件上应用一个过滤器。