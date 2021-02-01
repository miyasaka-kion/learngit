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



查看分支：

`git branch`

创建分支：

`git branch <name>`

切换分支：

`git switch <name>`

创建+切换分支：

`git switch -c <name>`

合并某个分支到当前的分支：

`git merge <name>`

删除分支：

`git branch -d <name>`

合并（禁用`Fast forward`）到当前分支：

`git merge --no-ff -m "<message>" <branch_name>`

