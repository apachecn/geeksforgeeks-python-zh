# Python 日历模块| HTMLCalendar formatmonth()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-html calendar-format month-method/](https://www.geeksforgeeks.org/python-calendar-module-htmlcalendar-formatmonth-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的阳历在两个方向上无限延长。

***类* `calendar.HTMLCalendar(firstweekday=0)`** 可以用来生成生成 HTML 日历..formatmonth()方法是 HTMLCalendar 实例的方法之一。

**`formatmonth()`** 方法在 Python 中是用来获取月历作为 HTML 表的。

> **语法:** formatmonth(年，月，带 year=True)
> 
> **参数:**
> **年:**日历年
> **月:**日历月
> **withyear:** 【可选】如果 withyear 为真，则该年将包含在表头中，否则仅使用月份名称。
> 
> **返回:**返回一个月的日历。

**代码#1:**

```py
# Python program to demonstrate working of formatmonth() method

# importing calendar module
import calendar

text_cal = calendar.HTMLCalendar(firstweekday = 0)

year = 2018
month = 9
# default value of width is 0

# printing formatmonth
print(text_cal.formatmonth(year, month))
```

**输出:**

```py
<table border="0" cellpadding="0" cellspacing="0" class="month">
    <tr>
        <th colspan="7" class="month">September 2018</th>
    </tr>
    <tr>
        <th class="mon">Mon</th>
        <th class="tue">Tue</th>
        <th class="wed">Wed</th>
        <th class="thu">Thu</th>
        <th class="fri">Fri</th>
        <th class="sat">Sat</th>
        <th class="sun">Sun</th>
    </tr>
    <tr>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="sat">1</td>
        <td class="sun">2</td>
    </tr>
    <tr>
        <td class="mon">3</td>
        <td class="tue">4</td>
        <td class="wed">5</td>
        <td class="thu">6</td>
        <td class="fri">7</td>
        <td class="sat">8</td>
        <td class="sun">9</td>
    </tr>
    <tr>
        <td class="mon">10</td>
        <td class="tue">11</td>
        <td class="wed">12</td>
        <td class="thu">13</td>
        <td class="fri">14</td>
        <td class="sat">15</td>
        <td class="sun">16</td>
    </tr>
    <tr>
        <td class="mon">17</td>
        <td class="tue">18</td>
        <td class="wed">19</td>
        <td class="thu">20</td>
        <td class="fri">21</td>
        <td class="sat">22</td>
        <td class="sun">23</td>
    </tr>
    <tr>
        <td class="mon">24</td>
        <td class="tue">25</td>
        <td class="wed">26</td>
        <td class="thu">27</td>
        <td class="fri">28</td>
        <td class="sat">29</td>
        <td class="sun">30</td>
    </tr>
</table>
```

**代码#2:** 带参数宽度

```py
# Python program to demonstrate working of formatmonth() method

# importing calendar module
import calendar

text_cal = calendar.HTMLCalendar(firstweekday = 0)

# printing formatmonth
print(text_cal.formatmonth(2018, 9))
```

**输出:**

```py
<table border="0" cellpadding="0" cellspacing="0" class="month">
    <tr>
        <th colspan="7" class="month">September 2018</th>
    </tr>
    <tr>
        <th class="mon">Mon</th>
        <th class="tue">Tue</th>
        <th class="wed">Wed</th>
        <th class="thu">Thu</th>
        <th class="fri">Fri</th>
        <th class="sat">Sat</th>
        <th class="sun">Sun</th>
    </tr>
    <tr>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="noday"> </td>
        <td class="sat">1</td>
        <td class="sun">2</td>
    </tr>
    <tr>
        <td class="mon">3</td>
        <td class="tue">4</td>
        <td class="wed">5</td>
        <td class="thu">6</td>
        <td class="fri">7</td>
        <td class="sat">8</td>
        <td class="sun">9</td>
    </tr>
    <tr>
        <td class="mon">10</td>
        <td class="tue">11</td>
        <td class="wed">12</td>
        <td class="thu">13</td>
        <td class="fri">14</td>
        <td class="sat">15</td>
        <td class="sun">16</td>
    </tr>
    <tr>
        <td class="mon">17</td>
        <td class="tue">18</td>
        <td class="wed">19</td>
        <td class="thu">20</td>
        <td class="fri">21</td>
        <td class="sat">22</td>
        <td class="sun">23</td>
    </tr>
    <tr>
        <td class="mon">24</td>
        <td class="tue">25</td>
        <td class="wed">26</td>
        <td class="thu">27</td>
        <td class="fri">28</td>
        <td class="sat">29</td>
        <td class="sun">30</td>
    </tr>
</table>
```

**代码#3:** 年份会包含在表头。

```py
# Python program to demonstrate working of formatmonth() method

# importing calendar module
import calendar

text_cal = calendar.HTMLCalendar(firstweekday = 0)

# printing formatmonth
print(text_cal.formatmonth(2018, 9, withyear = True))
```

**输出:**

```py
<table border ="0" cellpadding ="0" cellspacing ="0" class ="month">
    <tr>
        <th colspan ="7" class ="month">September 2018</th>
    </tr>
    <tr>
        <th class ="mon">Mon</th>
        <th class ="tue">Tue</th>
        <th class ="wed">Wed</th>
        <th class ="thu">Thu</th>
        <th class ="fri">Fri</th>
        <th class ="sat">Sat</th>
        <th class ="sun">Sun</th>
    </tr>
    <tr>
        <td class ="noday"> </td>
        <td class ="noday"> </td>
        <td class ="noday"> </td>
        <td class ="noday"> </td>
        <td class ="noday"> </td>
        <td class ="sat">1</td>
        <td class ="sun">2</td>
    </tr>
    <tr>
        <td class ="mon">3</td>
        <td class ="tue">4</td>
        <td class ="wed">5</td>
        <td class ="thu">6</td>
        <td class ="fri">7</td>
        <td class ="sat">8</td>
        <td class ="sun">9</td>
    </tr>
    <tr>
        <td class ="mon">10</td>
        <td class ="tue">11</td>
        <td class ="wed">12</td>
        <td class ="thu">13</td>
        <td class ="fri">14</td>
        <td class ="sat">15</td>
        <td class ="sun">16</td>
    </tr>
    <tr>
        <td class ="mon">17</td>
        <td class ="tue">18</td>
        <td class ="wed">19</td>
        <td class ="thu">20</td>
        <td class ="fri">21</td>
        <td class ="sat">22</td>
        <td class ="sun">23</td>
    </tr>
    <tr>
        <td class ="mon">24</td>
        <td class ="tue">25</td>
        <td class ="wed">26</td>
        <td class ="thu">27</td>
        <td class ="fri">28</td>
        <td class ="sat">29</td>
        <td class ="sun">30</td>
    </tr>
</table>
```