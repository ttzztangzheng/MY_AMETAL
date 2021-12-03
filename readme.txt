创建仓库：
	git init

将文件放到Git仓库只需要两步:
	1.git add 文件名				//把文件添加到仓库
	2.git commit -m "massage"		//把文件提交到仓库
	
仓库当前状态：
	git status

查看修改:
	git diff file_name
	
查看提交历史
	git log							//由近到远
	git log --pretty=oneline		//简化log输出
	
版本回退
	git reset --hard HEAD^			//上一个版本，HEAD~100上100个版本
	git reset --hard commit_id
	
查询命令历史
	git reflog						//可回退到未来版本
	
	
工作区	add	暂存区	commit	当前分支

查看工作区和版本库里面最新版本的区别：
	git diff HEAD -- readme.txt
	
撤销工作区的修改：
	git checkout -- file_name		//撤销回最新暂存或版本库
	git restire file_name

撤销暂存区的修改回到工作区，再撤销工作区	
	git restore --staged <file>
	git reset HEAD <file>
	
删除文件
	git rm <file>					//git status有提示撤销命令
	
将已有仓库与远端关联：
	git remote add origin git@github.com:ttzztangzheng/MY_AMETAL.git

把本地库的所有内容推送到远程库上：
	git push -u origin master
	
把本地master分支的最新修改推送至GitHub:
	git push origin master
	
删除远程库:
	git remote rm <name>
	
查看远程库信息:
	git remote -v
	
克隆一个本地库:
	git clone 远程库地址
	
创建分支：
	git checkout -b 分支名			//-b表示创建并切换
	git branch dev					//创建分支
	git checkout dev				//切换分支 两者与-b等价

查看当前分支：
	git branch						//列出所有分支，当前分支前面会标一个*号

合并分支到当前分支：
	git merge 分支名
		
删除分支：
	git branch -d 分支名

切换分支:
	git switch
	创建并切换到新的dev分支:
		git switch -c dev
	切换到已有的master分支:
		git switch master

查看分支合并图
	git log --graph
	
准备合并dev分支，请注意--no-ff参数，表示禁用Fast forward：
	强制禁用Fast forward模式，Git就会在merge时生成一个新的commit
	合并后的历史有分支，能看出来曾经做过合并
	git merge --no-ff -m "merge with no-ff" dev

储藏当前工作现场：
	git stash
	git stash lish			//查看stash列表
	git stash apply			//恢复工作区，但stash内容不删除，git stash apply stash@{0}
	git stash drop			//删除stash内容
	git stash pop			//恢复同时删除stash内容
	
在master分支上修复的bug，想要合并到当前dev分支，可以用git cherry-pick <commit>命令，把bug提交的修改“复制”到当前分支，避免重复劳动。	

多人协作的工作模式通常是这样：
	首先，可以试图用git push origin <branch-name>推送自己的修改；
	如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
	如果合并有冲突，则解决冲突，并在本地提交；
	没有冲突或者解决掉冲突后，再用git push origin <branch-name>推送就能成功！
	
	如果git pull提示no tracking information，
	则说明本地分支和远程分支的链接关系没有创建，
	用命令git branch --set-upstream-to <branch-name> origin/<branch-name>

还要改一下































	
	
	
	
