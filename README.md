# git简单教程及原理

## 一：Git是什么？
Git是目前世界上最先进的分布式版本控制系统。

工作原理 / 流程：
![如图](https://img2018.cnblogs.com/blog/1588197/201901/1588197-20190129144117651-860073754.png)
- Workspace：工作区，就是你平时存放项目代码的地方

- Index / Stage：暂存区，用于临时存放你的改动，事实上它只是一个文件，保存即将提交到文件列表信息

- Repository：仓库区（或本地仓库），就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本

- Remote：远程仓库，托管代码的服务器，可以简单的认为是你项目组中的一台电脑用于远程数据交换
## 二、在windows上如何安装Git？
git的工作流程一般是这样的：

在[官网](https://git-scm.com/download/win)下载 git-2.20.1-64-bit.exe

安装完成后，还需要最后一步设置，在命令行输入如下：

git config --global user.name "YOUR NAME"

git config --global user.email "YOUR EMAIL"

因为Git是分布式版本控制系统，所以需要填写用户名和邮箱作为一个标识。

## 三：如何操作？

##### 1.创建版本库

什么是版本库？版本库又名仓库，英文名repository,你可以简单的理解一个目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改，删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻还可以将文件”还原”。

所以创建一个版本库也非常简单，如下我是D盘 –> repo下 目录下新建一个testgit版本库。

想看readme.txt文件到底改了什么内容，如何查看呢？可以使用命令：git diff readme.txt 

##### 2.理解工作区与暂存区的区别

工作区：就是你在电脑上看到的目录，比如目录下testgit里的文件(.git隐藏目录版本库除外)。或者以后需要再新建的目录文件等等都属于工作区范畴。
版本库(Repository)：工作区有一个隐藏目录.git,这个不属于工作区，这是版本库。其中版本库里面存了很多东西，其中最重要的就是stage(暂存区)，还有Git为我们自动创建了第一个分支master,以及指向master的一个指针HEAD。

我们前面说过使用Git提交文件到版本库有两步：

第一步：是使用 git add 把文件添加进去，实际上就是把文件添加到暂存区。

第二步：使用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支上。

## 四：Git撤销修改和删除文件操作

##### 1.撤销修改

第一：如果我知道要删掉那些内容的话，直接手动更改去掉那些需要的文件，然后add添加到暂存区，最后commit掉。

第二：我可以按以前的方法直接恢复到上一个版本。使用 git reset --hard HEAD^

##### 2.删除文件

在版本库testgit目录添加一个文件b.txt,然后提交。一般情况下，可以直接在文件目录中把文件删了，或者使用如上rm命令：rm b.txt 

如果我想彻底从版本库中删掉了此文件的话，可以再执行commit命令 提交掉。

只要没有commit之前，如果我想在版本库中恢复此文件如何操作呢？

可以使用如下命令 git checkout -- b.txt

## 五：Git撤销修改和删除文件操作

第一步：创建SSH KEY。

第二步：登录github,打开” settings”中的SSH Keys页面，然后点击“Add SSH Key”,填上任意title，在Key文本框里黏贴id_rsa.pub文件的内容。
点击 Add Key，你就应该可以看到已经添加的key。

如何添加远程库？

首先，登录github上，然后在右上角找到“create a new repo”创建一个新的仓库。

 在Repository name填入testgit，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库。
 
 现在，我们根据GitHub的提示，在本地的testgit仓库下运行命令：

$ git remote add origin https://github.com/jjleee/gittest.git

把本地库的内容推送到远程，使用 git push -u origin master命令，实际上是把当前分支master推送到远程。

由于远程库是空的，我们第一次推送master分支时，加上了 –u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。


[我的GitHub项目地址](https://github.com/0uroboro5/xiangmu)
