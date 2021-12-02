创建仓库：
	git init

将文件放到Git仓库只需要两步:
	1.git add 文件名				//把文件添加到仓库
	2.git commit -m "提交说明"		//把文件提交到仓库
	
仓库当前状态：
	git status

查看修改:
	git diff 文件名
	
查看历史提交日志
	git log							//由近到远
	git log --pretty=oneline		//简化log输出
	
版本回退
	git reset --hard HEAD^			//上一个版本，HEAD~100上100个版本
	git reset --hard 版本号
	
查询使用命令
	git reflog