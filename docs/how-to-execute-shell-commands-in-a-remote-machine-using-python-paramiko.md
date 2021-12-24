# 如何使用 Python-Paramiko 在远程机器中执行 Shell 命令

> 原文:[https://www . geesforgeks . org/如何使用 python-paramiko 执行远程机器中的 shell 命令/](https://www.geeksforgeeks.org/how-to-execute-shell-commands-in-a-remote-machine-using-python-paramiko/)

**Paramiko** 是一个 Python 库，通过 SSh 与远程设备进行连接。Paramiko 正在使用 SSH2 作为 SSL 的替代品，在两台设备之间建立安全连接。它还支持 SFTP 客户端和服务器模型。

### 正在验证 SSH 连接

要验证 SSH 连接，我们需要设置一个**私有 RSA SSH 密钥**(不要与 OpenSSH 混淆)。我们可以使用以下命令生成密钥:

> $ ssh-keygen -t rsa

这将提示我们为密钥提供一个名称。任意命名它，并生成一个公钥/私钥对。输入您希望用来保存密钥的名称。

> 即/home/username/。ssh/id_rsa

接下来，系统会提示您提供密码(请随意留空)。

现在我们有了密钥，我们需要将它复制到我们的远程主机上。最简单的方法是使用 **ssh-copy-id** :

> $ ssh-copy-id -i ~/。ssh/mykey 用户名@my_remote_host.org

如果你想检查你已经有哪些钥匙，这些可以在你的系统**中找到。ssh** 目录:

> ~/.sshCheck

我们正在寻找以下列标题开头的关键字:

> ——开始 RSA 私钥——
> 
> ——结束 RSA 私钥——

SSH(安全外壳)是在 SSH 协议中使用的访问凭证。换句话说，它是一种[加密](https://www.geeksforgeeks.org/cryptography-and-its-types/)网络协议，用于通过网络传输加密数据。它允许您连接到一台或多台服务器，而无需您记住或输入要从一个系统远程登录到另一个系统的每个系统的密码。

### 安装帕拉米科

要安装 paramiko 库，请在命令提示符下运行后续命令。paramiko 需要密码学作为依赖模块。因此，在命令提示符下运行这两个命令:

> pip 安装 paramiko
> 
> pip 安装加密

**注意:**更多信息请参考 [**在 Windows 和 Linux 上安装 Paramiko**](https://www.geeksforgeeks.org/python-install-paramiko-on-windows-and-linux/#:~:text=Paramiko%20is%20a%20Python%20library,SFTP%20client%20and%20server%20model.)

安装完成后，现在我们将使用 paramiko 库连接一个远程 SSH 服务器。等效代码片段如下所示:

## 蟒蛇 3

```py
import paramiko

# Create object of SSHClient and
# connecting to SSH
ssh = paramiko.SSHClient()
ssh.connect('1.1.1.2', port=22, username='UserName',
            password='PassWord', timeout=3)

# Adding new host key to the local
# HostKeys object(in case of missing)
ssh.set_missing_host_key_policy(paramiko.AutoAddPolicy())

# Execute command on SSH terminal
# using exec_command
stdin, stdout, stderr = ssh.exec_command('show ip interface brief')
```

以此为基础，只需使用一个 python 脚本，就可以自动登录到远程 SSH 服务器、执行命令和捕获结果。

通过这种方式，您可以在应用程序中创建到另一个主机的 SSH 连接，通过这种连接，您可以向主机发送命令并检索输出。

下面给出的程序也是如此。我们在这里打印用户名。

**程序:**

## 蟒蛇 3

```py
import paramiko
output_file = 'paramiko.org'

def paramiko_GKG(hostname, command):
    print('running')
    try:
        port = '22'

        # created client using paramiko
        client = paramiko.SSHClient()

        # here we are loading the system
        # host keys
        client.load_system_host_keys()

        # connecting paramiko using host
        # name and password
        client.connect(hostname, port=22, username='geeksForgeeks',
                       password='geeksForgeeks')

        # below line command will actually
        # execute in your remote machine
        (stdin, stdout, stderr) = client.exec_command(command)

        # redirecting all the output in cmd_output
        # variable
        cmd_output = stdout.read()
        print('log printing: ', command, cmd_output)

        # we are creating file which will read our
        # cmd_output and write it in output_file
        with open(output_file, "w+") as file:
            file.write(str(cmd_output))

        # we are returning the output
        return output_file
    finally:
        client.close()

paramiko_GKG('10.10.10.1', 'uname')
```

**输出:**

```py
$ python GFG_paramiko.py
running
[log printing: ,'uname','Linux\n']
```

因此，通过运行我们的 Python 文件，我们得到了一个带有 uname 命令和 Linux 作为输出的打印语句。相同的程序可以针对不同的命令进行修改，以根据需要获取信息。