# 如何使用 ipaddress 模块在 Python 中操纵 IP 地址？

> 原文:[https://www . geesforgeks . org/如何使用 ipaddress 模块操纵 python 中的 ip 地址/](https://www.geeksforgeeks.org/how-to-manipulate-ip-addresses-in-python-using-ipaddress-module/)

IP 地址代表互联网协议地址。这是与所选计算机或网络相关的识别号。当连接到网络时，该 IP 地址允许计算机发送和接收信息。Python 提供了 IP 地址模块，该模块提供了在 IPv4 和 IPv6 地址和网络上创建、操作和操作的能力。这个模块内置了 python 3.3+，所以如果你有 python 3.3+，就不需要安装它了。虽然可以用 pip 安装。

```
pip install ipaddress
```

该模块有 *IPv4Address* 类和 *IPv6Address* 类，分别处理 IPv4 和 IPv6 格式。由于 *IPv4Address* 和 *IPv6Address* 对象共享许多我们将只在 IPv4 格式中看到的公共属性，同样我们也可以在 IPv6 格式中看到。

### IPv4Address

IPv4 地址对象对于 IP v4 地址有很多属性。 **ipaddress。IPv4Address('Address')** 构造一个表示 IPv4 地址' address '的 IPv4Address 对象。该类的一些属性如下:

*   **max_prefixlen:** 返回 IPv4Address 对象表示的 IP 地址中的总位数(IPv4 为 32，IPv6 为 128)。
*   **is_multicast:** 如果该地址是为多播使用而保留的，则返回 True。
*   **是 _private:** 如果地址是为专用网络分配的，则返回 True。
*   **是 _ 全局:**如果地址是为公共网络分配的，则返回 True。
*   **为 _ 未指定:**如果地址未指定，则返回真。
*   **是 _ 保留的:**如果地址是 IETF 保留的，则返回真。
*   **是 _ 环回:**如果这是一个环回地址，返回真。
*   **是 _link_local:** 如果地址是为链路本地使用而保留的，则返回 True。

我们还可以使用比较运算符来比较地址对象。此外，我们可以从地址对象中添加或减去整数。

现在让我们看一个这些属性的例子。

**例:**

## 蟒 3

```
import ipaddress
# Creating an object of IPv4Address class and
# initializing it with an IPv4 address.
ip = ipaddress.IPv4Address('112.79.234.30')

# Print total number of bits in the ip.
print("Total no of bits in the ip:", ip.max_prefixlen)

# Print True if the IP address is reserved for multicast use.
print("Is multicast:", ip.is_multicast)

# Print True if the IP address is allocated for private networks.
print("Is private:", ip.is_private)

# Print True if the IP address is global.
print("Is global:", ip.is_global)

# Print True if the IP address is unspecified.
print("Is unspecified:", ip.is_unspecified)

# Print True if the IP address is otherwise IETF reserved.
print("Is reversed:", ip.is_reserved)

# Print True if the IP address is a loopback address.
print("Is loopback:", ip.is_loopback)

# Print True if the IP address is Link-local
print("Is link-local:", ip.is_link_local)

# next ip address
ip1 = ip + 1
print("Next ip:", ip1)

# previous ip address
ip2 = ip - 1
print("Previous ip:", ip2)

# Print True if ip1 is greater than ip2
print("Is ip1 is greater than ip2:", ip1 > ip2)
```

**输出:**

```
Total no of bits in the ip: 32
Is multicast: False
Is private: False
Is global: True
Is unspecified: False
Is reversed: False
Is loopback: False
Is link-local: False
Next ip: 112.79.234.31
Previous ip: 112.79.234.29
Is ip1 is greater than ip2: True
```

### IPv4Network

IPv4 网络对象用于检查和定义 IP 网络。地址对象的所有属性对网络对象也有效，此外，网络对象还提供了附加属性。下面列出了其中的一些。

*   **Network _ Address:** Returns the network address of the network.
*   **Broadcast _ Address:** Returns the broadcast address of the network. Every host on the network should receive packets sent to the broadcast address.
*   **Netmask:** Returns the netmask of the network.
*   [T0】 with _ net mask: 【T1] Returns the string representation of the network, and the mask is expressed in netmask.
*   [T0】 with _ host mask: 【T1] Returns the string representation of the network, which is represented by the hostmask symbol.
*   **Prefix:** Returns the length of the network prefix in bits.
*   [T0】 num _ address: 【T1] Returns the total number of addresses of this network.
*   **hosts ():** Returns the iterator of available hosts in the network. Available hosts are all IP addresses belonging to the network, except the network address itself and the network broadcast address.
*   **Overlapping (** Others **):** Returns True if the network is partially or completely contained in other networks, or all other networks are contained in the network.
*   **Subnet (** Prefixlen _ diff **):** According to the parameter value, return the joined subnet to define the current network. *Prefixlen _ diff parameter* is an integer indicating that the prefix length should be increased.
*   **supernet (** prefix _ diff **):** returns the supernet containing this network definition, *prefix _ diff* is the amount by which our prefix length should be reduced.
*   **subnet _ of (** other **):** If this network is a subnet of *other* , it will return true ( <u>is added in Python 3.7).</u>
*   **supernet _ of (** other **):** If this network is the supernet of *other* , it will return true ( <u>is added in Python 3.7).</u>
*   [T0】 Compare _ networks( 【T1] Others **):** Compare the ip network with other IP networks. In this comparison, only the network address is considered, not the host bit. It returns -1, 0 or 1.

现在让我们看一个上述方法的例子。

**例:**

## 蟒 3

```
import ipaddress

# Initializing an IPv4 Network.
network = ipaddress.IPv4Network("192.168.1.0/24")

# Print the network address of the network.
print("Network address of the network:", network.network_address)

# Print the broadcast address
print("Broadcast address:", network.broadcast_address)

# Print the network mask.
print("Network mask:", network.netmask)

# Print with_netmask.
print("with netmask:", network.with_netmask)

# Print with_hostmask.
print("with_hostmask:", network.with_hostmask)

# Print Length of network prefix in bits.
print("Length of network prefix in bits:", network.prefixlen)

# Print the number of hosts under the network.
print("Total number of hosts under the network:", network.num_addresses)

# Print if this network is under (or overlaps) 192.168.0.0/16
print("Overlaps 192.168.0.0/16:", network.overlaps(ipaddress.IPv4Network("192.168.0.0/16")))

# Print the supernet of this network
print("Supernet:", network.supernet(prefixlen_diff=1))

# Print if the network is subnet of 192.168.0.0/16.
print("The network is subnet of 192.168.0.0/16:",
      network.subnet_of(ipaddress.IPv4Network("192.168.0.0/16")))

# Print if the network is supernet of 192.168.0.0/16.
print("The network is supernet of 192.168.0.0/16:",
      network.supernet_of(ipaddress.IPv4Network("192.168.0.0/16")))

# Compare the ip network with 192.168.0.0/16.
print("Compare the network with 192.168.0.0/16:",
      network.compare_networks(ipaddress.IPv4Network("192.168.0.0/16")))
```

**输出:**

```
Network address of the network: 192.168.1.0
Broadcast address: 192.168.1.255
Network mask: 255.255.255.0
with netmask: 192.168.1.0/255.255.255.0
with_hostmask: 192.168.1.0/0.0.0.255
Length of network prefix in bits: 24
Total number of hosts under the network: 256
Overlaps 192.168.0.0/16: True
Supernet: 192.168.0.0/23
The network is subnet of 192.168.0.0/16: True
The network is supernet of 192.168.0.0/16: False
Compare the network with 192.168.0.0/16: 1
```