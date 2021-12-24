# Python 中的 pwd 模块

> 原文:[https://www.geeksforgeeks.org/pwd-module-in-python/](https://www.geeksforgeeks.org/pwd-module-in-python/)

Python 中的`***pwd module***`提供了对 *Unix 用户帐户和密码数据库*的访问。存储在 *Unix 用户帐户和密码数据库*中的每个条目被报告为一个类似元组的对象，其属性类似于*密码结构*的成员，该结构在[T9】pwd . h>头文件](http://man7.org/linux/man-pages/man0/pwd.h.0p.html)中定义。

以下是元组状对象的属性，它代表存储在 Unix 用户帐户和密码数据库中的条目:

| **指数** | **属性** | **表示** |
| --- | --- | --- |
| **0** | **pw_name** | **登录名** |
| **1** | **pw_passwd** | **可选加密密码** |
| **2** | **pw_uid** | **数字用户标识** |
| **3** | **pwd_gid** | **数字组标识** |
| **4** | pw _ gecos | **用户名或评论栏** |
| **5** | pw _ dir | **用户主目录** |
| **6** | **pw_shell** | **用户命令解释器** |

**注意:** `***pwd module***`是 UNIX 特有的服务。因此，该模块的所有方法仅在 UNIX 版本上可用。

`***pwd module***`定义以下三种方法:

*   `***pwd.getpwuid() method***`
*   `***pwd.getpwnam() method***`
*   `***pwd.getpwall() method***`

## `*pwd.getpwuid() method -*`

Python 中的`***pwd.getpwnam()***`方法用于获取指定用户 id 的密码数据库条目。

> **语法:**pwd . get wuid(uid)
> 
> **参数:**
> **uid:** 代表需要输入密码数据库的用户 id 的数值。
> 
> **返回类型:**这个方法返回一个类‘pwd . struct _ passwd’的类似元组的对象，它代表指定用户 id 的密码数据库条目。

**代码:**使用 pwd.getpwuid()方法

```py
# Python program to explain pwd.getpwuid() method

# importing pwd module 
import pwd

# User id
uid = 1000

# Get the password 
# database entry for the
# specified user id
# using pwd.getpwuid() method
entry = pwd.getpwuid(uid)

# Print the retrieved entry
print("Password database entry for user id : % d:" % uid)
print(entry)

# User id
uid = 0

# Get the password 
# database entry for the
# specified user id
# using pwd.getpwuid() method
entry = pwd.getpwuid(uid)

# Print the retrieved entry
print("Password database entry for user id : % d:" % uid)
print(entry)
```

**Output:**

```py
Password database entry for user id : 1000
pwd.struct_passwd(pw_name='ihritik', pw_passwd='x', pw_uid=1000, pw_gid=1000,
pw_gecos='Hritik,,, ', pw_dir='/home/ihritik', pw_shell='/bin/bash')

Password database entry for user id : 0
pwd.struct_passwd(pw_name='root', pw_passwd='x', pw_uid=0, pw_gid=0, pw_gecos='root',
pw_dir='/root', pw_shell='/bin/bash')

```

## `*pwd.getpwnam() method -*`

Python 中的`***pwd.getpwnam()***`方法用于获取指定用户名的密码数据库条目

> **语法:** pwd.getpwnam(名称)
> 
> **参数:**
> **名称:**表示需要输入密码数据库的用户名的字符串值。
> 
> **返回类型:**这个方法返回一个类‘pwd . struct _ passwd’的类似元组的对象，它代表指定名称的密码数据库条目。

**代码:**使用 pwd.getpwnam()方法

```py
# Python program to explain pwd.getpwnam() method

# importing pwd module 
import pwd

# User name
name = "ihritik"

# Get the password 
# database entry for the
# specified username
# using pwd.getpwnam() method
entry = pwd.getpwnam(name)

# Print the retrieved entry
print("Password database entry for '% s':" % name)
print(entry)

# User name
name = "root"

# Get the password 
# database entry for the
# specified username
# using pwd.getpwnam() method
entry = pwd.getpwnam(name)

# Print the retrieved entry
print("\nPassword database entry for '% s':" % name)
print(entry)
```

**Output:**

```py
Password database entry for 'ihritik':
pwd.struct_passwd(pw_name='ihritik', pw_passwd='x', pw_uid=1000, pw_gid=1000,
pw_gecos='Hritik,,, ', pw_dir='/home/ihritik', pw_shell='/bin/bash')

Password database entry for 'root':
pwd.struct_passwd(pw_name='root', pw_passwd='x', pw_uid=0, pw_gid=0, pw_gecos='root',
pw_dir='/root', pw_shell='/bin/bash')

```

## `*pwd.getpwall()方法-*`

``***pwd.getpwall()***`Python 中的方法用于获取密码数据库中存储的所有可用条目的列表。`

> `**语法:**pwd . get wall()`
> 
> `**参数:**不需要参数。`
> 
> `**返回类型:**这个方法返回一个类‘pwd . struct _ passwd’的元组样对象的列表，其元素代表密码数据库中存储的所有可用条目。`

`**代码:**使用 pwd.getpwall()方法`

```py
# Python program to explain pwd.getpwall() method

# importing pwd module 
import pwd

# Get the list 
# of all available password
# database entries using
# pwd.getpwall() method
entries = pwd.getpwall()

# Print the list 
print("Password database entries:")
for row in entries:
    print(row)
```

`**Output:**

```py
Password database entries:
pwd.struct_passwd(pw_name=’root’, pw_passwd=’x’, pw_uid=0, pw_gid=0, pw_gecos=’root’, pw_dir=’/root’, pw_shell=’/bin/bash’)
pwd.struct_passwd(pw_name=’daemon’, pw_passwd=’x’, pw_uid=1, pw_gid=1, pw_gecos=’daemon’, pw_dir=’/usr/sbin’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’bin’, pw_passwd=’x’, pw_uid=2, pw_gid=2, pw_gecos=’bin’, pw_dir=’/bin’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’sys’, pw_passwd=’x’, pw_uid=3, pw_gid=3, pw_gecos=’sys’, pw_dir=’/dev’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’sync’, pw_passwd=’x’, pw_uid=4, pw_gid=65534, pw_gecos=’sync’, pw_dir=’/bin’, pw_shell=’/bin/sync’)
pwd.struct_passwd(pw_name=’games’, pw_passwd=’x’, pw_uid=5, pw_gid=60, pw_gecos=’games’, pw_dir=’/usr/games’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’man’, pw_passwd=’x’, pw_uid=6, pw_gid=12, pw_gecos=’man’, pw_dir=’/var/cache/man’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’lp’, pw_passwd=’x’, pw_uid=7, pw_gid=7, pw_gecos=’lp’, pw_dir=’/var/spool/lpd’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’mail’, pw_passwd=’x’, pw_uid=8, pw_gid=8, pw_gecos=’mail’, pw_dir=’/var/mail’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’news’, pw_passwd=’x’, pw_uid=9, pw_gid=9, pw_gecos=’news’, pw_dir=’/var/spool/news’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’uucp’, pw_passwd=’x’, pw_uid=10, pw_gid=10, pw_gecos=’uucp’, pw_dir=’/var/spool/uucp’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’proxy’, pw_passwd=’x’, pw_uid=13, pw_gid=13, pw_gecos=’proxy’, pw_dir=’/bin’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’www-data’, pw_passwd=’x’, pw_uid=33, pw_gid=33, pw_gecos=’www-data’, pw_dir=’/var/www’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’backup’, pw_passwd=’x’, pw_uid=34, pw_gid=34, pw_gecos=’backup’, pw_dir=’/var/backups’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’list’, pw_passwd=’x’, pw_uid=38, pw_gid=38, pw_gecos=’Mailing List Manager’, pw_dir=’/var/list’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’irc’, pw_passwd=’x’, pw_uid=39, pw_gid=39, pw_gecos=’ircd’, pw_dir=’/var/run/ircd’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’gnats’, pw_passwd=’x’, pw_uid=41, pw_gid=41, pw_gecos=’Gnats Bug-Reporting System (admin)’, pw_dir=’/var/lib/gnats’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’nobody’, pw_passwd=’x’, pw_uid=65534, pw_gid=65534, pw_gecos=’nobody’, pw_dir=’/nonexistent’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’systemd-timesync’, pw_passwd=’x’, pw_uid=100, pw_gid=102, pw_gecos=’systemd Time Synchronization,,, ‘, pw_dir=’/run/systemd’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’systemd-network’, pw_passwd=’x’, pw_uid=101, pw_gid=103, pw_gecos=’systemd Network Management,,, ‘, pw_dir=’/run/systemd/netif’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’systemd-resolve’, pw_passwd=’x’, pw_uid=102, pw_gid=104, pw_gecos=’systemd Resolver,,, ‘, pw_dir=’/run/systemd/resolve’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’systemd-bus-proxy’, pw_passwd=’x’, pw_uid=103, pw_gid=105, pw_gecos=’systemd Bus Proxy,,, ‘, pw_dir=’/run/systemd’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’syslog’, pw_passwd=’x’, pw_uid=104, pw_gid=108, pw_gecos=”, pw_dir=’/home/syslog’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’messagebus’, pw_passwd=’x’, pw_uid=105, pw_gid=109, pw_gecos=”, pw_dir=’/var/run/dbus’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’_apt’, pw_passwd=’x’, pw_uid=106, pw_gid=65534, pw_gecos=”, pw_dir=’/nonexistent’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’uuidd’, pw_passwd=’x’, pw_uid=107, pw_gid=113, pw_gecos=”, pw_dir=’/run/uuidd’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’rtkit’, pw_passwd=’x’, pw_uid=108, pw_gid=114, pw_gecos=’RealtimeKit,,, ‘, pw_dir=’/proc’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’avahi-autoipd’, pw_passwd=’x’, pw_uid=109, pw_gid=115, pw_gecos=’Avahi autoip daemon,,, ‘, pw_dir=’/var/lib/avahi-autoipd’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’usbmux’, pw_passwd=’x’, pw_uid=110, pw_gid=46, pw_gecos=’usbmux daemon,,, ‘, pw_dir=’/var/lib/usbmux’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’dnsmasq’, pw_passwd=’x’, pw_uid=111, pw_gid=65534, pw_gecos=’dnsmasq,,, ‘, pw_dir=’/var/lib/misc’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’whoopsie’, pw_passwd=’x’, pw_uid=112, pw_gid=119, pw_gecos=”, pw_dir=’/nonexistent’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’kernoops’, pw_passwd=’x’, pw_uid=113, pw_gid=65534, pw_gecos=’Kernel Oops Tracking Daemon,,, ‘, pw_dir=’/’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’speech-dispatcher’, pw_passwd=’x’, pw_uid=114, pw_gid=29, pw_gecos=’Speech Dispatcher,,, ‘, pw_dir=’/var/run/speech-dispatcher’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’avahi’, pw_passwd=’x’, pw_uid=115, pw_gid=120, pw_gecos=’Avahi mDNS daemon,,, ‘, pw_dir=’/var/run/avahi-daemon’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’saned’, pw_passwd=’x’, pw_uid=116, pw_gid=122, pw_gecos=”, pw_dir=’/var/lib/saned’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’pulse’, pw_passwd=’x’, pw_uid=117, pw_gid=123, pw_gecos=’PulseAudio daemon,,, ‘, pw_dir=’/var/run/pulse’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’colord’, pw_passwd=’x’, pw_uid=118, pw_gid=125, pw_gecos=’colord colour management daemon,,, ‘, pw_dir=’/var/lib/colord’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’hplip’, pw_passwd=’x’, pw_uid=119, pw_gid=7, pw_gecos=’HPLIP system user,,, ‘, pw_dir=’/var/run/hplip’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’geoclue’, pw_passwd=’x’, pw_uid=120, pw_gid=126, pw_gecos=”, pw_dir=’/var/lib/geoclue’, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’gdm’, pw_passwd=’x’, pw_uid=121, pw_gid=127, pw_gecos=’Gnome Display Manager’, pw_dir=’/var/lib/gdm3′, pw_shell=’/bin/false’)
pwd.struct_passwd(pw_name=’ihritik’, pw_passwd=’x’, pw_uid=1000, pw_gid=1000, pw_gecos=’Hritik,,, ‘, pw_dir=’/home/ihritik’, pw_shell=’/bin/bash’)
pwd.struct_passwd(pw_name=’sshd’, pw_passwd=’x’, pw_uid=122, pw_gid=65534, pw_gecos=”, pw_dir=’/run/sshd’, pw_shell=’/usr/sbin/nologin’)
pwd.struct_passwd(pw_name=’master’, pw_passwd=’x’, pw_uid=1001, pw_gid=1002, pw_gecos=’,,, ‘, pw_dir=’/home/master’, pw_shell=’/bin/bash’)
````