# GitLearn
git使用版本号  2.24.1.2  各个版本之间某些命令会存在差别,以具体使用版本为准(git命令行内一般有相关提示)  
说明：命令行后面 [] 里面的是可选参数，<> 里面是必需参数  
git init	初始化仓库 会生成 .git 的隐藏目录。  
git add <文件名>|<.>	添加修改到暂存区，'.'代表当前目录下所有文件。  
git commit -m <提交说明> [文件名]		提交文件，无文件名表示提交暂存区的所有文件。  
git add把文件添加进去，实际上就是把文件修改添加到暂存区，用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支，所以提交只会提交暂存区里面的内容。  
git status		查看工作区的状态。  
git log [--pretty=oneline]		查看日志，也可以使用git log --oneline。  
git reset --<hard>|<soft>|<mixed> <版本号>		回退到某个版本，HEAD可以代表当前版本，HEAD^标识上一个版本，符号^的个数N表示相对于当前版本的上N个版本，数量太多可以用HEAD~数量代替，如HEAD~100。soft参数会保留工作目录，并把指定的commit节点与当前分支的差异都存入暂存区。也就是说，没有被commit的代码也能够保留下来。mixed参数将会保留工作目录，并且把工作区，暂存区以及与reset的差异都放到工作区，然后清空暂存区，不带参数，也就是mixed模式。hard参数会重置暂存区和工作区，完全重置为指定的commit节点。当前分支没有commit的代码会被清除。  
git reflog		查看命令历史，可以查看回到哪个版本需要移动几步，回退操作前可以先使用该命令查看需要回退多少步 。  
git diff 	工作区与暂存区对比。  		
git diff <HEAD>|<版本号>		工作区与本地库对比。  
git diff -cached		暂存区与本地库对比。  
git restore <文件名>		 撤销未提交到暂存区的修改，工作区的修改被还原。  
git restore --staged <文件名> 		撤销已经提交到暂存区的修改(相当于清空暂存区关于该文件的内容，实际修改的内容还在工作区)。  
git rm <文件名>		提交对某个文件的删除操作到暂存区，之后可以用git commit提交到版本库，或者使用上面两个命令进行撤销操作。  
ssh-keygen -t rsa -C "youremail@example.com"		创建SSH Key。在用户主目录下(C:/用户/用户名)，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，没有执行此命令生成。登陆GitHub，打开“Account settings”，“SSH Keys”页面，然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容。  
git remote add <远程库名字> git@server-name:path/repo-name.git	关联远程库。  
git push [-u] <远程库名字> <远程库分支名>		将本地库推送至远程库，-u使用在第一次推送远程库分支的所有内容。  
git clone git@github.com:laolaoMonkey/GitLearn.git	克隆远程库。  
git branch <分支名称>	创建分支。  
git switch <分支名称>	切换到某分支。  
git switch -c <分支名称>	创建并切换到某分支，上面两条命令合起来的接单命令。  
git branch	[-v]	列出所有分支，会在当前分支前面显示*号，带上-v会在每个分支显示该分支最后一次提交日志及版本号。  
git merge <分支名称> 	将某分支的内容合并到指令改命令的分支。  
git branch -d <分支名称> 		删除某分支。  
Fast-forward		合并时显示信息，代表此次合并是“快进模式”，也就是直接把master指向dev的当前提交，所以合并速度非常快，不是每次合并都能Fast-forward。  
git log --graph 		查看分支合并图。  
git config [--global] user.name 用户名	git config [--global] user.email 邮箱地址		设置签名，带上--global标识设置全局级别的签名，设置项目级别需要在项目目录下执行该命令，设置签名后可以在远程库的提交日志里面看到提交人设置的签名信息。  
git help <具体命令> 		可以直接在浏览器打开具体命令的帮助文档(Git安装时自动安装在本地的文档)。  
git fetch <远程库名字> <远程库分支名>		拉取远程库的内容到本地，但是并不合并。  
git merge <远程库名字/远程库分支名>		把远程库拉取下来的内容合并到本地。  
git pull <远程库名字> <远程库分支名>		将远程库分支的内容拉取到本地并合并，相当于git fetch和git merge两条命令的合并命令。  
