# Python 中的网络编程–DNS 查找

> 原文:[https://www . geesforgeks . org/network-programming-in-python-DNS-look/](https://www.geeksforgeeks.org/network-programming-in-python-dns-look-up/)

**域名系统**也叫 **DNS** 是互联网的一个电话簿，里面有和域名相关的内容。域名系统将域名转换为相应的 IP 地址，以便浏览器可以访问资源。Python 提供了 DNS 模块，用于处理域名到 IP 地址的转换。

### **查找记录**

dnspython 模块提供 dns.resolver()来帮助查找域名的各种记录。该函数接受两个重要参数，域名和记录类型。下面列举了一些带有例子的记录类型:

*   **A record:** is the basic type of DNS record, where a stands for address. It displays the IP address of the domain.

## 蟒 3

```
# Import libraries
import dns.resolver

# Finding A record
result = dns.resolver.query('geeksforgeeks.org', 'A')

# Printing record
for val in result:
    print('A Record : ', val.to_text())
```