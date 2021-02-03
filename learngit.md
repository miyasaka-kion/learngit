# Git Note

#### basic command:

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



#### 分支

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

处理未完成的工作现场：

`git stash`

恢复工作现场：

`git stash apply`

删除`stash`：

`git stash drop`

恢复并删除：

`git stash pop`

已经在其他分支上修复的bug，合并到另一个分支：

`git cherry-pick <commit>`

丢弃一个没有合并的分支：

`git branch -D <name>`




#### 多人协作

查看远程库信息：

`git remote -v`

在本地创建远程分支对应的分支：

`git checkout -b <branch_name> origin/<branch_name>`

尝试从本地推送分支：

`git push origin <branch_name>`

推送失败，说明远程分支版本新，先拉取：

`git pull`

解决冲突并且在本地提交；

冲突解决了，推送：

`git push origin <branch_name>`

如果`git pull`提示`no tracking information`，则需要创建本地分支很远程分支的链接关系：

`git branch--set-upstream-to <branch_name> origin/<branch_name>`  



#### 标签

新建一个标签（默认为`HEAD`）：

`git tag <tagname>`

制定标签信息：

`git tag -a <tagname> -m "<message>"`

查看标签：

`git tag`

推送一个本地标签：

`git push origin <tagname>`

推送全部未推送的本地标签：

`git push origin --tags`

删除一个本地标签：

`git tag -d <tagname>`

删除一个远程标签：

`git push origin :ref/tags/<tagname>`

#### 忽略特殊文件

写在`.gitignore` 中；

强行`add`会被`ignore`的文件：

`git add -f <file_name>`

排除所有`.`开头的文件但不排除`.gitignore`

```shell
# ignore all file begin with '.'
.*
# ignore all .class file
.class
# DO NOT ignore .gitignore and App.class
!.gitignore
!App.class
```

