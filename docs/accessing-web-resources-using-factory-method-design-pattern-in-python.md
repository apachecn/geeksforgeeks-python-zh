# 使用 Python 中的工厂方法设计模式访问 Web 资源

> 原文:[https://www . geesforgeks . org/access-web-resources-use-factory-method-design-pattern-in-python/](https://www.geeksforgeeks.org/accessing-web-resources-using-factory-method-design-pattern-in-python/)

工厂是一个用于构建其他对象的类，它基于传递的参数创建并返回一个对象。这里，客户端向工厂类提供材料，工厂类基于给定的材料创建并返回产品。工厂不是设计模式，但它是工厂方法设计模式的基础。

在进入工厂方法设计模式之前，让我们创建一个**简单工厂**。在下面的示例中， *SimpleFactory* 类有一个名为 *build_connection()* 的静态方法，用于基于接收到的参数创建对象。

## 蟒 3

```
import http.client
from ftplib import FTP

class SimpleFactory(object):

    @staticmethod
    def build_connection(protocol):
        if protocol == 'https':
            return http.client.HTTPSConnection('www.python.org')
        elif protocol == 'ftp':
            return FTP('ftp1.at.proftpd.org')
        else:
            raise RuntimeError('Unknown protocol')

if __name__ == '__main__':

    input_protocol = input('Which protocol to use? (https or ftp):')
    protocol = SimpleFactory.build_connection(input_protocol)

    if input_protocol == 'https':
        protocol.request("GET", "/")
        resp = protocol.getresponse()
        print(resp.status, resp.reason)

    elif input_protocol == 'ftp':
        resp = protocol.login()
        print(resp)
```