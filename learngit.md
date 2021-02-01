Git Note

basic command:

`git add file`

`git commit ^m 'message'`

舍弃工作区的更改：

 `git checkout -- <filename>`

舍弃暂存区的更改：

`git reset HEAD <filename>`

查看历史：

`git log`

版本回退：

`git reset --hard HEAD^`, `git reset --hard <commit ID>`

要关联一个远程库：

`git remote add origin git@server-name:repo-name.git`

关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；

之后的每次提交：

`git push origin master`

从远程的库克隆：

`git clone <...>`