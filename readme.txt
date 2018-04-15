Git is a distributed version control system.
Git is free software distributed under the GPL2.
$ mkdir xx  创建子目录
$ cd xx 进入该目录
$ pwd 显示该目录
$ git init  变成git可以管理的仓库
$git add
$git commit -m "xxx"  xxx代表本次修改大的有意义内容的记录
$git log或者git log --pretty=oneline
$git reflog
$git status 当前状态
$git diff readme.txt  查看做了什么修改
$git reset --hard HEAD^或HEAD~2
$git reset --hard 版本号
$cat readme.txt  查看readme.txt的内容
q代表返回上一级喔

git checkout -- file可以丢弃工作区的修改
一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
总之，就是让这个文件回到最近一次git commit或git add时的状态。
git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令

git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区

git rm file 删除文件 git commit提交修改-
git remote add origin git@github.com:chaserLX/learngit.git  本地关联远程库

git push -u origin（远程库的名字） master（master 分支）
本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程
由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地
的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master
分支关联起来，在以后的推送或者拉取时就可以简化命令

之后，就可以git push origin master 直接推送

git clone git@github.com:chaserLX/gitskills.git  从远程库克隆一个本地库

ls  查看你克隆的库

git checkout命令加上-b参数表示创建并切换 git checkout -b +（新分支的名字）

用git branch命令查看当前分支

dev分支的工作完成，我们就可以切换回master分支  git checkout master

如在dev分支修改了readme.txt，但是master的分支并没有被修改，可以dev分支的工作成果合并
到master分支上： git merge dev

合并完成后，就可以放心地删除dev分支（分支可实现类似平行宇宙的功能）
因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，
合并后再删掉分支，这和直接在master分支上工作效果是一样的，但过程更安全

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>