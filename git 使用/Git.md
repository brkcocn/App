## 1. Git基础

### 1.1 版本管理

#### 1.1.1 什么是版本管理

版本管理是一种记录文件变化的方式，以便将来查阅特定版本的文件内容。

![](assets/01.png)

#### 1.1.2 人为维护文档版本的问题

1. 文档数量多且命名不清晰导致文档版本混乱

2. 每次编辑文档需要复制，不方便

3. 多人同时编辑同一个文档，容易产生覆盖




![](assets/04.png)



### 1.2 Git 是什么

Git是一个版本管理控制系统（缩写VCS），它可以在任何时间点，将文档的状态作为更新记录保存起来，也可以在任何时间点，将更新记录恢复回来。



![](assets/19.png)

### 1.3 Git 安装

[下载地址](https://git-scm.com/downloads) 

在安装的过程中，所有选项使用默认值即可。



### 1.4 Git 基本工作流程

| git仓库          | 暂存区             | 工作目录            |
| ---------------- | ------------------ | ------------------- |
| 用于存放提交记录 | 临时存放被修改文件 | 被Git管理的项目目录 |

![](assets/05.png)

### 1.5 Git 的使用

#### 1.5.1 Git 使用前配置

在使用 git 前，需要告诉 git 你是谁，在向 git 仓库中提交时需要用到。

1. 配置提交人姓名：`git config --global user.name 提交人姓名`
2. 配置提交人姓名：`git config --global user.email 提交人邮箱` 
3. 查看git配置信息：`git config --list`   

**注意**

1. 如果要对配置信息进行修改，重复上述命令即可。

2. 配置只需要执行一次。

#### 1.5.2 提交步骤

1. `git init` 初始化git仓库
2. `git status` 查看文件状态
3. `git add 文件列表` 追踪文件
4. `git commit -m 提交信息`  向仓库中提交代码
5. `git log` 查看提交记录

#### 1.5.3 撤销

- 用暂存区中的文件覆盖工作目录中的文件： `git checkout 文件`

- 将文件从暂存区中删除： `git rm --cached 文件`
- 将 git 仓库中指定的更新记录恢复出来，并且覆盖暂存区和工作目录：`git rest --hard commitID` 

![](assets/07.png)



## 2. Git分支

### 2.1 分支

为了便于理解，大家暂时可以认为分支就是当前工作目录中代码的一份副本。

使用分支，可以让我们从开发主线上分离出来，以免影响开发主线。

![](assets/08.png)



#### 2.1.1 分支细分

1. 主分支（master）：第一次向 git 仓库中提交更新记录时自动产生的一个分支。

   

   ![](assets/06.png)

   

2. 、开发分支（develop）：作为开发的分支，基于 master 分支创建。

   

   ![](assets/09.png)

3. 功能分支（feature）：作为开发具体功能的分支，基于开发分支创建

   

   ![](assets/10.png)

**功能分支 -> 开发分支 -> 主分支**

#### 2.1.2 分支命令

- `git branch` 查看分支

- `git branch 分支名称` 创建分支

- `git swich 分支名称` 切换分支

- `git merge 来源分支` 合并分支

- `git branch -d 分支名称` 删除分支（分支被合并后才允许删除）（-D 强制删除）


### 2.2 暂时保存更改

在git中，可以暂时提取分支上所有的改动并存储，让开发人员得到一个干净的工作副本，临时转向其他工作。

使用场景：分支临时切换

- 存储临时改动：`git stash`
- 恢复改动：`git stash pop`

## 3. Github

在版本控制系统中，大约90%的操作都是在本地仓库中进行的：暂存，提交，查看状态或者历史记录等等。除此之外，如果仅仅只有你一个人在这个项目里工作，你永远没有机会需要设置一个远程仓库。

只有当你需要和你的开发团队共享数据时，设置一个远程仓库才有意义。你可以把它想象成一个 “文件管理服务器”，利用这个服务器可以与开发团队的其他成员进行数据交换。

### 3.1 注册

### 3.2 多人协作开发流程

- A在自己的计算机中创建本地仓库
- A在github中创建远程仓库
- A将本地仓库推送到远程仓库
- B克隆远程仓库到本地进行开发
- B将本地仓库中开发的内容推送到远程仓库
- A将远程仓库中的最新内容拉去到本地

![](assets/20.png)



![](assets/21.png)

### 3.3 创建仓库

1. 填写仓库基本信息

   ![](assets/17.png)

2. 将本地仓库推送到远程仓库

   ![](assets/18.png)

   1. git push 远程仓库地址 分支名称

   2. git remote add 远程仓库地址别名 远程仓库地址

   3. git push 远程仓库地址别名 分支名称

   4. git push -u 远程仓库地址别名 分支名称

       -u 记住推送地址及分支，下次推送只需要输入git push即可
   
       git remote add origin_ssh git@github.com:Brk-cocoon/App.git

### 3.4 拉取操作

#### 3.4.1 克隆仓库

克隆远端数据仓库到本地：`git clone 仓库地址`

#### 3.4.2 拉取远程仓库中最新的版本

拉取远程仓库中最新的版本：`git pull 远程仓库地址 分支名称`

### 3.5 解决冲突

在多人同时开发一个项目时，如果两个人修改了同一个文件的同一个地方，就会发生冲突。冲突需要人为解决。

### 3.6 跨团队协作

1. 程序员 C fork仓库
2. 程序员 C 将仓库克隆在本地进行修改
3. 程序员 C 将仓库推送到远程
4. 程序员 C 发起pull reqest
5. 原仓库作者审核
6. 原仓库作者合并代码

### 3.7 ssh免登陆



![](assets/22.png)

生成秘钥：`ssh-keygen`

```ssh-keygen -t rsa```

秘钥存储目录：C:\Users\用户\\.ssh

公钥名称：id_rsa.pub

私钥名称：id_rsa

![](assets/23.png)

![](assets/24.png)

### 3.8 GIT忽略清单

将不需要被git管理的文件名字添加到此文件中，在执行git命令的时候，git就会忽略这些文件。

git忽略清单文件名称：**.gitignore**

将工作目录中的文件全部添加到暂存区：`git add .`





### git_bash

![image-20210811092132724](C:\Users\Eason\AppData\Roaming\Typora\typora-user-images\image-20210811092132724.png)

## 3.Git 进阶

###  1.alias

git config --global alias.co checkout       **checkout别名co**

git config --global alias.psm 'push origin master'      **push origin master别名psm**

git config --global alias.a     add .

### 2.diff

git dif 比较暂存区和工作区的差别

git diff --staged  比较暂存区和版本库差异

git diff <\$id1>  <$id2> # 比较两次提交之间的差异 

git diff \<branch1>  \<branch2>在两个分支之间比较 

### 3.checkout

1.切换分支==switch

2.切换tag

3.还原 暂存区或版本库文件到工作目录==restore

### 4.tag

静态记录每次commit

git tag

git tag  \<tag name>

git checkout  \<tagname>



#### 一、删除文件

如果需要删除的 commit 是一个或多个文件，可以进行以下操作。

1. 被提交到仓库的某个文件需要删除，可以使用 `git rm` 命令：



```cpp
1. git rm <file> // 从工作区和暂存区删除某个文件
2. git commit -m "" // 再次提交到仓库
```

1. 如果只想从暂存区删除文件，本地工作区不做出改变，可以：



```xml
1. git rm --cached <file>
```

1. 如果在工作区不小心删错了某个文件，可以用 `git checkout` 将暂存区的文件覆盖工作区的文件，从而把误删的文件恢复：



```jsx
1. git checkout -- <file>
```

1. 用 `git rm` 删除文件，同时还会将这个删除操作记录下来；
    用 `rm` 删除文件，删除的仅仅是本地物理文件，没有将其从 git 的记录中剔除。
2. `git add` 和 `git rm` 有相似的功能，
    但 `git add` 仅能记录添加、改动的动作，删除的动作需靠 `git rm` 来完成。

#### 二、GitHub 删除某次 commit

如果需要删除的不只是某个文件，而是交错的代码，那么有以下三种方法可以删除 commit 。

##### 1. git reset

- `git reset` ：回滚到某次提交。
- `git reset --soft`：此次提交之后的修改会被退回到暂存区。
- `git reset --hard`：此次提交之后的修改不做任何保留，`git status` 查看工作区是没有记录的。

1. 回滚代码
    如果需要删除的 commit 是最新的，那么可以通过 `git reset` 命令将代码回滚到之前某次提交的状态，但一定要将现有的代码做好备份，否则回滚之后这些变动都会消失。具体操作如下：



```cpp
1. git log // 查询要回滚的 commit_id
2. git reset --hard commit_id // HEAD 就会指向此次的提交记录
3. git push origin HEAD --force // 强制推送到远端
```

1. 误删恢复
    如果回滚代码之后发现复制错了 commit_id，或者误删了某次 commit 记录，也可以通过下方代码恢复：



```bash
1. git relog // 复制要恢复操作的前面的 hash 值
2. git reset --hard hash // 将 hash 换成要恢复的历史记录的 hash 值
```

1. 注意：删除中间某次提交时最好不要用 `git reset` 回退远程库，因为之后其他人提交代码时用 `git pull` 也会把自己的本地仓库回退到之前的版本，容易出现差错进而增加不必要的工作量。

##### 2. git rebase

- `git rebase`：当两个分支不在一条线上，需要执行 merge 操作时使用该命令。

1. 撤销提交
    如果中间的某次 commit 需要删除，可以通过 `git rebase` 命令实现，方法如下：



```go
1. git log // 查找要删除的前一次提交的 commit_id
2. git rebase -i commit_id // 将 commit_id 替换成复制的值
3. 进入 Vim 编辑模式，将要删除的 commit 前面的 `pick` 改成 `drop`
4. 保存并退出 Vim
```

这样就完成了。

1. 解决冲突
    该命令执行时极有可能出现 reabase 冲突，可以通过以下方法解决：



```csharp
1. git diff // 查看冲突内容
2. // 手动解决冲突（冲突位置已在文件中标明）
3. git add <file> 或 git add -A // 添加
4. git rebase --continue // 继续 rebase
5. // 若还在 rebase 状态，则重复 2、3、4，直至 rebase 完成出现 applying 字样
6. git push
```

##### 3. git revert

- `git revert`：放弃某次提交。
   `git revert` 之前的提交仍会保留在 git log 中，而此次撤销会做为一次新的提交。
- `git revert -m`：用于对 merge 节点的操作，-m 指定具体某个提交点。

1. 撤销提交
    要撤销中间某次提交时，使用 `git revert` 也是一个很好的选择：



```cpp
1. git log // 查找需要撤销的 commit_id
2. git revert commit_id  // 撤销这次提交
```

1. 撤销 merge 节点提交
    如果这次提交是 merge 节点的话，则需要加上 `-m` 指令：



```csharp
1. git revert commit_id -m 1 // 第一个提交点
2. // 手动解决冲突
3. git add -A
4. git commit -m ""
5. git revert commit_id -m 2 // 第二个提交点
6. // 重复 2，3，4
7. git push
```

