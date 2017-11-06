## git 使用的有关命令

###创建版本库

	$ git init

* 添加文件
		
		$ git add readme.txt 

* 提交文件

		$ git commit -m "[MOD]"

###版本控制

* 当前的状态查看

		$ git status

* 查看difference

		$ git diff readme.txt 

* 历史记录查看

		$ git log

* 版本回退

		$ git reset --hard HEAD^
		上一个版本就是HEAD^,上上一个版本就是HEAD^^,HEAD~100
		$ git reflog（查看历史记录）
		$ git reset --hard 3628164 (回退指定版本)
		$ cat readme.txt（查看readme.txt文件内容）


* 保存当前的工作进度。

		git stash

* 拉取

		git pull

* 重新应用存储 (自动合并)

		git stash pop

* 查看分支

		git branch

* 列出远程分支

		git branch -r

* 列出本地分支和远程分支

		git branch -a

* 创建一个新的本地分支

		git branch newbranch2

* 重命名分支 _如果newbranch名字分支已经存在，则需要使用-M强制重命名，否则，使用-m进行重命名_

		git branch -m | -M oldbranch newbranch

* 删除branchname分支

		git branch -d | -D branchname

* 删除远程branchname分支

		git branch -d -r branchname

* 切换到一个branch

		git checkout branch

* 新建并且切换到该branch

		git checkout -b branch