#Git notes
The good thing that people get older is that you become wiser. Well, the not so good thing is that **you forget things**... 

So that's why these notes are here :)

---

* Set proxy
		
		git config --global http.proxy http://proxyuser:proxypwd@proxy.server.com:8080

* Unset http.proxy
	
		git config --global --unset http.proxy



* stash
	* git stash  对当前的暂存区和工作区状态进行保存。 
	* git stash list  列出所有保存的进度列表。 
	* git stash pop [--index] [<stash>] 恢复工作进度
	
	* git stash apply [--index] [<stash>] 不删除已恢复的进度，其他同git stash pop 
	* git stash drop [<stash>] 删除某一个进度，默认删除最新进度 
	* git stash clear 删除所有进度 
	* git stash branch <branchname> <stash> 基于进度创建分支

	>生成测试环境

		// 初始化仓库，进行一次提交
		# git init stash-test
		# cd stash-test && echo 'hello'> readme
		# git add . && git commit -m "init"
		
		// 修改工作区和暂存区
		# echo 'need to be stashed' >> readme
		# git add readme
		
		// 查看此时工作区和版本库区别
		# git diff HEAD
		diff --git a/readme b/readme
		index ce01362..55d6c28 100644
		--- a/readme
		+++ b/readme
		@@ -1 +1,2 @@
		 hello
		+need to be stashed

	>执行stash及恢复


		// 暂存当前状态
		# git stash
		
		// 查看当前工作区和版本库区别
		# git diff HEAD
		==> 此时什么都没有输出，说明工作区被重置为HEAD指向内容了
		
		// 显示已暂存列表
		# git stash list
		stash@{0}: WIP on master: 440e976 init
		
		// 恢复暂存区和工作区进度
		# git stash pop --index stash@{0}
		
		// 查看工作区和版本库区别
		# git diff HEAD
		diff --git a/readme b/readme
		index ce01362..55d6c28 100644
		--- a/readme
		+++ b/readme
		@@ -1 +1,2 @@
		 hello
		+need to be stashed