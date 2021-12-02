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

1|1
	
	
	
	
