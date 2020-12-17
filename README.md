# git工作原理
<a><font size='4'>*Git本地有三个工作区域：工作目录（Working Directory）、暂存区(Stage/Index)、资源库(Repository或Git Directory)。如果在加上远程的git仓库(Remote Directory)就可以分为四个工作区域。文件在这四个区域之间的转换关系如下：*</font></a>
![如图](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p0NJ4L9OPI9ia1MmibpvDd6cSddBdvrlbdEtyEOrh4CKnWVibyfCHa3lzXw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
- Workspace：工作区，就是你平时存放项目代码的地方

- Index / Stage：暂存区，用于临时存放你的改动，事实上它只是一个文件，保存即将提交到文件列表信息

- Repository：仓库区（或本地仓库），就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本

- Remote：远程仓库，托管代码的服务器，可以简单的认为是你项目组中的一台电脑用于远程数据交换
## 工作流程
git的工作流程一般是这样的：

1. 在工作目录中添加、修改文件；

2. 将需要进行版本管理的文件放入暂存区域；

3. 将暂存区域的文件提交到git仓库。

因此，git管理的文件有三种状态：已修改（modified）,已暂存（staged）,已提交(committed)
![](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p09iaOhl0dACfLrMwNbDzucGQ30s3HnsiaczfcR6dC9OehicuwibKuHjRlzg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

## 创建工作目录与常用指令
工作目录（WorkSpace)一般就是你希望Git帮助你管理的文件夹，可以是你项目的目录，也可以是一个空目录，建议不要有中文。

日常使用只要记住下图6个命令：
![](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p0AII6YVooUzibpibzJnoOHHXUsL3f9DqA4horUibfcpEZ88Oyf2gQQNR6w/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

<font size='5' color=‘blue’>本地仓库搭建</font>

创建本地仓库的方法有两种：一种是创建全新的仓库，另一种是克隆远程仓库。

##### 1、创建全新的仓库，需要用GIT管理的项目的根目录执行：

>在当前目录新建一个Git代码库  
$ git init

##### 2、执行后可以看到，仅仅在项目目录多出了一个.git目录，关于版本等的所有信息都在这个目录里面。

<font size='5' color=‘blue’>克隆远程仓库</font>

1、另一种方式是克隆远程目录，由于是将远程服务器上的仓库完全镜像一份至本地！

>克隆一个项目和它的整个代码历史(版本信息)
$ git clone [url]

2、去 gitee 或者 github 上克隆一个测试！

# <font size='15'>linus下的git命令
## <a><font size='6' color='black'> 1）cd : 改变目录。
## <font size='6'> 2）cd.. 回退到上一个目录，直接cd进入默认目录
## <font size='6'> 3）pwd:显示当前所在的目录路径。
## <font size='6'> 4）ls(ll):  都是列出当前目录中的所有文件，只不过ll(两个ll)列出的内容更为详细。
## <font size='6'> 5）touch : 新建一个文件 如 touch index.js 就会在当前目录下新建一个index.js文件。
## <font size='6'> 6)rm:  删除一个文件, rm index.js 就会把index.js文件删除。
## <font size='6'> 7）mkdir:  新建一个目录,就是新建一个文件夹。
## <font size='6'> 8）rm -r :  删除一个文件夹, rm -r src 删除src目录

<a href="https://github.com/hao3145/hao">项目提交的github地址</a>
