# 用 Python 自动发送生日邮件

> 原文:[https://www . geesforgeks . org/automatic-生日邮件-用 python 发送/](https://www.geeksforgeeks.org/automatic-birthday-mail-sending-with-python/)

你是否对给朋友送生日祝福感到厌烦，还是忘记给朋友送祝福，或者你想在凌晨 12 点给他们送祝福，但你总是睡着？为什么不通过编写 Python 脚本来自动化这个简单的任务。

我们首先要做的是导入六个库:

*   **熊猫**
*   [**日期时间**](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)
*   [**【smplib】**](https://www.geeksforgeeks.org/send-mail-gmail-account-using-python/)
*   **时间**
*   [**请求**](https://www.geeksforgeeks.org/python-requests-tutorial/)
*   **win10toast**

除此之外，还要创建一个 Excel 表来包含这样的记录:**姓名**、**电子邮件**、**联系人**、**生日**、**T9】和**年份**。**

**进场:**

*   对于发送邮件部分，我们定义了**sendmail()**函数，该函数将启动一个 Gmail 会话，发送电子邮件，并退出会话。
*   对于短信部分，我们必须在[www.fast2sms.com](https://www.fast2sms.com/)有一个账户，我们将从那里获得一个应用编程接口密钥。此 API 密钥用于在 fast2sms 上使用您的帐户通过移动号码发送短信，然后我们创建一个**发送短信()**功能，该功能将验证 API 密钥并发送短信。
*   在驱动程序代码部分，我们从 Excel 工作表中读取数据，并将今天的日期与任何生日进行匹配。如果匹配，我们调用**sendmail()**和 **sendsms()** 函数，并在 Excel 表中添加当前年份。此外，一旦电子邮件和短信发送成功，我们将使用 win10toast 库中的**发送通知程序**来显示桌面通知。

下面是实现:

## 计算机编程语言

```
# import required packages
import pandas as pd
import datetime
import smtplib
import time
import requests
from win10toast import ToastNotifier

# your gmail credentials here
GMAIL_ID = 'your_email_here'
GMAIL_PWD = 'your_password_here'

# for desktop notification
toast = ToastNotifier()

# define a function for sending email
def sendEmail(to, sub, msg):

    # conncection to gmail
    gmail_obj = smtplib.SMTP('smtp.gmail.com', 587) 

    # starting the session
    gmail_obj.starttls()     

    # login using credentials
    gmail_obj.login(GMAIL_ID, GMAIL_PWD)   

    # sending email
    gmail_obj.sendmail(GMAIL_ID, to, 
                   f"Subject : {sub}\n\n{msg}") 

    # quit the session
    gmail_obj.quit()  

    print("Email sent to " + str(to) + " with subject " 
          + str(sub) + " and message :" + str(msg))

    toast.show_toast("Email Sent!" , 
                     f"{name} was sent e-mail",
                     threaded = True, 
                     icon_path = None,
                     duration = 6)

    while toast.notification_active():
        time.sleep(0.1)

# define a funtion for sending sms        
def sendsms(to, msg, name, sub):

    url = "https://www.fast2sms.com/dev/bulk"
    payload = f"sender_id=FSTSMS&message={msg}&language=english&route=p&numbers={to}"

    headers = {
        'authorization': "API_KEY_HERE",
        'Content-Type': "application/x-www-form-urlencoded",
        'Cache-Control': "no-cache",
        }

    response_obj = requests.request("POST", url,
                                data = payload,
                                headers = headers)
    print(response_obj.text)
    print("SMS sent to " + str(to) + " with subject :" + 
          str(sub) + " and message :" + str(msg))

    toast.show_toast("SMS Sent!" ,
                     f"{name} was sent message", 
                     threaded = True, 
                     icon_path = None,
                     duration = 6)

    while toast.notification_active():
        time.sleep(0.1)

# driver code
if __name__=="__main__":

      # read the excel sheet having all the details
    dataframe = pd.read_excel("excelsheet.xlsx")   

    # today date in format : DD-MM
    today = datetime.datetime.now().strftime("%d-%m") 

    # current year in format : YY
    yearNow = datetime.datetime.now().strftime("%Y")

    # writeindex list
    writeInd = []                                                   

    for index,item in dataframe.iterrows():

        msg = "Many Many Happy Returns of the day dear " + str(item['NAME']) 

        # stripping the birthday in excel 
        # sheet as : DD-MM
        bday = item['Birthday'].strftime("%d-%m")        

        # condition checking
        if (today == bday) and yearNow not in str(item['Year']):    

            # calling the sendEmail function
            sendEmail(item['Email'], "Happy Birthday",
                      msg)    

            # calling the sendsms function
            sendsms(item['Contact'], msg, item['NAME'],
                    "Happy Birthday")   

            writeInd.append(index)                                  

    for i in writeInd:

        yr = dataframe.loc[i,'Year']

        # this will record the years in which
        # email has been sent
        dataframe.loc[i,'Year'] = str(yr) + ',' + str(yearNow)             

    dataframe.to_excel('excelsheet.xlsx', 
                index = False)
```