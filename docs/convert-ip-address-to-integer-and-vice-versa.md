# 将 IP 地址转换为整数，反之亦然

> 原文:[https://www . geesforgeks . org/convert-IP-address-to-integer-反之亦然/](https://www.geeksforgeeks.org/convert-ip-address-to-integer-and-vice-versa/)

为此，我们将使用[IP 地址模块](https://docs.python.org/3/library/ipaddress.html)。ipaddress 是一个帮助创建、操作和操作 IPv4 和 IPv6 地址和网络的模块。

将 IP 地址转换为整数，反之亦然的动机是，使用 IP 地址的其他模块(如套接字)通常不会直接接受 IP 地址模块的对象。相反，它们必须转换为字符串或其他模块可以接受的整数。

> **语法:** ipaddress.ip_address(地址)
> 
> **参数:**以整数或字符串形式传递 IP 地址。小于 2**32 的整数值被视为 IPv4 地址。
> 
> **返回:**根据作为参数传递的 IP 地址，返回 IPv4Address 或 IPv6Address 对象。如果传递的地址不代表有效的 IPv4 或 IPv6 地址，则会引发值错误。

将整数转换为 IP 地址的程序:

## 蟒蛇 3

```
# importing the module
import ipaddress

# converting int to IPv4 address
print(ipaddress.ip_address(3221225000))
print(ipaddress.ip_address(123))

# converting int to IPv6 address
print(ipaddress.ip_address(42540766400282592856903984001653826561))
```

**输出:**

```
191.255.254.40
0.0.0.123
2001:db7:dc75:365:220a:7c84:d796:6401
```

对于将 IP 地址转换为整数:

## 蟒蛇 3

```
# importing the module
import ipaddress

# converting IPv4 address to int
addr1 = ipaddress.ip_address('191.255.254.40')
addr2 = ipaddress.ip_address('0.0.0.123')
print(int(addr1))
print(int(addr2))

# converting IPv6 address to int
addr3 = ipaddress.ip_address('2001:db7:dc75:365:220a:7c84:d796:6401')
print(int(addr3))
```

**输出:**

```
3221225000
123
42540766400282592856903984001653826561
```