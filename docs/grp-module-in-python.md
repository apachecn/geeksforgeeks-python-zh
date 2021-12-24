# Python 中的 grp 模块

> 原文:[https://www.geeksforgeeks.org/grp-module-in-python/](https://www.geeksforgeeks.org/grp-module-in-python/)

Python 中的`***grp module***`提供了对 *Unix 组数据库*的访问。 *Unix 组数据库*的每个条目被报告为一个类似元组的对象，其属性类似于*组结构*的成员，该组结构在 [< grp.h >头](http://man7.org/linux/man-pages/man0/grp.h.0p.html)中定义。

以下是元组状对象的属性，表示存储在 *Unix 组数据库*中的条目:

| **指数** | **属性** | **表示** |
| --- | --- | --- |
| **0** | **gr_name** | **团体名称** |
| **1** | **gr_passwd** | **该(加密)组密码；常空** |
| **2** | **gr_gid** | **数字组标识** |
| **3** | **gr_mem** | **所有群成员的用户名** |

**注意:** `***grp module***`是 UNIX 特有的服务。因此，本模块的所有方法仅在 UNIX 版本上可用。

Python 中的`***grp.getgrnam()***`定义了以下方法:

*   `***grp.getgrgid() method***`
*   `***grp.getgrnam() method***`
*   `***grp.getgrall() method***`

## `*grp.getgrgid() method -*`

Python 中的`***grp.getgrgid()***`方法用于获取存储在 UNIX 组数据库中的指定组 id 的条目。*键错误*如果指定的组 id 无效或找不到与之关联的条目，则会引发异常。

> **语法:** grp.getgrgid(gid)
> 
> **参数:**
> **gid:** 表示需要组数据库条目的组 id 的整数值。
> 
> **返回类型:**这个方法返回一个类‘grp . struct _ group’的类似元组的对象，它代表与指定组 id (gid)相关联的组数据库条目。

**代码:**使用`***grp.getgrgid()***`方法

```py
# Python program to explain grp.getgrgid() method

# importing grp module 
import grp

# Group id
gid = 1000

# Get the group 
# database entry for the
# specified group id
# using grp.getgrgid() method
entry = grp.getgrgid(gid)

# Print the retrieved entry
print("Group database entry for group id % s:" % gid)
print(entry)

# Group id
gid = 0

# Get the group 
# database entry for the
# specified group id
# using grp.getgrgid() method
entry = grp.getgrgid(gid)

# Print the retrieved entry
print("\nGroup database entry for group id % s:" % gid)
print(entry)
```

**Output:**

> 组 id 1000 的组数据库条目:
> grp . struct _ group(gr _ name = ' ihritik '，gr_passwd='x '，gr_gid=1000，gr_mem=[])
> 
> 组 id 0 的组数据库条目:
> grp . struct _ group(gr _ name = ' root '，gr_passwd='x '，gr_gid=0，gr_mem=[])

## `*grp.getgrnam() method -*`

`***grp.getgrnam()***`Python 中的方法用于获取存储在 UNIX 组数据库中的指定组名的条目。*键错误*如果指定的组名无效或找不到与之关联的条目，则会引发异常。

> **语法:** grp.getgrnam(名称)
> 
> **参数:**
> **名称:**表示需要组数据库条目的组名的字符串值。
> 
> **返回类型:**这个方法返回一个类‘grp . struct _ group’的类似元组的对象，它代表与指定组名相关联的组数据库条目。

**代码:**使用`***grp.getgrnam()***`方法

```py
# Python program to explain grp.getgrnam() method

# importing grp module 
import grp

# Group name
name = "ihritik"

# Get the group 
# database entry for the
# specified group name
# using grp.getgrnam() method
entry = grp.getgrnam(name)

# Print the retrieved entry
print("Group database entry for the group name '%s':" %name)
print(entry)

# Group name
name = "root"

# Get the group 
# database entry for the
# specified group name
# using grp.getgrnam() method
entry = grp.getgrnam(name)

# Print the retrieved entry
print("\nGroup database entry for the group name '% s':" % name)
print(entry)
```

**Output:**

> 组名“ihritik”的组数据库条目:
> grp . struct _ group(gr _ name =“ihritik”，gr _ passwd =“x”，gr_gid=1000，gr_mem=[])
> 
> 组名“root”的组数据库条目:
> grp . struct _ group(gr _ name =“root”，gr _ passwd =“x”，gr_gid=0，gr_mem=[])

## `*grp.getgrall() method -*`

`***grp.getgrall()***`Python 中的方法用于获取存储在 UNIX 组数据库中的所有可用条目。

> **语法:** grp.getgrall()
> 
> **参数:**不需要参数。
> 
> **返回类型:**这个方法返回一个类‘grp . struct _ group’的类似元组的对象列表，其元素代表组数据库条目。

**代码:**使用`***grp.getgrall()***`方法

```py
# Python program to explain grp.getgrall() method

# importing grp module 
import grp

# Get the all available group 
# database entries
# using grp.getgrall() method
entries = grp.getgrall()

# Print the retrieved entry
print("Group database entries:")

for row in entries:
    print(row)
```

**Output:**

```py
Group database entries:
grp.struct_group(gr_name=’root’, gr_passwd=’x’, gr_gid=0, gr_mem=[])
grp.struct_group(gr_name=’daemon’, gr_passwd=’x’, gr_gid=1, gr_mem=[])
grp.struct_group(gr_name=’bin’, gr_passwd=’x’, gr_gid=2, gr_mem=[])
grp.struct_group(gr_name=’sys’, gr_passwd=’x’, gr_gid=3, gr_mem=[])
grp.struct_group(gr_name=’adm’, gr_passwd=’x’, gr_gid=4, gr_mem=[‘syslog’, ‘ihritik’])
grp.struct_group(gr_name=’tty’, gr_passwd=’x’, gr_gid=5, gr_mem=[])
grp.struct_group(gr_name=’disk’, gr_passwd=’x’, gr_gid=6, gr_mem=[])
grp.struct_group(gr_name=’lp’, gr_passwd=’x’, gr_gid=7, gr_mem=[])
grp.struct_group(gr_name=’mail’, gr_passwd=’x’, gr_gid=8, gr_mem=[])
grp.struct_group(gr_name=’news’, gr_passwd=’x’, gr_gid=9, gr_mem=[])
grp.struct_group(gr_name=’uucp’, gr_passwd=’x’, gr_gid=10, gr_mem=[])
grp.struct_group(gr_name=’man’, gr_passwd=’x’, gr_gid=12, gr_mem=[])
grp.struct_group(gr_name=’proxy’, gr_passwd=’x’, gr_gid=13, gr_mem=[])
grp.struct_group(gr_name=’kmem’, gr_passwd=’x’, gr_gid=15, gr_mem=[])
grp.struct_group(gr_name=’dialout’, gr_passwd=’x’, gr_gid=20, gr_mem=[])
grp.struct_group(gr_name=’fax’, gr_passwd=’x’, gr_gid=21, gr_mem=[])
grp.struct_group(gr_name=’voice’, gr_passwd=’x’, gr_gid=22, gr_mem=[])
grp.struct_group(gr_name=’cdrom’, gr_passwd=’x’, gr_gid=24, gr_mem=[‘ihritik’])
grp.struct_group(gr_name=’floppy’, gr_passwd=’x’, gr_gid=25, gr_mem=[])
grp.struct_group(gr_name=’tape’, gr_passwd=’x’, gr_gid=26, gr_mem=[])
grp.struct_group(gr_name=’sudo’, gr_passwd=’x’, gr_gid=27, gr_mem=[‘ihritik’])
grp.struct_group(gr_name=’audio’, gr_passwd=’x’, gr_gid=29, gr_mem=[‘pulse’])
grp.struct_group(gr_name=’dip’, gr_passwd=’x’, gr_gid=30, gr_mem=[‘ihritik’])
grp.struct_group(gr_name=’www-data’, gr_passwd=’x’, gr_gid=33, gr_mem=[])
grp.struct_group(gr_name=’backup’, gr_passwd=’x’, gr_gid=34, gr_mem=[])
grp.struct_group(gr_name=’operator’, gr_passwd=’x’, gr_gid=37, gr_mem=[])
grp.struct_group(gr_name=’list’, gr_passwd=’x’, gr_gid=38, gr_mem=[])
grp.struct_group(gr_name=’irc’, gr_passwd=’x’, gr_gid=39, gr_mem=[])
grp.struct_group(gr_name=’src’, gr_passwd=’x’, gr_gid=40, gr_mem=[])
grp.struct_group(gr_name=’gnats’, gr_passwd=’x’, gr_gid=41, gr_mem=[])
grp.struct_group(gr_name=’shadow’, gr_passwd=’x’, gr_gid=42, gr_mem=[])
grp.struct_group(gr_name=’utmp’, gr_passwd=’x’, gr_gid=43, gr_mem=[])
grp.struct_group(gr_name=’video’, gr_passwd=’x’, gr_gid=44, gr_mem=[])
grp.struct_group(gr_name=’sasl’, gr_passwd=’x’, gr_gid=45, gr_mem=[])
grp.struct_group(gr_name=’plugdev’, gr_passwd=’x’, gr_gid=46, gr_mem=[‘ihritik’])
grp.struct_group(gr_name=’staff’, gr_passwd=’x’, gr_gid=50, gr_mem=[])
grp.struct_group(gr_name=’games’, gr_passwd=’x’, gr_gid=60, gr_mem=[])
grp.struct_group(gr_name=’users’, gr_passwd=’x’, gr_gid=100, gr_mem=[])
grp.struct_group(gr_name=’nogroup’, gr_passwd=’x’, gr_gid=65534, gr_mem=[])
grp.struct_group(gr_name=’systemd-journal’, gr_passwd=’x’, gr_gid=101, gr_mem=[])
grp.struct_group(gr_name=’systemd-timesync’, gr_passwd=’x’, gr_gid=102, gr_mem=[])
grp.struct_group(gr_name=’systemd-network’, gr_passwd=’x’, gr_gid=103, gr_mem=[])
grp.struct_group(gr_name=’systemd-resolve’, gr_passwd=’x’, gr_gid=104, gr_mem=[])
grp.struct_group(gr_name=’systemd-bus-proxy’, gr_passwd=’x’, gr_gid=105, gr_mem=[])
grp.struct_group(gr_name=’input’, gr_passwd=’x’, gr_gid=106, gr_mem=[])
grp.struct_group(gr_name=’crontab’, gr_passwd=’x’, gr_gid=107, gr_mem=[])
grp.struct_group(gr_name=’syslog’, gr_passwd=’x’, gr_gid=108, gr_mem=[])
grp.struct_group(gr_name=’messagebus’, gr_passwd=’x’, gr_gid=109, gr_mem=[])
grp.struct_group(gr_name=’netdev’, gr_passwd=’x’, gr_gid=110, gr_mem=[])
grp.struct_group(gr_name=’mlocate’, gr_passwd=’x’, gr_gid=111, gr_mem=[])
grp.struct_group(gr_name=’ssl-cert’, gr_passwd=’x’, gr_gid=112, gr_mem=[])
grp.struct_group(gr_name=’uuidd’, gr_passwd=’x’, gr_gid=113, gr_mem=[])
grp.struct_group(gr_name=’rtkit’, gr_passwd=’x’, gr_gid=114, gr_mem=[])
grp.struct_group(gr_name=’avahi-autoipd’, gr_passwd=’x’, gr_gid=115, gr_mem=[])
grp.struct_group(gr_name=’bluetooth’, gr_passwd=’x’, gr_gid=116, gr_mem=[])
grp.struct_group(gr_name=’ssh’, gr_passwd=’x’, gr_gid=117, gr_mem=[])
grp.struct_group(gr_name=’lpadmin’, gr_passwd=’x’, gr_gid=118, gr_mem=[‘ihritik’])
grp.struct_group(gr_name=’whoopsie’, gr_passwd=’x’, gr_gid=119, gr_mem=[])
grp.struct_group(gr_name=’avahi’, gr_passwd=’x’, gr_gid=120, gr_mem=[])
grp.struct_group(gr_name=’scanner’, gr_passwd=’x’, gr_gid=121, gr_mem=[‘saned’])
grp.struct_group(gr_name=’saned’, gr_passwd=’x’, gr_gid=122, gr_mem=[])
grp.struct_group(gr_name=’pulse’, gr_passwd=’x’, gr_gid=123, gr_mem=[])
grp.struct_group(gr_name=’pulse-access’, gr_passwd=’x’, gr_gid=124, gr_mem=[])
grp.struct_group(gr_name=’colord’, gr_passwd=’x’, gr_gid=125, gr_mem=[])
grp.struct_group(gr_name=’geoclue’, gr_passwd=’x’, gr_gid=126, gr_mem=[])
grp.struct_group(gr_name=’gdm’, gr_passwd=’x’, gr_gid=127, gr_mem=[])
grp.struct_group(gr_name=’ihritik’, gr_passwd=’x’, gr_gid=1000, gr_mem=[])
grp.struct_group(gr_name=’sambashare’, gr_passwd=’x’, gr_gid=128, gr_mem=[‘ihritik’])
grp.struct_group(gr_name=’hadoop’, gr_passwd=’x’, gr_gid=1001, gr_mem=[‘master’])
grp.struct_group(gr_name=’master’, gr_passwd=’x’, gr_gid=1002, gr_mem=[])
```