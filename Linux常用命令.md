# Linux 常用命令

1. **sudo** 意为 superuser do，是允许系统管理员让普通用户执行一些或者全部root命令的一个工具，如 halt、reboot、su等。
2. **进入 root 模式** `su` 即superuser之意，然后根据提示输入密码即可。进入root模式可拥有更多权限。
3. **修改密码** `sudo passwd root`其中passwd是password的缩写，然后根据提示输入新密码。
4. **根据文件名搜索文件** `find / -name "文件名"` 其中，/ 代表全盘搜索，也可以指定目录搜索，示例：`find '/media/jasonhan/DATA' -name "*水电*"`
5. 