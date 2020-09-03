# Linux 常用命令

1. **sudo** 意为 superuser do，是允许系统管理员让普通用户执行一些或者全部root命令的一个工具，如 halt、reboot、su等。
2. **进入 root 模式** `su` 即superuser之意，然后根据提示输入密码即可。进入root模式可拥有更多权限。
3. **修改密码** `sudo passwd root`其中passwd是password的缩写，然后根据提示输入新密码。
4. **根据文件名搜索文件** `find / -name "文件名"` 其中，/ 代表全盘搜索，也可以指定目录搜索，示例：`find '/media/jasonhan/DATA' -name "*水电*"`
5. `ls` 及 list 展示出文件夹下所有的文件，包含多个属性，举例：
   1. `-l`意为 long format，以详细列表的形式展示文件夹内容；
   2. `-a`意为 all，展示所有的文件，包括隐藏文件夹

6. **清空终端屏幕** `ctrl+l`或`clear`。
7. **清空当前输入的命令**`ctrl+u`
8. **移动光标快捷键**`ctrl+F`向后移动；`ctrl+B`向前移动；F 和 B 分别代表 Forward 和 Backward

9. **什么事Shell** 
   1. Shell是用户和内核之间的连接，其实就是一个应用程序，和QQ、微信一样，只不过，QQ微信是图形化界面，而Shell是命令行；
   ```mermaid
   graph BT;
   hardware("硬件(CPU、RAM、硬盘、显示器)") --> kernal("内核(驱动、文件系统、进程管理、网络服务等)")
   kernal-->hardware
   kernal-->shell(Shell)
   kernal-->otherApplication("其他应用程序(如QQ、微信)")   
   shell-->user("用户")
   otherApplication-->user
   shell-->otherApplication
   otherApplication-->shell
   ```
   1. Shell可被视为一种脚本语言，可以进行if else、print等变成；
   2. 对于Linux，Shell是开机自启的，否则无法运行系统；
   3. Shell真正的强大支持在于，可以组织协调其他的程序，可将一个程序的输出写入其他程序。
   4. 