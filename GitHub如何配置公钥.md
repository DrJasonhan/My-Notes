# GitHub 如何配置SSH密钥
## 1. SSH 是什么
SSH（Security shell, 安全外壳协议），是一种加密的网络传输协议，可以再不安全的网络中为网络服务提供安全的传输环境。SSH通过在网路中建立安全隧道来实现客户端与服务器之间的连接<font size=1.5>[[参考]](https://zh.wikipedia.org/wiki/Secure_Shell)</font>。
## 2. GitHub管理项目的两种方式 <font size=1.5>[[参考]](https://www.cnblogs.com/ayseeing/p/3572582.html)</font>
一种是直接使用 https url 克隆到本地，一种是使用SSH url 克隆到本地。对于初学者，使用https url比较方便，而在使用SSH之前，却需要先在本地配置好SSH Key。同时，如果想使用SSH url克隆，你必须是项目的拥有者，否则无法添加SSH key。
在clone项目时，使用https url可以随意clone；而使用SSH时，条件是自己是该项目的拥有者或管理员。
在push代码时，https url需要验证用户名和密码；SSH则不需要输入用户名，因为已经通过公钥和私钥在GitHub服务器上进行了定向的识别，如果设置了密码，则需要设置密码，也可以不设置。<font size=1.5>注：公钥是给服务器的，在生成密钥的时候，XXX.pub是公钥，XXX则是对应的私钥，一般存放在C:\Users\xxx\.ssh里面[[参考]](https://blog.csdn.net/wj123446/article/details/52781214)</font>
## 3. 如何生成密钥
**1. 验证是否存在密钥**
打开 git bash，输入
```
$ cd ~/.ssh
$ ls
```
第一句是转到SSH所在的文件夹，如果本地已经存在了密钥，命令行则会直接转到~/.ssh。ls是显示当前路径下的所有文件，与Linux中的命令相同。如果存在密钥，则会显示id_rsa_pub或id_dsa.pub。
**2. 创建一个SSH Key**
`$ ssh-keygen -t rsa -C"email@example.com"`
其中，-t 制定密钥的类型，默认是rsa，可以省略。
-C 设置注释文字，比如邮箱
-f 制定密钥文件存储文件名。
以上代码省略了-f参数，运行后会让你输入文件名，用于保存刚才生成的SSH Key，如：
```
Generating public/private rsa key pair.
# Enter file in which to save the key (/c/Users/you/.ssh/id_rsa): [Press enter]
```
也可以不输入文件名，直接回车，则会生成默认的密钥文件id_rsa.pub(公钥)和id_rsa(私钥)。
之后，会提示输入两次密码，注意，该密码是push文件的时候需要输入的，而不是GitHub管理者的密码。也可以不输入密码，直接回车，这样在push的时候就不需要输入密码，直接push了。
当代码如下提示，说明生成成功。
```
Your identification has been saved in /c/Users/you/.ssh/id_rsa.
Your public key has been saved in /c/Users/you/.ssh/id_rsa.pub.
```
接下来，输入：
```cat ~/.ssh/id_rsa.pub```
会显示当前已经生成的公钥，将其选中并复制到剪切板。
## 4. 如何将公钥添加到GitHub中
1. 登录GitHub并进入项目；
2. 点击右上角的账户，并进入Settings；
3. 在左边栏点击SSH and GPG keys；
4. 点击右上角New SSH key；
5. 将之前复制的公钥粘贴到Key文本框中；
6. 点击Add SSH key，完成。