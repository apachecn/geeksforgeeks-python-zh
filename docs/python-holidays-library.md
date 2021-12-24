# Python |节假日库

> 原文:[https://www.geeksforgeeks.org/python-holidays-library/](https://www.geeksforgeeks.org/python-holidays-library/)

Python 假日库是一个高效的库，用于尽可能快速灵活地确定特定日期是否是假日。对于任何一个国家来说，都可以发现那一天是否是假日。只有固定的日子(公共)假期，如圣诞节、新年等。可以被检测到。

**安装:**

```py
pip install holidays
```

**语法:**

> 假期。假期基数(年=[]，展开=真，观察=真，证明=无，状态=无)

**参数:**

> **年:**指定假日对象应该预先生成的年的可迭代整数列表。这通常仅在设置扩展为假时使用。(默认[])
> 
> **展开:**一个布尔值，它指定是否将新年假期追加到假期对象中。(默认值:真)
> 
> **观察到的:**一个布尔值，当设置为真时，它将在适当的时候包括周末假日的观察到的一天。(默认值:真)
> 
> **省:**指定具有唯一法定假日的省份的字符串。(默认值:澳大利亚='ACT '，加拿大='ON '，新西兰=无)
> 
> **状态:**指定具有唯一法定假日的状态的字符串。(默认值:美国=无)

**方法:**

*   **get(key，默认值=None):** 返回包含日期键中假日名称的字符串，可以是日期、日期时间、字符串、unicode、字节、整数或浮点类型。如果多个假日在同一天，名字会用逗号隔开。
*   **get_list(键):**与 get 相同，只是返回假日名称列表，而不是逗号分隔的字符串。
*   **弹出(键，默认=无):**与`get`相同，只是键从假日对象更新/追加中移除。接受{date: name}对字典、日期列表，甚至单个日期/字符串/时间戳对象，并将它们添加到假日列表中。

**代码#1 :** 对于特定国家和年份，显示所有节假日。

```py
from datetime import date
import holidays

# Select country
uk_holidays = holidays.UnitedKingdom()

# Print all the holidays in UnitedKingdom in year 2018
for ptr in holidays.UnitedKingdom(years = 2018).items():
    print(ptr)
```

**输出:**

```py
(datetime.date(2018, 1, 1), "New Year's Day")
(datetime.date(2018, 1, 2), 'New Year Holiday [Scotland]')
(datetime.date(2018, 3, 17), "St. Patrick's Day [Northern Ireland]")
(datetime.date(2018, 3, 19), "St. Patrick's Day [Northern Ireland] (Observed)")
(datetime.date(2018, 3, 30), 'Good Friday')
(datetime.date(2018, 4, 2), 'Easter Monday [England, Wales, Northern Ireland]')
(datetime.date(2018, 5, 7), 'May Day')
(datetime.date(2018, 5, 28), 'Spring Bank Holiday')
(datetime.date(2018, 7, 12), 'Battle of the Boyne [Northern Ireland]')
(datetime.date(2018, 8, 6), 'Summer Bank Holiday [Scotland]')
(datetime.date(2018, 8, 27), 'Late Summer Bank Holiday [England, Wales, Northern Ireland]')
(datetime.date(2018, 11, 30), "St. Andrew's Day [Scotland]")
(datetime.date(2018, 12, 25), 'Christmas Day')
(datetime.date(2018, 12, 26), 'Boxing Day')

```

**代码#2 :** 检查给定日期是否为假日

```py
from datetime import date
import holidays

# Select country
uk_holidays = holidays.UnitedKingdom()

# If it is a holidays then it returns True else False
print('01-01-2018' in uk_holidays)
print('02-01-2018' in uk_holidays)

# What holidays is it?
print(uk_holidays.get('01-01-2018'))
print(uk_holidays.get('02-01-2018'))
```

**输出:**

```py
True
False
New Year's Day
None

```

**代码#3 :** 北美假期

```py
from datetime import date
import holidays

# Combining Countries
north_america = holidays.CA() + holidays.US() + holidays.MX()
# Output list of countries combined
print(north_america.country)

print(north_america.get('07-01-2018'))
print(north_america.get('07-04-2018'))
```

**输出:**

```py
['CA', 'US', 'MX']
Canada Day
Independence Day

```

**假日图书馆包含的国家列表–**

<colgroup><col><col><col></colgroup>
| 国家 | 缩写的/缩写词 | 可用省份/州 |
| --- | --- | --- |
| 阿根廷 | 阿肯色州 | 没有人 |
| 澳大利亚 | -干杯 | prov = **ACT** (默认值)，NSW，NT，QLD，SA，TAS，VIC，WA |
| 奥地利 | 在(某时间或时刻);在(学习或工作地点);在(某处) | prov = B、K、N、O、S、ST、T、V、 **W** (默认) |
| 比利时 | 存在 | 没有人 |
| 加拿大 | 加拿大 | prov = AB、BC、MB、NB、NL、NS、NT、NU、 **ON** (默认值)、
PE、QC、SK、YU |
| 哥伦比亚 | 指挥官（commanding officer) | 没有人 |
| 捷克人 | 捷克(Czech Republic) | 没有人 |
| 丹麦 | 丹麦 | 没有人 |
| 英格兰 |  | 没有人 |
| 欧洲中央银行 | 欧洲央行，西藏自治区 | 跨欧洲自动实时总结算(目标 2) |
| 芬兰 | 船方不负担装货费用 | 没有人 |
| 法国 | 联邦铁路局(Federal Railroad Administration) | (默认值)，Alsace-Moselle，Guadeloupe，圭亚那，
马提尼克，马约特，新喀里多尼亚，会议，
法属波利尼西亚，圣巴特梅，圣马丁，
瓦利斯和富图纳 |
| 德国 | 特拉华州 | BW、BY、BE、BB、HB、HH、HE、MV、NI、NW、RP、SL、SN、ST、
SH、TH |
| 匈牙利 | 胡（汉语拼音） | 没有人 |
| 爱尔兰 |  | 工业管理学(Industrial Engineering) |
| 马恩岛 |  | 没有人 |
| 意大利 | 信息技术 | S7-1200 可编程控制器 |
| 日本 | 地方官 | 没有人 |
| 墨西哥 | 麦克斯韦(maxwellˌ磁通量单位)ˌ中性(Middlesex) | 没有人 |
| 荷兰 | 荷兰 | 没有人 |
| 新西兰 | 新西兰 | prov = NTL，AUK，TKI，HKB，WGN，MBH，NSN，CAN，STC，WTL，
OTA，STL，CIT |
| 北爱尔兰 |  | 没有人 |
| 挪威 | 不 | 没有人 |
| 抛光剂 | 波兰 | 没有人 |
| 葡萄牙 | 体育锻炼 | 没有人 |
| 葡萄牙石 | 客运管理处 | *葡萄牙加上大部分人放假的延长天数* |
| 苏格兰 |  | 没有人 |
| 斯洛文尼亚 | 国际度量单位制 | 没有人 |
| 斯洛伐克 | 萨斯喀彻温 | 没有人 |
| 南非 | 为 | 没有人 |
| 西班牙 | 是吗 | prov = AND、ARG、AST、CAN、CAM、CAL、CAT、CVA、EXT、GAL、
IBA、ICA、MAD、MUR、NAV、PVA、RIO |
| 瑞典 | 如果 | 没有人 |
| 瑞士 | 荣誉勋位爵士 | prov = AG，AR，AI，BL，BS，BE，FR，GE，GL，GR，JU，LU，
NE，NW，OW，SG，SH，SZ，SO，TG，TI，UR，VD，VS，ZG，ZH |
| 大不列颠及北爱尔兰联合王国 | 英国 | 没有人 |
| 美国 | 美国 | state = AL，AK，AS，AZ，AR，CA，CO，CT，DE，DC，FL，GA，
GU，HI，ID，IL，IN，IA，KS，KY，LA，ME，MD，MH，MA，MI，
FM，MN，MS，MT，NE，NV，NH，NJ，NM，NY，NC，ND，MP，
哦，OK，OR，PW，PA，PR，RI，SC |
| 威尔士 |  | 没有人 |

在这个图书馆里，许多国家都不见了。所以，我们可以自己定制节日。

**代码#4 :** 印度自定义假日添加

```py
from datetime import date
import holidays

in_holidays = holidays.HolidayBase()

# Let's check our republic day
print('26-01-2019' in in_holidays)

# Add Holiday without description
in_holidays.append('26-01-2019')

# Let's verify
print('26-01-2019' in in_holidays) # True

# Let's Check Description
print(in_holidays.get('26-01-2019'))

# Add Holiday with description
in_holidays.append({'26-01-2019':'Republic Day India'})
print(in_holidays.get('26-01-2019'))

# Add list of Dates Together
in_holidays.append(['02-10-2018', '15-08-2018'])
print('15-08-2018' in in_holidays) # True
print('02-10-2018' in in_holidays) # True

# a single date item
in_holidays.append(date(2018, 12, 25))
print('25-12-2018' in in_holidays) # True
```

**输出:**

```py
False 
True 
Holiday 
Republic Day India, Holiday
True 
True 
True 

```

**参考:**[https://pypi.org/project/holidays/](https://pypi.org/project/holidays/)