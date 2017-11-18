# Git使用指南
### 版本控制系统

#### 1. 集中式

版本库是集中存放在中央服务器的，而干活的时候，用的都是自己的电脑，所以要先从中央服务器取得最新的版本，然后开始干活，干完活了，再把自己的活推送给中央服务器。

最大的毛病就是必须联网才能工作，如果在局域网内还好，带宽够大，速度够快，可如果在互联网上，遇到网速慢的话，可能提交一个10M的文件就需要5分钟，这还不得把人给憋死啊。

#### 2. 分布式

每个人的电脑上都是一个完整的版本库，这样，你工作的时候，就不需要联网了，因为版本库就在你自己的电脑上。

分布式版本控制系统的安全性要高很多，因为每个人电脑里都有完整的版本库，某一个人的电脑坏掉了不要紧，随便从其他人那里复制一个就可以了。而集中式版本控制系统的中央服务器要是出了问题，所有人都没法干活了。

### 配置Git
```
git config --global user.name "qiwei0727"  
git config --global user.email "qiwei0727@163.com"
```  
### 创建新仓库
```
cd d:  //跳转到d盘  
mkdir Git  //创建一个文件夹  
cd Git    

git init   //初始化一个Git仓库

git clone https://github.com/qiwei0727/Git.git//克隆远端仓库

//添加文件到暂存区
git add readme.txt  （添加单个文件）
git add .   (添加所有未添加)

//暂存区的所有内容提交到当前分支
git commit -m ""

//仓库当前的状态
git status 

//查看文件内容
cat readme.txt 

//差异
git diff readme.txt

//查看工作区和版本库里面最新版本的区别
git diff HEAD -- readme.txt

//查看提交日志
git log

```
### 本地操作原理

你的本地仓库由 git 维护的三棵“树”组成。

1. 第一个是你的 工作目录，它持有实际文件；
2. 第二个是 暂存区（Index），它像个缓存区域，临时保存你的改动；
3. 最后是 HEAD，它指向你最后一次提交的结果。

### 推送到远端仓库

你的改动现在已经在本地仓库的 HEAD 中了。

执行如下命令以将这些改动提交到远端仓库：
```
git push -u origin master//第一次用这个
git push origin master
```
可以把 master 换成你想要推送的任何分支。

如果你还没有克隆现有仓库，并欲将你的仓库连接到某个远程服务器（关联一个远程库）， 
你可以使用如下命令添加：
```
git remote add origin https://github.com/tugenhua0707/testgit 
```

如此你就能够将你的改动推送到所添加的服务器上去了。

### 版本回退

- HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
- 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
- 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。


```
//Git允许我们在版本的历史之间穿梭
git reset --hard commit_id

//回退到上一个版本(HEAD指向的版本就是当前版本)
git reset -hard HEAD^ 

git reset -hard HEAD^^(上上一个版本)

//查看命令历史
git reflog 
```

```
// 撤销最近的一个提交.
git revert HEAD

// 取消 commit + add
git reset --mixed

// 取消 commit
git reset --soft
```

### 删除
```
//删除
git rm readme.md

//如果删错了，版本库里的版本替换工作区的版本
git checkout -- readme.md
```

### 分支

主分支（master分支）

```
//创建并切换
git checkout -b dev

//相当于
git branch dev //创建
git checkout dev //切换

git checkout master//切换到主分支

//将dev分支合并到master分支上
git merge dev （合并指定分支到当前分支）

//删除分支
git branch -d dev

//查看分支
git branch
```

#### Android Studio中合并分支操作

- 当前分支切换到主分支，然后进行合并
- VCS-> Git-> Merge Branches


### 参考

> https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

> https://github.com/francistao/LearningNotes/blob/master/Part1/Android/Git%E6%93%8D%E4%BD%9C.md

> https://git-scm.com/blog

> http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000
