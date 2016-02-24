# Git
Git使用指南

配置Git

     git config --global user.name "qiwei0727"  
     git config --global user.email "qiwei0727@163.com"
     
     
     
创建新仓库

     cd d:  //跳转到d盘  
     mkdir Git  //创建一个文件夹  
     cd Git    
     git init   
     git status : 查看仓库状态

克隆远端仓库

git clone https://github.com/qiwei0727/Git.git

本地操作原理

你的本地仓库由 git 维护的三棵“树”组成。

第一个是你的 工作目录，它持有实际文件；
第二个是 暂存区（Index），它像个缓存区域，临时保存你的改动；
最后是 HEAD，它指向你最后一次提交的结果。
这里写图片描述

添加并提交

 git add .//把它们添加到暂存区
 git add <filename>

这是 git 基本工作流程的第一步；使用如下命令以实际提交改动：

git commit -m "代码提交信息"  
git log //查看提交历史

现在，你的改动已经提交到了 HEAD，但是还没到你的远端仓库。

这个命令会把之前所有的已经添加的文件都加入到这个版本中。

    git commit -a -m "代码提交信息"
推送到远端仓库

你的改动现在已经在本地仓库的 HEAD 中了。

执行如下命令以将这些改动提交到远端仓库：

    git push -u origin master//第一次用这个
    git push origin master

可以把 master 换成你想要推送的任何分支。

如果你还没有克隆现有仓库，并欲将你的仓库连接到某个远程服务器（关联一个远程库）， 
你可以使用如下命令添加：

    git remote add origin https://github.com/tugenhua0707/testgit 

push-username 
push-password

如此你就能够将你的改动推送到所添加的服务器上去了。
