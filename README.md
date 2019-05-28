1. `git init`&emsp;初始化当前目录为 &nbsp;_`git`_&nbsp;版本库;
2. `git add [fileName]`&emsp;添加文件给 &nbsp;_`git`_ &nbsp;库管理;
3. `git commit -m(message) "提交说明"`&emsp;提交当前库的文件给 &nbsp;_`git`_ &nbsp;当前分支;
4. `git status`&emsp;查看文件修改状态;
5. `git diff`&emsp;显示文件的不同，查看修改过的位置;
6. `git log --pretty=oneline`&emsp;查看提交日志，显示每一次提交到暂存库的 ID、作者、日期;
   - `--pretty=oneline` &nbsp;将每次提交格式化显示为一行;
   - `-1`&nbsp;显示最近的一次提交;
7. `git reset --hard HEAD^`&emsp;回退到上一个版本;
   - `--hard` &nbsp;重置索引和工作树,之后对工作树中跟踪文件的任何更改&nbsp;_`commit`_&nbsp;都将被丢弃;
   - 用&nbsp;`HEAD`&nbsp;表示当前版本;
   - 用&nbsp;`HEAD^`&nbsp;表示上一个版本;
   - 用&nbsp;`HEAD^^`&nbsp;表示上上个版本;
   - 用&nbsp;`HEAD~100`&nbsp;表示前&nbsp;**100**&nbsp;个版本;
8. `git reflog`&emsp;记录每一次执行过的命令，可用于找到历史&nbsp;_`commitId`_;
9. `git checkout -- 文件名`&emsp;丢弃工作区的修改，也就是撤销工作区的全部修改;
   - `--`&nbsp;很重要，没有&nbsp;`--`&nbsp;，就变成了&emsp;**切换到另一个分支**&emsp;的命令;
10. `git reset HEAD 文件名`&emsp;把暂存区的修改撤销掉，重新放回工作区;
11. `git rm 文件名`&emsp;删除该文件，&nbsp;`git commit`&nbsp;后就从&nbsp;_`git`_ &nbsp;版本库中移除了;
12. `ssh-keygen -t rsa -C "邮箱"`&emsp;创建&ensp;`SSH Key`&ensp;;
13. `git remote add origin git@github.com:GitHub用户名/仓库名.git`&emsp;建立与远程仓库的连接;
14. `git push -u origin master`&emsp;把当前分支 master 推送到远程;
    - `-u` &nbsp;Git 不但会把本地的&nbsp;`master`&nbsp;分支内容推送到远程新的&nbsp;`master`&nbsp;分支，还会把本地的&nbsp;`master`&nbsp;分支和远程的&nbsp;`master`&nbsp;分支关联起来，在以后的推送或者拉取时就可以简化命令;
15. `git clone`&emsp;从远程服务器克隆仓库到本地;
16. `git branch`&emsp;命令会列出所有分支，当前分支前面会标一个&nbsp;`*`&nbsp;号;
17. `git checkout -b 分支名`&emsp;创建+切换分支;
    - `-b`&nbsp;参数表示创建并切换到新分支，相当于&nbsp;`git branch dev`&nbsp;和&nbsp;`git checkout dev`;
18. `git checkout -b 分支名 origin/分支名`&emsp;切换到远程分支;
19. `git merge 分支名`&emsp;命令用于合并指定分支到当前分支;
20. `git branch -d 分支名`&emsp;命令用于**删除**指定分支;
21. `git push origin -d 分支名`&emsp;命令用于**删除**远程分支，强行删除，需要使用大写的&nbsp;`-D`&nbsp;参数;
    - 先通过&nbsp;`git branch -d 分支名`&emsp;删除本地分支;
    - 再通过&nbsp;`git push origin : 分支名`&emsp;删除远程分支;
22. `git log --graph --pretty=oneline --abbrev-commit`&emsp;查看分支合并情况;
23. `git merge --no-ff -m "提交说明" 分支名`&emsp;强制禁用`Fast forward`模式合并分支;
    - 合并分支时，加上`--no-ff`参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并;
    - 本次合并要创建一个新的&nbsp;`commit`，所以加上&nbsp;`-m`&nbsp;参数，把&nbsp;`commit`&nbsp;描述写进去;
24. `git stash`&emsp;把当前工作现场&nbsp;**储藏**&nbsp;起来，等以后恢复现场后继续工作;
    - 工作只进行到一半，还没法提交，预计完成还需 1 天时间。但是，必须在两个小时内在&nbsp;`bug`&nbsp;分支修复&nbsp;`bug`&nbsp;时可使用;
    - `git stash list`&emsp;查看储藏列表;
    - 方法一用&nbsp;`git stash apply`&nbsp;恢复，但是恢复后，stash 内容并不删除，你需要用&nbsp;`git stash drop`&nbsp;来删除；
    - 方法二用&nbsp;`git stash pop`&nbsp;，恢复的同时把 stash 内容也删了;
25. `git remote -v`&emsp;查看远程详细信息;
26. `git pull`&emsp;拉取远程分支与本地分支合并;
    - 如果`git pull`提示`no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to 分支名 origin/分支名`。
27. `git tag <name>`&emsp;给分支打上标签，便于识别;
    - - 用&nbsp;`-d`&nbsp;删除标签;
28. `git show <tagname>`&emsp;查看标签信息;
29. `git tag -a v0.1 -m "version 0.1 released" 1094adb`&emsp;给历史版本打上标签;
    - 用&nbsp;`-a`&nbsp;指定标签名;
    - 用&nbsp;`-m`&nbsp;指定说明文字;
    - `1094adb`&nbsp;分支 ID;
30. `git push origin <tagname>`&emsp;推送标签到远程仓库;
31. `git config --global alias.st status`&emsp;配置别名，使用简写命令，`git st`看看效果;
    - `git config --global alias.co checkout`&nbsp;用&nbsp;`co`&nbsp;表示&nbsp;`checkout`&nbsp;;
    - `git config --global alias.ci commit`&nbsp;用&nbsp;`ci`&nbsp;表示&nbsp;`commit`&nbsp;;
    - `git config --global alias.br branch`&nbsp;用&nbsp;`br`&nbsp;表示&nbsp;`branch`&nbsp;;
