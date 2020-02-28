# <p align = "center"> Git笔记 </p>
## Git介绍
- Git是分布式版本控制系统，Git的工作就是创建和保存你的项目的快照与之后的快照进行对比。

  ##### 什么是快照(snapshot)？

  **通俗的解释：**我们给一张桌子拍一张照片，纪录了桌子上所有物品的位置、状态，这样就可以称之为快照。 
  我们不必存储所有的物品，只需存储这个照片就可以了，下一次想恢复以前的状态的时候，只需要翻出当时的那张照片，再把物品按照那张照片里的位置摆放一下就OK了。           

  > In computer systems, a snapshot is a state a system at a particular point in time

  **《Git Pro》中英文原文如下：**

  > Every time you commit, or save the state of your project in Git, it basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot.
  >
  > 每次你提交或者要在git中保存项目的状态时，git仅仅是制作快照(像拍照一样记录所有文件在那个时刻的样子)，并保存指向这个快照的引用。

  因此在Git中，快照应理解为整个系统或者应用在某个时刻的状态记录。s实际上它就是一个备份，但这个备份不是像我们粘贴复制那么简单，git会处理，压缩，你可以使用这个快照恢复原来的状态。git会根据当前的内容生成一个校验和，是以此校验和为索引。每次提交，检测到校验和变化，就会生成一个新的快照，未更改的文件，则会链接到上一次的快照。这样就形成了一条链（这里先讨论没有其他分支的情况），git有一个HEAD指针，这个指针可以移动，这个指针移动到哪个快照，你就可以查看该快照也就是当时的状态。

- Github是用Git做版本控制的代码托管平台，类似的还有码云

- 集中式VS分布式，SVN VS Git
  1. SVN和Git主要的区别在于历史版本维护的位置
  2. Git本地仓库包含代码库还有历史库，在本地的环境开发就可以记录历史而SVN的历史库存在于中央仓库，每次对比与提交代码都必须连接到中央仓库才能进行。
  3. 这样的好处在于：
     - 自己可以在脱机环境查看开发的版本历史。

     - 多人开发时如果充当中央仓库的Git仓库挂了，可以随时创建一个新的中央仓库然后同步就立刻恢复了中央库。

## Git命令
### Git配置
```bash
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```
`git config`命令的`--global`参数，表明这台机器上的所有Git仓库都会使用这个配置，也可以对某个仓库指定不同的用户名和邮箱地址。

### 创建版本库
#### 初始化一个Git仓库
```bash
$ git init
```
在你的工作目录下启动bash，运行该命令

#### 添加文件到Git仓库

包括两步：
```bash
$ git add <file>
$ git commit -m "description"
```
`git add`提交到暂存区（也叫index索引区），告诉Git开始对这些文件进行跟踪，以备下次提交生成快照。可以反复多次使用，添加多个文件，

`git commit`可以一次提交很多文件，`-m`后面输入的是本次提交的说明，可以输入任意内容，不使用该参数会尝试打开编辑器以填写提交信息。

**从快照的角度**：当 `git commit` 命令执行时，默认情况下它只会检查暂存区域，因此 `git add` 是用来确定下一次提交时快照的样子的。`git commit`命令将所有通过 `git add` 暂存的文件内容在数据库中创建一个持久的快照，然后将当前分支上的分支指针移到其之上。

### 工作区、暂存区和版本库

**工作区**：在电脑里能看到的目录；
**版本库**：在工作区有一个隐藏目录`.git`，是Git的版本库。
**暂存区**：Git的版本库中存了很多东西，其中最重要的就是称为stage（或者称为index）的暂存区，还有Git自动创建的`master`（分支），以及指向`master`的指针`HEAD`。

![理解](https://cdn.liaoxuefeng.com/cdn/files/attachments/001384907720458e56751df1c474485b697575073c40ae9000/0)

进一步解释一些命令：

- `git add`实际上是把文件添加到暂存区
- `git commit`实际上是把暂存区的所有内容提交到当前分支

### 查看工作区状态
```bash
$ git status
```
-s参数   获取简短的输出

### 查看修改内容

```bash
$ git diff
```
```bash
$ git diff --cached
```
```bash
$ git diff HEAD -- <file>
```
- `git diff` 可以查看工作区(work dict)和暂存区(stage)的区别
- `git diff --cached` 可以查看暂存区(stage)和分支(master)的区别
- `git diff HEAD -- <file>` 可以查看工作区和版本库里面最新版本的区别
### 查看提交日志
```bash
$ git log
```
简化日志输出信息
```bash
$ git log --pretty=oneline
```
### 查看命令历史
```bash
$ git reflog
```
### 版本回退
```bash
$ git reset --hard HEAD^
```
以上命令是返回上一个版本，在Git中，用`HEAD`表示当前版本，上一个版本就是`HEAD^`，上上一个版本是`HEAD^^`，往上100个版本写成`HEAD~100`。
### 回退指定版本号
```bash
$ git reset --hard commit_id
```
commit_id是版本号，是一个用SHA1计算出的序列。如果不记得commit_id可以使用`git reflog`查找。

### 管理修改

为什么Git比其他版本控制系统设计得优秀，**因为Git跟踪并管理的是修改，而非文·件。**

那么，什么是修改？比如你新增了一行，这就是一个修改，删除了一行，也是一个修改，更改了某些字符，也是一个修改，删了一些又加了一些，也是一个修改，甚至创建一个新文件，也算一个修改。

### 撤销修改

#### 丢弃工作区的修改
```bash
$ git checkout -- <file>
```
该命令是指将文件在工作区的修改全部撤销，这里有两种情况：
1. 一种是file自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
2. 一种是file已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

总之，就是让这个文件回到最近一次git commit或git add时的状态。

#### 丢弃暂存区的修改
分两步：
第一步，把暂存区的修改撤销掉(unstage)，重新放回工作区：

```bash
$ git reset HEAD <file>
```
第二步，撤销工作区的修改
```bash
$ git checkout -- <file>
```
##### 丢弃版本库的修改

版本回退操作`$ git reset --hard commit_id`

**小结：**

1. 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- <file>`。
2. 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD <file>`，就回到了第一步，第二步按第一步操作。

3. 已经提交了不合适的修改到版本库时，想要撤销本次提交，进行版本回退，前提是没有推送到远程库。

### 删除文件

1、手动删除或者`rm filename`，不会将操作（删除其实也是修改）提交到暂存区

2、`$ git rm <file>`        相当于执行

```bash
$ rm <file>
$ git add <file>
```
3、真的想要从暂存区删除某个文件，可以使用

`$ git rm -f <file>-`强制删除

#### 进一步的解释

Q：比如执行了`rm text.txt` 误删了怎么恢复？
A：执行`git checkout -- text.txt` 把版本库的东西重新写回工作区就行了，前提是之前提交过该文件。

Q：如果执行了`git rm text.txt`我们会发现工作区的text.txt也删除了，怎么恢复？
A：先撤销暂存区修改，重新放回工作区，然后再从版本库写回到工作区

```bash
$ git reset head text.txt
$ git checkout -- text.txt
```
Q：如果真的想从版本库里面删除文件怎么做？
A：执行`git commit -m "delete text.txt"`，提交后最新的版本库将不包含这个文件

### 移动或者重命名文件

`$ git mv`

### 远程仓库

#### 创建SSH Key
```bash
$ ssh-keygen -t rsa -C "youremail@example.com"
```
> ssh是Secure Shell（安全外壳协议）是较可靠，专为[远程登录](https://baike.baidu.com/item/%E8%BF%9C%E7%A8%8B%E7%99%BB%E5%BD%95/1071998)会话和其他网络服务提供安全性的协议。

#### 关联远程仓库

**两种方法：**

1. `$ git remote add origin https://github.com/username/repositoryname.git`

   添加后，远程库的名称是origin，这是github的默认叫法，也可以改成其他名称，但是origin一看就知道是远程仓库

2. 在github上新建一个仓库，然后克隆到本地

   `$ git clone git@github.com:yourgithubname/learngit.git`

   注意：GitHub给出的地址不止一个，还可以用https://github.com/michaelliao/gitskills.git这样的地址。实际上，Git支持多种协议，默认的git://使用ssh，但也可以使用https等其他协议。

   使用https除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用ssh协议而只能用https。

#### 推送到远程仓库
```bash
$ git push -u origin master
```
`-u` 表示第一次推送master分支的所有内容，此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改。

### 分支

使用分支意味着你可以从开发主线上分离开来，然后在不影响主线的同时继续工作。在git中，每次提交都被串成一条线，这个时间线就是一个分支。而master就是一个主分支。这里以主分支为例，HEAD严格上来说是指向当前主分支（master）的，master才是指向提交的。

#### 创建分支
```bash
$ git branch <branchname>
```
#### 查看分支
```bash
$ git branch
```
`git branch`命令会列出所有分支，当前分支前面会标一个*号。

#### 切换分支
```bash
$ git checkout <branchname>
```

为了与前面的撤销修改的命令区分，新版本的git创建并切换到新的dev分支，可以使用：git switch master  切换分支，Git 2.23才有的新特性

​	`$ git switch -c dev`

#### 创建+切换分支

```bash
$ git checkout -b <branchname>
```

#### 合并某分支到当前分支
```bash
$ git merge <branchname>
```

#### 删除分支
```bash
$ git branch -d <branchname>      
出现error：the branch "xxx" is not fully merged的报错信息
意思是xxx分支有/没有合并到当前分支的内容，解决方法就是使用大写的D强制删除。

```
#### 查看分支合并图
```bash
$ git log --graph
```
当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。用`git log --graph`命令可以看到分支合并图。

#### 分支管理策略

 通常情况下，Git合并默认是Fast forward模式，但这种模式删除分支后，会丢失分支信息

> 举例来说，开发一直在master分支进行，但忽然有一个新的想法，于是新建了一个dev的分支，并在其上进行一系列提交，完成时，回到master分支，此时，master分支在创建dev分支之后并未产生任何新的commit。此时的合并就叫`fast forward`。
>
> 两种合并模式的对比：
>
> ![img](https://img-blog.csdnimg.cn/20190514203355476.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2R0YTA1MDI=,size_16,color_FFFFFF,t_70)

如果要强制禁用Fast forward模式。Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

#### 普通模式合并分支
```bash
$ git merge --no-ff -m "description" <branchname>
```
因为本次合并要创建一个新的commit，所以加上`-m`参数，把commit描述写进去。合并分支时，加上`--no-ff`参数就可以用普通模式合并，能看出来曾经做过合并，包含作者和时间戳等信息，而fast forward合并就看不出来曾经做过合并。

### 工作现场的应用场景

每一个bug都可以在一个临时分支上来修复。

 当你在一个分支dev上的工作进行到一半时，接到一个bug修复任务。但是，由于dev工作还没有完成，无法进行提交。这时候git提供了 stash功能，把当前工作现场储藏起来，等以后恢复现场之后工作。

即此时git  status查看工作区是干净的。

然后修复bug的时候，先确定是在哪个分支修复。如果是在master分支，就先切换到master，然后创建一个issue-101的分支进行修复。

修复完成后，切换到master分支，完成合并，最后删除issue-101分支，然后再回到原来的工作现场工作。

#### 保存工作现场

```bash
$ git stash
```
#### 查看工作现场
```bash
$ git stash list
```
#### 恢复工作现场

有两种方法：

1. 用`git stash apply`恢复，但是恢复后，stash内容并不删除，你需要用`git stash drop`来删除；
2. 使用`git stash pop`，恢复的同时把stash内容也删了；

当然你可以多次stash，恢复的时候，先用git stash list查看，然后恢复指定的stash，用命令：

`$ git stash apply stash@{0}`

 在master分支修改了bug后，由于dev是早期master分出来的，那么需要在dev分支上修改同样的bug。笨一点的方法就是重复操作一次，提交。

但是git提供了一个`cherry-pick <commit id>`命令，让我们能复制一个特定的提交到当前分支。

#### 丢弃一个没有合并过的分支
```bash
$ git branch -D <branchname>
```

#### 查看远程库信息
```bash
$ git remote -v
```

> $ git remote -v
>  origin  git@github.com:michaelliao/learngit.git (fetch)
>  origin  git@github.com:michaelliao/learngit.git (push)

上面显示了可以抓取和推送的origin的地址。如果没有推送权限，就看不到push的地址。

#### 在本地创建和远程分支对应的分支

```bash
$ git checkout -b branch-name origin/branch-name，
```
本地和远程分支的名称最好一致；

#### 建立本地分支和远程分支的关联
```bash
$ git branch --set-upstream branch-name origin/branch-name；
```
#### 从本地推送分支
```bash
$ git push origin branch-name
```
如果推送失败（说明远程分支比你的本地分支更新），先用git pull抓取远程的新提交；
#### 从远程抓取分支
```bash
$ git pull
```
如果git pull提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，则先创建关联，再抓取远程分支，然后在本地进行合并，解决冲突，再推送。

### 标签管理

发布一个版本时，我们通常先在版本库中打一个标签（tag），这样，就唯一确定了打标签时刻的版本。将来无论什么时候，取某个标签的版本，就是把那个打标签的时刻的历史版本取出来。所以，标签也是版本库的一个快照。

Git的标签虽然是版本库的快照，但其实它就是指向某个commit的指针（跟分支很像对不对？但是分支可以移动，标签不能移动），所以，创建和删除标签都是瞬间完成的。

tag就是一个让人容易记住的有意义的名字，它跟某个commit绑在一起。
#### 新建一个标签
```bash
$ git tag <tagname>
```
命令`git tag <tagname>`用于在当前分支新建一个标签，默认为HEAD，也可以指定一个commit id。

`git log --pretty-oneline --abbrev-commit`      //查找历史commit id

#### 指定标签信息
```bash
$ git tag -a <tagname> -m <description> <branchname> or commit_id
```
`git tag -a <tagname> -m "blablabla..."`可以指定标签信息。
#### PGP签名标签
```bash
$ git tag -s <tagname> -m <description> <branchname> or commit_id
```
`git tag -s <tagname> -m "blablabla..."`可以用PGP签名标签。
#### 创建带说明的标签

 `git show -a  <name>  -m "message" <commit id>`

用 -a 制定标签， -m 指定说明文字

#### 查看标签信息

注意，标签不是按时间顺序列出，而是按字母排序的。

可以用`git show <tagname>`查看标签信息。

#### 查看所有标签

```bash
$ git tag
```
#### 推送一个本地标签
```bash
$ git push origin <tagname>
```
#### 推送全部未推送过的本地标签
```bash
$ git push origin --tags
```
#### 删除一个本地标签
```bash
$ git tag -d <tagname>
```
#### 删除一个远程标签
```bash
$ git push origin :refs/tags/<tagname>
```
