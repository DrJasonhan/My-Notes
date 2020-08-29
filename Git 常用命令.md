# Git 常用命令

## 一、常用命令
1. **撤销更改**
git checkout -- <file>
2. **初始化** git init
3. **创建文件** touch 文件名，示例：touch testfile.txt
4. ** **

## 二、问题汇总
1. **git push -u origin master 与 git push origin master 的区别**
   git push origin master 推送到指定的远程仓库名(origin)的指定分支(master)。当只关联一个远程且只有一个分支时，其可以简写为 **git push**。但是，当关联了多个远程仓库、有多个分支时，直接用简化的语句可能会报错。
   git push -u origin master 的完全版为 git push --set-upstream origin master。指将本地的master分支推送到origin主机，同时指定origin为默认主机，后面就可以不加任何参数使用git push了。