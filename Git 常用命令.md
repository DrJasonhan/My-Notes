# Git 常用命令

## 一、常用命令
1. **撤销更改** `git checkout -- <file>`。
2. **初始化** `git init`。
3. **建立与远程仓库的连接** `git remote add origin git@github.com:XXXXXXXX.git`,其中，remote 即远程；origin 是后面 github 地址的名称，也可自定义成其他名称；本地仓库可以 add 多个远程仓库，推送代码时可指定远程仓库推送。
4. **创建文件** touch 文件名，示例：`touch testfile.txt`。
5. **暂存文件** add 文件名，示例：`git add .`其中点 . 代表所有文件。
6. **提交到本地的版本库** git commit -m"添加说明"，示例：`git commit -m "修改了XX中的bug"`，其中，-m 中的 m 代表 message。

## 二、问题汇总
1. **git push -u origin master 与 git push origin master 的区别**
git push origin master 推送到指定的远程仓库名(origin)的指定分支(master)。当只关联一个远程且只有一个分支时，其可以简写为 **git push**。但是，当关联了多个远程仓库、有多个分支时，直接用简化的语句可能会报错。
git push -u origin master 的完全版为 git push --set-upstream origin master。指将本地的master分支推送到origin主机，同时指定origin为默认主机，后面就可以不加任何参数使用git push了。  
2. **单杠-和双杠--的区别**
   在命令行中，单杠-后面接的是缩写，双杠--后面要接全称
3. **在 GitHub 中，markdonw文件里的公式不能正常显示怎么办？**
   在 Google Chrome 中添加插件(https://chrome.google.com/webstore/detail/mathjax-plugin-for-github/ioemnmodlmafdkllaclgeombjnmnbima/related)
4. **当本地与远程仓库冲突时，如何合并** 先 `git pull`，然后手动在代码中进行修改，然后 `git push`。其中 `git pull` 相当于`git fetch`+`git merge`。