# Python 日历模块:HTMLCalendar formatyearpage()方法

> 原文:[https://www . geesforgeks . org/python-calendar-module-html calendar-format yearpage-method/](https://www.geeksforgeeks.org/python-calendar-module-htmlcalendar-formatyearpage-method/)

日历模块允许像程序一样输出日历，并提供与日历相关的附加有用功能。日历模块中定义的函数和类使用理想化的日历，当前的公历在两个方向上无限延长。

***类* `calendar.HTMLCalendar(firstweekday=0)`** 可以用来生成生成 HTML 日历。formatyearpage()方法是 HTMLCalendar 实例的方法之一。

**`formatyearpage()`** 方法在 Python 中是用来获取年历作为一个完整的 HTML 页面。

> **语法:** formatyearpage(year，width=3，css='calendar.css '，编码=None)
> 
> **参数:**
> **年份:**日历年
> **宽度:**【默认值为 3】指定要使用的 css 的宽度日期栏
> **css:** 【可选】名称。
> **编码:**【可选】指定用于输出的编码
> 
> **返回:**返回一整年的 HTML 页面。

取决于构造函数中指定的或`setfirstweekday()`方法设置的第一个工作日。

**代码#1:**

```
# Python program to demonstrate working of formatyearpage() method

# importing calendar module
import calendar

text_cal = calendar.HTMLCalendar(firstweekday = 0)

year = 2018
# Default value of width is 3

# printing formatyearpage
print(text_cal.formatyearpage(year))
```

**输出:**

```
b'
<?xml version="1.0" encoding="utf-8"?>\n
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">\n
<html>\n
    <head>\n
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />\n

        <link rel="stylesheet" type="text/css" href="calendar.css" />\n
        <title>Calendar for 2018</title>\n
    </head>\n

    <body>\n
        <table border="0" cellpadding="0" cellspacing="0" class="year">\n
            <tr>
                <th colspan="3" class="year">2018</th>
            </tr>
            <tr>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">January</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n

                        <tr>
                            <td class="mon">1</td>
                            <td class="tue">2</td>
                            <td class="wed">3</td>
                            <td class="thu">4</td>
                            <td class="fri">5</td>
                            <td class="sat">6</td>
                            <td class="sun">7</td>
                        </tr>\n
                        <tr>
                            <td class="mon">8</td>
                            <td class="tue">9</td>
                            <td class="wed">10</td>
                            <td class="thu">11</td>
                            <td class="fri">12</td>
                            <td class="sat">13</td>
                            <td class="sun">14</td>
                        </tr>\n

                        <tr>
                            <td class="mon">15</td>
                            <td class="tue">16</td>
                            <td class="wed">17</td>
                            <td class="thu">18</td>
                            <td class="fri">19</td>
                            <td class="sat">20</td>
                            <td class="sun">21</td>
                        </tr>\n
                        <tr>
                            <td class="mon">22</td>
                            <td class="tue">23</td>
                            <td class="wed">24</td>
                            <td class="thu">25</td>
                            <td class="fri">26</td>
                            <td class="sat">27</td>
                            <td class="sun">28</td>
                        </tr>\n
                        <tr>
                            <td class="mon">29</td>
                            <td class="tue">30</td>
                            <td class="wed">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">February</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="thu">1</td>
                            <td class="fri">2</td>
                            <td class="sat">3</td>
                            <td class="sun">4</td>
                        </tr>\n
                        <tr>
                            <td class="mon">5</td>
                            <td class="tue">6</td>
                            <td class="wed">7</td>
                            <td class="thu">8</td>
                            <td class="fri">9</td>
                            <td class="sat">10</td>
                            <td class="sun">11</td>
                        </tr>\n
                        <tr>
                            <td class="mon">12</td>
                            <td class="tue">13</td>
                            <td class="wed">14</td>
                            <td class="thu">15</td>
                            <td class="fri">16</td>
                            <td class="sat">17</td>
                            <td class="sun">18</td>
                        </tr>\n
                        <tr>
                            <td class="mon">19</td>
                            <td class="tue">20</td>
                            <td class="wed">21</td>
                            <td class="thu">22</td>
                            <td class="fri">23</td>
                            <td class="sat">24</td>
                            <td class="sun">25</td>
                        </tr>\n
                        <tr>
                            <td class="mon">26</td>
                            <td class="tue">27</td>
                            <td class="wed">28</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">March</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="thu">1</td>
                            <td class="fri">2</td>
                            <td class="sat">3</td>
                            <td class="sun">4</td>
                        </tr>\n
                        <tr>
                            <td class="mon">5</td>
                            <td class="tue">6</td>
                            <td class="wed">7</td>
                            <td class="thu">8</td>
                            <td class="fri">9</td>
                            <td class="sat">10</td>
                            <td class="sun">11</td>
                        </tr>\n
                        <tr>
                            <td class="mon">12</td>
                            <td class="tue">13</td>
                            <td class="wed">14</td>
                            <td class="thu">15</td>
                            <td class="fri">16</td>
                            <td class="sat">17</td>
                            <td class="sun">18</td>
                        </tr>\n
                        <tr>
                            <td class="mon">19</td>
                            <td class="tue">20</td>
                            <td class="wed">21</td>
                            <td class="thu">22</td>
                            <td class="fri">23</td>
                            <td class="sat">24</td>
                            <td class="sun">25</td>
                        </tr>\n
                        <tr>
                            <td class="mon">26</td>
                            <td class="tue">27</td>
                            <td class="wed">28</td>
                            <td class="thu">29</td>
                            <td class="fri">30</td>
                            <td class="sat">31</td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
            </tr>
            <tr>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">April</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sun">1</td>
                        </tr>\n
                        <tr>
                            <td class="mon">2</td>
                            <td class="tue">3</td>
                            <td class="wed">4</td>
                            <td class="thu">5</td>
                            <td class="fri">6</td>
                            <td class="sat">7</td>
                            <td class="sun">8</td>
                        </tr>\n
                        <tr>
                            <td class="mon">9</td>
                            <td class="tue">10</td>
                            <td class="wed">11</td>
                            <td class="thu">12</td>
                            <td class="fri">13</td>
                            <td class="sat">14</td>
                            <td class="sun">15</td>
                        </tr>\n
                        <tr>
                            <td class="mon">16</td>
                            <td class="tue">17</td>
                            <td class="wed">18</td>
                            <td class="thu">19</td>
                            <td class="fri">20</td>
                            <td class="sat">21</td>
                            <td class="sun">22</td>
                        </tr>\n
                        <tr>
                            <td class="mon">23</td>
                            <td class="tue">24</td>
                            <td class="wed">25</td>
                            <td class="thu">26</td>
                            <td class="fri">27</td>
                            <td class="sat">28</td>
                            <td class="sun">29</td>
                        </tr>\n
                        <tr>
                            <td class="mon">30</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">May</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="tue">1</td>
                            <td class="wed">2</td>
                            <td class="thu">3</td>
                            <td class="fri">4</td>
                            <td class="sat">5</td>
                            <td class="sun">6</td>
                        </tr>\n
                        <tr>
                            <td class="mon">7</td>
                            <td class="tue">8</td>
                            <td class="wed">9</td>
                            <td class="thu">10</td>
                            <td class="fri">11</td>
                            <td class="sat">12</td>
                            <td class="sun">13</td>
                        </tr>\n
                        <tr>
                            <td class="mon">14</td>
                            <td class="tue">15</td>
                            <td class="wed">16</td>
                            <td class="thu">17</td>
                            <td class="fri">18</td>
                            <td class="sat">19</td>
                            <td class="sun">20</td>
                        </tr>\n
                        <tr>
                            <td class="mon">21</td>
                            <td class="tue">22</td>
                            <td class="wed">23</td>
                            <td class="thu">24</td>
                            <td class="fri">25</td>
                            <td class="sat">26</td>
                            <td class="sun">27</td>
                        </tr>\n
                        <tr>
                            <td class="mon">28</td>
                            <td class="tue">29</td>
                            <td class="wed">30</td>
                            <td class="thu">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">June</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="fri">1</td>
                            <td class="sat">2</td>
                            <td class="sun">3</td>
                        </tr>\n
                        <tr>
                            <td class="mon">4</td>
                            <td class="tue">5</td>
                            <td class="wed">6</td>
                            <td class="thu">7</td>
                            <td class="fri">8</td>
                            <td class="sat">9</td>
                            <td class="sun">10</td>
                        </tr>\n
                        <tr>
                            <td class="mon">11</td>
                            <td class="tue">12</td>
                            <td class="wed">13</td>
                            <td class="thu">14</td>
                            <td class="fri">15</td>
                            <td class="sat">16</td>
                            <td class="sun">17</td>
                        </tr>\n
                        <tr>
                            <td class="mon">18</td>
                            <td class="tue">19</td>
                            <td class="wed">20</td>
                            <td class="thu">21</td>
                            <td class="fri">22</td>
                            <td class="sat">23</td>
                            <td class="sun">24</td>
                        </tr>\n
                        <tr>
                            <td class="mon">25</td>
                            <td class="tue">26</td>
                            <td class="wed">27</td>
                            <td class="thu">28</td>
                            <td class="fri">29</td>
                            <td class="sat">30</td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
            </tr>
            <tr>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">July</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sun">1</td>
                        </tr>\n
                        <tr>
                            <td class="mon">2</td>
                            <td class="tue">3</td>
                            <td class="wed">4</td>
                            <td class="thu">5</td>
                            <td class="fri">6</td>
                            <td class="sat">7</td>
                            <td class="sun">8</td>
                        </tr>\n
                        <tr>
                            <td class="mon">9</td>
                            <td class="tue">10</td>
                            <td class="wed">11</td>
                            <td class="thu">12</td>
                            <td class="fri">13</td>
                            <td class="sat">14</td>
                            <td class="sun">15</td>
                        </tr>\n
                        <tr>
                            <td class="mon">16</td>
                            <td class="tue">17</td>
                            <td class="wed">18</td>
                            <td class="thu">19</td>
                            <td class="fri">20</td>
                            <td class="sat">21</td>
                            <td class="sun">22</td>
                        </tr>\n
                        <tr>
                            <td class="mon">23</td>
                            <td class="tue">24</td>
                            <td class="wed">25</td>
                            <td class="thu">26</td>
                            <td class="fri">27</td>
                            <td class="sat">28</td>
                            <td class="sun">29</td>
                        </tr>\n
                        <tr>
                            <td class="mon">30</td>
                            <td class="tue">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">August</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="wed">1</td>
                            <td class="thu">2</td>
                            <td class="fri">3</td>
                            <td class="sat">4</td>
                            <td class="sun">5</td>
                        </tr>\n
                        <tr>
                            <td class="mon">6</td>
                            <td class="tue">7</td>
                            <td class="wed">8</td>
                            <td class="thu">9</td>
                            <td class="fri">10</td>
                            <td class="sat">11</td>
                            <td class="sun">12</td>
                        </tr>\n
                        <tr>
                            <td class="mon">13</td>
                            <td class="tue">14</td>
                            <td class="wed">15</td>
                            <td class="thu">16</td>
                            <td class="fri">17</td>
                            <td class="sat">18</td>
                            <td class="sun">19</td>
                        </tr>\n
                        <tr>
                            <td class="mon">20</td>
                            <td class="tue">21</td>
                            <td class="wed">22</td>
                            <td class="thu">23</td>
                            <td class="fri">24</td>
                            <td class="sat">25</td>
                            <td class="sun">26</td>
                        </tr>\n
                        <tr>
                            <td class="mon">27</td>
                            <td class="tue">28</td>
                            <td class="wed">29</td>
                            <td class="thu">30</td>
                            <td class="fri">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">September</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sat">1</td>
                            <td class="sun">2</td>
                        </tr>\n
                        <tr>
                            <td class="mon">3</td>
                            <td class="tue">4</td>
                            <td class="wed">5</td>
                            <td class="thu">6</td>
                            <td class="fri">7</td>
                            <td class="sat">8</td>
                            <td class="sun">9</td>
                        </tr>\n
                        <tr>
                            <td class="mon">10</td>
                            <td class="tue">11</td>
                            <td class="wed">12</td>
                            <td class="thu">13</td>
                            <td class="fri">14</td>
                            <td class="sat">15</td>
                            <td class="sun">16</td>
                        </tr>\n
                        <tr>
                            <td class="mon">17</td>
                            <td class="tue">18</td>
                            <td class="wed">19</td>
                            <td class="thu">20</td>
                            <td class="fri">21</td>
                            <td class="sat">22</td>
                            <td class="sun">23</td>
                        </tr>\n
                        <tr>
                            <td class="mon">24</td>
                            <td class="tue">25</td>
                            <td class="wed">26</td>
                            <td class="thu">27</td>
                            <td class="fri">28</td>
                            <td class="sat">29</td>
                            <td class="sun">30</td>
                        </tr>\n
                    </table>\n
                </td>
            </tr>
            <tr>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">October</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="mon">1</td>
                            <td class="tue">2</td>
                            <td class="wed">3</td>
                            <td class="thu">4</td>
                            <td class="fri">5</td>
                            <td class="sat">6</td>
                            <td class="sun">7</td>
                        </tr>\n
                        <tr>
                            <td class="mon">8</td>
                            <td class="tue">9</td>
                            <td class="wed">10</td>
                            <td class="thu">11</td>
                            <td class="fri">12</td>
                            <td class="sat">13</td>
                            <td class="sun">14</td>
                        </tr>\n
                        <tr>
                            <td class="mon">15</td>
                            <td class="tue">16</td>
                            <td class="wed">17</td>
                            <td class="thu">18</td>
                            <td class="fri">19</td>
                            <td class="sat">20</td>
                            <td class="sun">21</td>
                        </tr>\n
                        <tr>
                            <td class="mon">22</td>
                            <td class="tue">23</td>
                            <td class="wed">24</td>
                            <td class="thu">25</td>
                            <td class="fri">26</td>
                            <td class="sat">27</td>
                            <td class="sun">28</td>
                        </tr>\n
                        <tr>
                            <td class="mon">29</td>
                            <td class="tue">30</td>
                            <td class="wed">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">November</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="thu">1</td>
                            <td class="fri">2</td>
                            <td class="sat">3</td>
                            <td class="sun">4</td>
                        </tr>\n
                        <tr>
                            <td class="mon">5</td>
                            <td class="tue">6</td>
                            <td class="wed">7</td>
                            <td class="thu">8</td>
                            <td class="fri">9</td>
                            <td class="sat">10</td>
                            <td class="sun">11</td>
                        </tr>\n
                        <tr>
                            <td class="mon">12</td>
                            <td class="tue">13</td>
                            <td class="wed">14</td>
                            <td class="thu">15</td>
                            <td class="fri">16</td>
                            <td class="sat">17</td>
                            <td class="sun">18</td>
                        </tr>\n
                        <tr>
                            <td class="mon">19</td>
                            <td class="tue">20</td>
                            <td class="wed">21</td>
                            <td class="thu">22</td>
                            <td class="fri">23</td>
                            <td class="sat">24</td>
                            <td class="sun">25</td>
                        </tr>\n
                        <tr>
                            <td class="mon">26</td>
                            <td class="tue">27</td>
                            <td class="wed">28</td>
                            <td class="thu">29</td>
                            <td class="fri">30</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">December</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sat">1</td>
                            <td class="sun">2</td>
                        </tr>\n
                        <tr>
                            <td class="mon">3</td>
                            <td class="tue">4</td>
                            <td class="wed">5</td>
                            <td class="thu">6</td>
                            <td class="fri">7</td>
                            <td class="sat">8</td>
                            <td class="sun">9</td>
                        </tr>\n
                        <tr>
                            <td class="mon">10</td>
                            <td class="tue">11</td>
                            <td class="wed">12</td>
                            <td class="thu">13</td>
                            <td class="fri">14</td>
                            <td class="sat">15</td>
                            <td class="sun">16</td>
                        </tr>\n
                        <tr>
                            <td class="mon">17</td>
                            <td class="tue">18</td>
                            <td class="wed">19</td>
                            <td class="thu">20</td>
                            <td class="fri">21</td>
                            <td class="sat">22</td>
                            <td class="sun">23</td>
                        </tr>\n
                        <tr>
                            <td class="mon">24</td>
                            <td class="tue">25</td>
                            <td class="wed">26</td>
                            <td class="thu">27</td>
                            <td class="fri">28</td>
                            <td class="sat">29</td>
                            <td class="sun">30</td>
                        </tr>\n

                        <tr>
                            <td class="mon">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
            </tr>
        </table>
    </body>\n
</html>\n'
```

请注意，可以生成日历的最早年份取决于平台。

**代码#2:** 宽度给定 5

```
# Python program to demonstrate working of formatyearpage() method

# importing calendar module
import calendar

text_cal = calendar.HTMLCalendar(firstweekday = 0)

# default value of width is 0

# printing formatyearpage
print(text_cal.formatyearpage(2018, 5, encoding = None))
```

**输出:**

```
b'
<?xml version="1.0" encoding="utf-8"?>\n
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
 "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">\n
<html>\n
    <head>\n
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />\n
        <link rel="stylesheet" type="text/css" href="calendar.css" />\n

        <title>Calendar for 2018</title>\n
    </head>\n
    <body>\n
        <table border="0" cellpadding="0" cellspacing="0" class="year">\n
            <tr>
                <th colspan="5" class="year">2018</th>
            </tr>
            <tr>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">January</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="mon">1</td>
                            <td class="tue">2</td>
                            <td class="wed">3</td>
                            <td class="thu">4</td>
                            <td class="fri">5</td>
                            <td class="sat">6</td>
                            <td class="sun">7</td>
                        </tr>\n
                        <tr>
                            <td class="mon">8</td>
                            <td class="tue">9</td>
                            <td class="wed">10</td>
                            <td class="thu">11</td>
                            <td class="fri">12</td>
                            <td class="sat">13</td>
                            <td class="sun">14</td>
                        </tr>\n
                        <tr>
                            <td class="mon">15</td>
                            <td class="tue">16</td>
                            <td class="wed">17</td>
                            <td class="thu">18</td>
                            <td class="fri">19</td>
                            <td class="sat">20</td>
                            <td class="sun">21</td>
                        </tr>\n
                        <tr>
                            <td class="mon">22</td>
                            <td class="tue">23</td>
                            <td class="wed">24</td>
                            <td class="thu">25</td>
                            <td class="fri">26</td>
                            <td class="sat">27</td>
                            <td class="sun">28</td>
                        </tr>\n
                        <tr>
                            <td class="mon">29</td>
                            <td class="tue">30</td>
                            <td class="wed">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">February</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="thu">1</td>
                            <td class="fri">2</td>
                            <td class="sat">3</td>
                            <td class="sun">4</td>
                        </tr>\n
                        <tr>
                            <td class="mon">5</td>
                            <td class="tue">6</td>
                            <td class="wed">7</td>
                            <td class="thu">8</td>
                            <td class="fri">9</td>
                            <td class="sat">10</td>
                            <td class="sun">11</td>
                        </tr>\n
                        <tr>
                            <td class="mon">12</td>
                            <td class="tue">13</td>
                            <td class="wed">14</td>
                            <td class="thu">15</td>
                            <td class="fri">16</td>
                            <td class="sat">17</td>
                            <td class="sun">18</td>
                        </tr>\n
                        <tr>
                            <td class="mon">19</td>
                            <td class="tue">20</td>
                            <td class="wed">21</td>
                            <td class="thu">22</td>
                            <td class="fri">23</td>
                            <td class="sat">24</td>
                            <td class="sun">25</td>
                        </tr>\n
                        <tr>
                            <td class="mon">26</td>
                            <td class="tue">27</td>
                            <td class="wed">28</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">March</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="thu">1</td>
                            <td class="fri">2</td>
                            <td class="sat">3</td>
                            <td class="sun">4</td>
                        </tr>\n
                        <tr>
                            <td class="mon">5</td>
                            <td class="tue">6</td>
                            <td class="wed">7</td>
                            <td class="thu">8</td>
                            <td class="fri">9</td>
                            <td class="sat">10</td>
                            <td class="sun">11</td>
                        </tr>\n
                        <tr>
                            <td class="mon">12</td>
                            <td class="tue">13</td>
                            <td class="wed">14</td>
                            <td class="thu">15</td>
                            <td class="fri">16</td>
                            <td class="sat">17</td>
                            <td class="sun">18</td>
                        </tr>\n
                        <tr>
                            <td class="mon">19</td>
                            <td class="tue">20</td>
                            <td class="wed">21</td>
                            <td class="thu">22</td>
                            <td class="fri">23</td>
                            <td class="sat">24</td>
                            <td class="sun">25</td>
                        </tr>\n
                        <tr>
                            <td class="mon">26</td>
                            <td class="tue">27</td>
                            <td class="wed">28</td>
                            <td class="thu">29</td>
                            <td class="fri">30</td>
                            <td class="sat">31</td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">April</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sun">1</td>
                        </tr>\n
                        <tr>
                            <td class="mon">2</td>
                            <td class="tue">3</td>
                            <td class="wed">4</td>
                            <td class="thu">5</td>
                            <td class="fri">6</td>
                            <td class="sat">7</td>
                            <td class="sun">8</td>
                        </tr>\n
                        <tr>
                            <td class="mon">9</td>
                            <td class="tue">10</td>
                            <td class="wed">11</td>
                            <td class="thu">12</td>
                            <td class="fri">13</td>
                            <td class="sat">14</td>
                            <td class="sun">15</td>
                        </tr>\n
                        <tr>
                            <td class="mon">16</td>
                            <td class="tue">17</td>
                            <td class="wed">18</td>
                            <td class="thu">19</td>
                            <td class="fri">20</td>
                            <td class="sat">21</td>
                            <td class="sun">22</td>
                        </tr>\n
                        <tr>
                            <td class="mon">23</td>
                            <td class="tue">24</td>
                            <td class="wed">25</td>
                            <td class="thu">26</td>
                            <td class="fri">27</td>
                            <td class="sat">28</td>
                            <td class="sun">29</td>
                        </tr>\n
                        <tr>
                            <td class="mon">30</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">May</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="tue">1</td>
                            <td class="wed">2</td>
                            <td class="thu">3</td>
                            <td class="fri">4</td>
                            <td class="sat">5</td>
                            <td class="sun">6</td>
                        </tr>\n
                        <tr>
                            <td class="mon">7</td>
                            <td class="tue">8</td>
                            <td class="wed">9</td>
                            <td class="thu">10</td>
                            <td class="fri">11</td>
                            <td class="sat">12</td>
                            <td class="sun">13</td>
                        </tr>\n
                        <tr>
                            <td class="mon">14</td>
                            <td class="tue">15</td>
                            <td class="wed">16</td>
                            <td class="thu">17</td>
                            <td class="fri">18</td>
                            <td class="sat">19</td>
                            <td class="sun">20</td>
                        </tr>\n
                        <tr>
                            <td class="mon">21</td>
                            <td class="tue">22</td>
                            <td class="wed">23</td>
                            <td class="thu">24</td>
                            <td class="fri">25</td>
                            <td class="sat">26</td>
                            <td class="sun">27</td>
                        </tr>\n
                        <tr>
                            <td class="mon">28</td>
                            <td class="tue">29</td>
                            <td class="wed">30</td>
                            <td class="thu">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
            </tr>
            <tr>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">June</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="fri">1</td>
                            <td class="sat">2</td>
                            <td class="sun">3</td>
                        </tr>\n
                        <tr>
                            <td class="mon">4</td>
                            <td class="tue">5</td>
                            <td class="wed">6</td>
                            <td class="thu">7</td>
                            <td class="fri">8</td>
                            <td class="sat">9</td>
                            <td class="sun">10</td>
                        </tr>\n
                        <tr>
                            <td class="mon">11</td>
                            <td class="tue">12</td>
                            <td class="wed">13</td>
                            <td class="thu">14</td>
                            <td class="fri">15</td>
                            <td class="sat">16</td>
                            <td class="sun">17</td>
                        </tr>\n
                        <tr>
                            <td class="mon">18</td>
                            <td class="tue">19</td>
                            <td class="wed">20</td>
                            <td class="thu">21</td>
                            <td class="fri">22</td>
                            <td class="sat">23</td>
                            <td class="sun">24</td>
                        </tr>\n
                        <tr>
                            <td class="mon">25</td>
                            <td class="tue">26</td>
                            <td class="wed">27</td>
                            <td class="thu">28</td>
                            <td class="fri">29</td>
                            <td class="sat">30</td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">July</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sun">1</td>
                        </tr>\n
                        <tr>
                            <td class="mon">2</td>
                            <td class="tue">3</td>
                            <td class="wed">4</td>
                            <td class="thu">5</td>
                            <td class="fri">6</td>
                            <td class="sat">7</td>
                            <td class="sun">8</td>
                        </tr>\n
                        <tr>
                            <td class="mon">9</td>
                            <td class="tue">10</td>
                            <td class="wed">11</td>
                            <td class="thu">12</td>
                            <td class="fri">13</td>
                            <td class="sat">14</td>
                            <td class="sun">15</td>
                        </tr>\n
                        <tr>
                            <td class="mon">16</td>
                            <td class="tue">17</td>
                            <td class="wed">18</td>
                            <td class="thu">19</td>
                            <td class="fri">20</td>
                            <td class="sat">21</td>
                            <td class="sun">22</td>
                        </tr>\n
                        <tr>
                            <td class="mon">23</td>
                            <td class="tue">24</td>
                            <td class="wed">25</td>
                            <td class="thu">26</td>
                            <td class="fri">27</td>
                            <td class="sat">28</td>
                            <td class="sun">29</td>
                        </tr>\n
                        <tr>
                            <td class="mon">30</td>
                            <td class="tue">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">August</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="wed">1</td>
                            <td class="thu">2</td>
                            <td class="fri">3</td>
                            <td class="sat">4</td>
                            <td class="sun">5</td>
                        </tr>\n
                        <tr>
                            <td class="mon">6</td>
                            <td class="tue">7</td>
                            <td class="wed">8</td>
                            <td class="thu">9</td>
                            <td class="fri">10</td>
                            <td class="sat">11</td>
                            <td class="sun">12</td>
                        </tr>\n
                        <tr>
                            <td class="mon">13</td>
                            <td class="tue">14</td>
                            <td class="wed">15</td>
                            <td class="thu">16</td>
                            <td class="fri">17</td>
                            <td class="sat">18</td>
                            <td class="sun">19</td>
                        </tr>\n
                        <tr>
                            <td class="mon">20</td>
                            <td class="tue">21</td>
                            <td class="wed">22</td>
                            <td class="thu">23</td>
                            <td class="fri">24</td>
                            <td class="sat">25</td>
                            <td class="sun">26</td>
                        </tr>\n
                        <tr>
                            <td class="mon">27</td>
                            <td class="tue">28</td>
                            <td class="wed">29</td>
                            <td class="thu">30</td>
                            <td class="fri">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">September</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sat">1</td>
                            <td class="sun">2</td>
                        </tr>\n
                        <tr>
                            <td class="mon">3</td>
                            <td class="tue">4</td>
                            <td class="wed">5</td>
                            <td class="thu">6</td>
                            <td class="fri">7</td>
                            <td class="sat">8</td>
                            <td class="sun">9</td>
                        </tr>\n
                        <tr>
                            <td class="mon">10</td>
                            <td class="tue">11</td>
                            <td class="wed">12</td>
                            <td class="thu">13</td>
                            <td class="fri">14</td>
                            <td class="sat">15</td>
                            <td class="sun">16</td>
                        </tr>\n
                        <tr>
                            <td class="mon">17</td>
                            <td class="tue">18</td>
                            <td class="wed">19</td>
                            <td class="thu">20</td>
                            <td class="fri">21</td>
                            <td class="sat">22</td>
                            <td class="sun">23</td>
                        </tr>\n
                        <tr>
                            <td class="mon">24</td>
                            <td class="tue">25</td>
                            <td class="wed">26</td>
                            <td class="thu">27</td>
                            <td class="fri">28</td>
                            <td class="sat">29</td>
                            <td class="sun">30</td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">October</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="mon">1</td>
                            <td class="tue">2</td>
                            <td class="wed">3</td>
                            <td class="thu">4</td>
                            <td class="fri">5</td>
                            <td class="sat">6</td>
                            <td class="sun">7</td>
                        </tr>\n
                        <tr>
                            <td class="mon">8</td>
                            <td class="tue">9</td>
                            <td class="wed">10</td>
                            <td class="thu">11</td>
                            <td class="fri">12</td>
                            <td class="sat">13</td>
                            <td class="sun">14</td>
                        </tr>\n
                        <tr>
                            <td class="mon">15</td>
                            <td class="tue">16</td>
                            <td class="wed">17</td>
                            <td class="thu">18</td>
                            <td class="fri">19</td>
                            <td class="sat">20</td>
                            <td class="sun">21</td>
                        </tr>\n
                        <tr>
                            <td class="mon">22</td>
                            <td class="tue">23</td>
                            <td class="wed">24</td>
                            <td class="thu">25</td>
                            <td class="fri">26</td>
                            <td class="sat">27</td>
                            <td class="sun">28</td>
                        </tr>\n
                        <tr>
                            <td class="mon">29</td>
                            <td class="tue">30</td>
                            <td class="wed">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
            </tr>
            <tr>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">November</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="thu">1</td>
                            <td class="fri">2</td>
                            <td class="sat">3</td>
                            <td class="sun">4</td>
                        </tr>\n
                        <tr>
                            <td class="mon">5</td>
                            <td class="tue">6</td>
                            <td class="wed">7</td>
                            <td class="thu">8</td>
                            <td class="fri">9</td>
                            <td class="sat">10</td>
                            <td class="sun">11</td>
                        </tr>\n
                        <tr>
                            <td class="mon">12</td>
                            <td class="tue">13</td>
                            <td class="wed">14</td>
                            <td class="thu">15</td>
                            <td class="fri">16</td>
                            <td class="sat">17</td>
                            <td class="sun">18</td>
                        </tr>\n
                        <tr>
                            <td class="mon">19</td>
                            <td class="tue">20</td>
                            <td class="wed">21</td>
                            <td class="thu">22</td>
                            <td class="fri">23</td>
                            <td class="sat">24</td>
                            <td class="sun">25</td>
                        </tr>\n
                        <tr>
                            <td class="mon">26</td>
                            <td class="tue">27</td>
                            <td class="wed">28</td>
                            <td class="thu">29</td>
                            <td class="fri">30</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
                <td>
                    <table border="0" cellpadding="0" cellspacing="0" class="month">\n
                        <tr>
                            <th colspan="7" class="month">December</th>
                        </tr>\n
                        <tr>
                            <th class="mon">Mon</th>
                            <th class="tue">Tue</th>
                            <th class="wed">Wed</th>
                            <th class="thu">Thu</th>
                            <th class="fri">Fri</th>
                            <th class="sat">Sat</th>
                            <th class="sun">Sun</th>
                        </tr>\n
                        <tr>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="sat">1</td>
                            <td class="sun">2</td>
                        </tr>\n
                        <tr>
                            <td class="mon">3</td>
                            <td class="tue">4</td>
                            <td class="wed">5</td>
                            <td class="thu">6</td>
                            <td class="fri">7</td>
                            <td class="sat">8</td>
                            <td class="sun">9</td>
                        </tr>\n
                        <tr>
                            <td class="mon">10</td>
                            <td class="tue">11</td>
                            <td class="wed">12</td>
                            <td class="thu">13</td>
                            <td class="fri">14</td>
                            <td class="sat">15</td>
                            <td class="sun">16</td>
                        </tr>\n
                        <tr>
                            <td class="mon">17</td>
                            <td class="tue">18</td>
                            <td class="wed">19</td>
                            <td class="thu">20</td>
                            <td class="fri">21</td>
                            <td class="sat">22</td>
                            <td class="sun">23</td>
                        </tr>\n
                        <tr>
                            <td class="mon">24</td>
                            <td class="tue">25</td>
                            <td class="wed">26</td>
                            <td class="thu">27</td>
                            <td class="fri">28</td>
                            <td class="sat">29</td>
                            <td class="sun">30</td>
                        </tr>\n
                        <tr>
                            <td class="mon">31</td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                            <td class="noday"> </td>
                        </tr>\n
                    </table>\n
                </td>
            </tr>
        </table>
    </body>\n
</html>\n'
```

HTMLCalendar 几乎没有可以覆盖的属性来自定义日历使用的 CSS 类。属性之一是**CSS class**。

**CSS class**是每个工作日使用的 CSS 类列表。默认列表为`cssclasses = ["mon", "tue", "wed", "thu", "fri", "sat", "sun"]`。风格可以每天修改，例如–`["mon text-bold", "tue", "wed", "thu", "fri", "sat", "sun red"]`