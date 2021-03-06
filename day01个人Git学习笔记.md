## **Git的安装及环境配置**

### **Git的安装**

#### **软件下载**

打开 [git官网] https://git-scm.com/，下载git对应操作系统的版本。

所有东西下载慢的话就可以去找镜像！

官网下载太慢，我们可以使用淘宝镜像下载：http://npm.taobao.org/mirrors/git-for-windows/

------

### **Git的使用**

#### **启动Git**

安装成功后在始菜单中会有Git项，菜单下有3个程序：任意文件夹下右键也可以看到对应的程序！![day01-01](https://github.com/MAYI-XINGKONG/JavaNotes/blob/master/images/day01-01.png?raw=true)

```
Git Bash：Unix与Linux风格的命令行，使用最多，推荐最多

Git CMD：Windows风格的命令行

Git GUI：图形界面的Git，不建议初学者使用，尽量先熟悉常用命令
```

------

#### **常用的Linux命令**

```
1）、cd : 改变目录。

2）、cd . . 回退到上一个目录，直接cd进入默认目录

3）、pwd : 显示当前所在的目录路径。

4）、ls(ll):  都是列出当前目录中的所有文件，只不过ll(两个ll)列出的内容更为详细。

5）、touch : 新建一个文件 如 touch index.js 就会在当前目录下新建一个index.js文件。

6）、rm:  删除一个文件, rm index.js 就会把index.js文件删除。

7）、mkdir:  新建一个目录,就是新建一个文件夹。

8）、rm -r :  删除一个文件夹, rm -r src 删除src目录

rm -rf / 切勿在Linux中尝试！删除电脑中全部文件！
9）、mv 移动文件, mv index.html src index.html 是我们要移动的文件, src 是目标文件夹,当然, 这样写,必须保证文件和目标文件夹在同一目录下。

10）、reset 重新初始化终端/清屏。

11）、clear 清屏。

12）、history 查看命令历史。

13）、help 帮助。

14）、exit 退出。

15）、#表示注释
```

------

### **Git的配置**

所有的配置文件，其实都保存在本地！

查看配置 git config -l![img](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p0GJANibs86DwYqoADdgZySGibmafR8p1XBq6ZG3t0J2wSg9icrIVVQo6dQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

查看不同级别的配置文件：

```java
#查看系统config
git config --system --list
　　
#查看当前用户（global）配置
git config --global  --list
```

#### **Git相关的配置文件**(gitconfig)

```
1）、Git\etc\gitconfig  ：Git 安装目录下的 gitconfig     --system 系统级

2）、C:\Users\Administrator\ .gitconfig    只适用于当前登录用户的配置  --global 全局
```

这里可以直接编辑配置文件，通过命令设置后会响应到这里。

------

#### **设置用户名与邮箱（用户标识，必要）**

当你安装Git后首先要做的事情是设置你的用户名称和e-mail地址。这是非常重要的，因为每次Git提交都会使用该信息。它被永远的嵌入到了你的提交中

```java
//第一种(全局设置)：
git config --global user.name "kuangshen"  #名称
git config --global user.email 24736743@qq.com   #邮箱
//第二种(单独设置)：建议
git config  user.name "kuangshen"  #名称
git config  user.email 24736743@qq.com   #邮箱
```

------

### *Git基本理论（重要）**

#### **三/四个区域**

Git本地有三个工作区域：工作目录（Working Directory）、暂存区(Stage/Index)、资源库(Repository或Git Directory)。如果在加上远程的git仓库(Remote Directory)就可以分为四个工作区域。文件在这四个区域之间的转换关系如下：![img](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p0NJ4L9OPI9ia1MmibpvDd6cSddBdvrlbdEtyEOrh4CKnWVibyfCHa3lzXw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

```
Workspace：工作区，就是你平时存放项目代码的地方

Index / Stage：暂存区，用于临时存放你的改动，事实上它只是一个文件，保存即将提交到文件列表信息

Repository：仓库区（或本地仓库），就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本。
(本地仓库实际上就是git init是所创建的.git)

Remote：远程仓库，托管代码的服务器，可以简单的认为是你项目组中的一台电脑用于远程数据交换。
(远程仓库实际上就是GitHub/码云等代码托管网站或者是一些托管代码的服务器)
```

本地的三个区域确切的说应该是git仓库中HEAD指向的版本：![img](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p0icz6X2aibIgUWzHxtwX8kicPCKpDrsiaPzZk04OlI2bzlydzicBuXTJvLEQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

```java
Directory：使用Git管理的一个目录，也就是一个仓库，包含我们的工作空间和Git的管理空间。

WorkSpace：需要通过Git进行版本控制的目录和文件，这些目录和文件组成了工作空间。

.git：存放Git管理信息的目录，初始化仓库的时候自动创建。

Index/Stage：暂存区，或者叫待提交更新区，在提交进入repo之前，我们可以把所有的更新放在暂存区。

Local Repo：本地仓库，一个存放在本地的版本库；HEAD会只是当前的开发分支（branch）。

Stash：隐藏，是一个工作状态保存栈，用于保存/恢复WorkSpace中的临时状态。
```

#### 工作流程

git的工作流程一般是这样的：

１、在工作目录中添加、修改文件；(鼠标键盘直接操作也可)

２、将需要进行版本管理的文件放入暂存区域；

３、将暂存区域的文件提交到git仓库。

因此，git管理的文件有三种状态：已修改（modified）,已暂存（staged）,已提交(committed)![img](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p09iaOhl0dACfLrMwNbDzucGQ30s3HnsiaczfcR6dC9OehicuwibKuHjRlzg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

### Git项目搭建

#### 创建工作目录与常用指令

工作目录（WorkSpace)一般就是你希望Git帮助你管理的文件夹，可以是你项目的目录，也可以是一个空目录，建议不要有中文。

日常使用只要记住下图6个命令：![img](https://mmbiz.qpic.cn/mmbiz_png/uJDAUKrGC7Ksu8UlITwMlbX3kMGtZ9p0AII6YVooUzibpibzJnoOHHXUsL3f9DqA4horUibfcpEZ88Oyf2gQQNR6w/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

#### 本地仓库搭建

创建本地仓库的方法有两种：一种是创建全新的仓库，另一种是克隆远程仓库。

1、创建全新的仓库，需要用GIT管理的项目的根目录执行：

```java
# 在当前目录新建一个Git代码库
$ git init
```

2、执行后可以看到，仅仅在项目目录多出了一个.git目录，关于版本等的所有信息都在这个目录里面。

#### 克隆远程仓库

1、另一种方式是克隆远程目录，由于是将远程服务器上的仓库完全镜像一份至本地！

```java
# 在GitHub、Gitee或者码云等网站项目页面上克隆一个项目和它的整个代码历史(版本信息)
$ git clone [url]  
		# https://gitee.com/kuangstudy/openclass.git
```

2、去 gitee 或者 github 上克隆一个测试！

### **Git文件操作**

#### **文件的四种状态**

版本控制就是对文件的版本控制，要对文件进行修改、提交等操作，首先要知道文件当前在什么状态，不然可能会提交了现在还不想提交的文件，或者要提交的文件没提交上。

```java
Untracked: 未跟踪, 此文件在文件夹中, 但并没有加入到git库, 不参与版本控制. 通过git add 状态变为Staged.

Unmodify: 文件已经入库, 未修改, 即版本库中的文件快照内容与文件夹中完全一致. 这种类型的文件有两种去处, 如果它被修改, 而变为Modified. 如果使用git rm移出版本库, 则成为Untracked文件

Modified: 文件已修改, 仅仅是修改, 并没有进行其他的操作. 这个文件也有两个去处, 通过git add可进入暂存staged状态, 使用git checkout 则丢弃修改过, 返回到unmodify状态, 这个git checkout即从库中取出文件, 覆盖当前修改 !

Staged: 暂存状态. 执行git commit则将修改同步到库中, 这时库中的文件和本地文件又变为一致, 文件为Unmodify状态. 执行git reset HEAD filename取消暂存, 文件状态为Modified
```

#### 查看文件状态

上面说文件有4种状态，通过如下命令可以查看到文件的状态：

```java
#查看指定文件状态
git status [filename]

#查看所有文件状态
git status

# git add .                  添加所有文件到暂存区
# git commit -m "消息内容"    提交暂存区中的内容到本地仓库 -m 提交信息
```

#### 忽略文件

有些时候我们不想把某些文件纳入版本控制中，比如数据库文件，临时文件，设计文件等

在主目录下建立".gitignore"文件，此文件有如下规则：

```java
1、忽略文件中的空行或以井号（#）开始的行将会被忽略。

2、可以使用Linux通配符。例如：星号（*）代表任意多个字符，问号（？）代表一个字符，方括号（[abc]）代表可选字符范围，大括号（{string1,string2,...}）代表可选的字符串等。

3、如果名称的最前面有一个感叹号（!），表示例外规则，将不被忽略。

4、如果名称的最前面是一个路径分隔符（/），表示要忽略的文件在此目录下，而子目录中的文件不忽略。

5、如果名称的最后面是一个路径分隔符（/），表示要忽略的是此目录下该名称的子目录，而非文件（默认文件或目录都忽略）。
```

```java
#为注释
*.txt        #忽略所有 .txt结尾的文件,这样的话上传就不会被选中！
!lib.txt     #但lib.txt除外
/temp        #仅忽略项目根目录下的TODO文件,不包括其它目录temp
build/       #忽略build/目录下的所有文件
doc/*.txt    #会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
```

### 使用GitHub/码云...（[Git 本地项目上传至托管平台（OsChina/GitHub）](https://www.cnblogs.com/ut2016-progam/p/6066834.html)）

#### 方法

##### 方法一：本地创建项目根目录(本地仓库)，然后与远程GitHub仓库关联！

1、新建仓库(随便命名，假如仓库名字:origin)，得到远程仓库的URL

2、初始化Git仓库

```
git init ;//新建一个本地仓库
```

3、添加文件

```
git add ./*;//将目录中所有文件添加
```

4、提交改变到缓存

```
git commit -m "提示信息"
```

5、本地git仓库关联Git仓库

```
git remote add origin URL;//添加远程仓库，origin只是一个远程仓库的别名，可以随意取
```

6、提交到Git仓库前先更新远程仓库内容到本地(等同于‘’二.5‘’)

```
git pull origin master;//防止远程仓库，有更新而产生冲突
```

7、提交到Git中(等同于‘’二.6‘’)

```java
git push -u origin master;//将本地仓库push到远程仓库，并将origin设为默认仓库

//该命令加上-u和不加的区别等问题:
	//$ git push origin
		上面命令表示，将当前分支推送到origin主机的对应分支。 
		如果当前分支只有一个追踪分支，那么主机名都可以省略。 
	//$ git push 
		如果当前分支与多个主机存在追踪关系，那么这个时候-u选项会指定一个默认主机，这样后面就可以不加任何参数使用git push。
	//$ git push -u origin master 
		上面命令将本地的master分支推送到origin主机，同时指定origin为默认主机，后面就可以不加任何参数使用git push了。不带任何参数的git push，默认只推送当前分支，这叫做simple方式。此外，还有一种matching方式，会推送所有有对应的远程分支的本地分支。Git 2.0版本之前，默认采用matching方法，现在改为默认采用simple方式。
```

##### 方法二：不用关联远程仓库，直接git仓库拉源码至本地！

1、从Git仓库拉项目到本地

```
//注意克隆的时候，直接在仓库根目录即可，不用再创建项目根目录；拉下来的项目会自动生成，git文件，表明是个git仓库，不用git init来初始化
git clone URL(这个是被克隆的项目的URL);
```

2、添加文件

```
git add ./*;将目录所有文件添加
```

3、提交缓存

```
git commit -m "提示信息"
```

4、合并master

```
git merge master
```

5、与GitHub远程仓库同步

```
git pull 远程仓库地址
```

6、提交到远程GitHub仓库

```
git push 远程仓库地址 master
```

##### 方法三：用Git Gui图形化界面操作！

此方法略.....

详细内容可以点击[Git 本地项目上传至托管平台（OsChina/GitHub）](https://www.cnblogs.com/ut2016-progam/p/6066834.html)此链接或本文件的图片

#### 之后的修改提交

1、与GitHub远程仓库同步

```
git pull ...
```

2、查看文件变更

```
git status [可以加上指定的文件名字]
```

3、提交代码到本地缓存

```
git commit -m "提示信息"
```

4、提交代码到远程GitHub仓库

```
git push ...
```

#### 可能产生的错误

###### git pull报错：

![img](https://images2015.cnblogs.com/blog/909970/201611/909970-20161115183753763-706780701.png)

```
错误可能是因为在你以前pull下来的代码没有自动合并导致的.
保留你本地的修改  git merge --abort   git reset --merge
合并后记得一定要提交这个本地的合并，然后在获取线上仓库！再git pull！
```

###### git add --all报错：

![img](https://images2015.cnblogs.com/blog/909970/201611/909970-20161115183754045-237706126.png)

```
原因分析：
在windows中的换行符为 CRLF， 而在linux下的换行符为：LF
使用git来生成工程后，文件中的换行符为LF， 当执行git add .时，系统提示：LF 将被转换成 CRLF
解决方法： 
删除刚刚生成的.git文件
 rm -rf .git  
  git config --global core.autocrlf false  
这样系统就不会去进行换行符的转换了
最后重新执行
Git init 再 git add --all
就按正常步骤操作！
如 git push 报 : error:src refspec master does not match any
原因分析
引起该错误的原因是，目录中没有文件，空目录是不能提交上去的
解决方法
touch READMEgit add README git commit -m 'first commit'git push origin master
```

### 简易命令行入门教程

![img](https://github.com/MAYI-XINGKONG/JavaNotes/blob/master/images/day01-09.png?raw=true)

### IDEA集成Git

#### 

