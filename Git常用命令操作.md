#### Git常用的命令参考图如下：
![Git命令参考图](https://img-blog.csdnimg.cn/20200214165926425.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0hlaV8xOTkz,size_16,color_FFFFFF,t_70)

#### 常用命令清单如下：
##### 1. 拉取远程分支
```bash
$ git clone [url]
```

##### 2.配置
```bash
# 显示当前的Git配置
$ git config --edit [--global]

# 设置提交代码的用户信息
$ git config [--global] user.name [username]
$ git config [--global] user.email [email address]
```
##### 3.分支

```bash
# 列出本地的所有分支
$ git branch
# 列出远程的所有分支
$ git branch -r
# 新建本地分支
# 未指定base-branch，会根据当前所在的分支建立分支；指定base-branch(可以是远程分支，origin/remote-branch)，会从远程分支拉取代码
$ git branch [branch] [base-branch]
# 将新建的本地分支推送到远程仓库上
$ git push [主机] [remote-branch]
# 切换本地分支
$ git checkout [branch]
# 新建本地分支并切换到新建的分支上
$ git checkout -b [branch]
# 删除本地分支
$ git branch -D [branch]
# 删除远程分支
$ git push --delete [主机] [remote-branch]
# 本地分支重命名
$ git branch --move [old-branch] [new-branch]
# 远程分支重命名(先删除远程分支，再将本地重命名后的分支推送上去)
$ git push [主机] --delete [old-remote-branch]
$ git push [主机] [new-branch]
# 本地分支追踪远程分支
$ git branch --set-upstream-to [主机]/[remote-branch]
# 合并指定分支到当前分支
$ git merge [branch]
```
##### 4.暂存文件

```bash
# 添加文件到暂存区
$ git add [file]
# 添加目录到暂存区(包括子文件夹)
$ git add [dir]
# 取消已暂存的文件
$ git reset HEAD [file]
```
##### 5.代码改动变化

```bash
# 查看尚未缓存的改动(没有进行git add操作)
$ git diff
# 查看已经缓存的改动
$ git diff --cached
```
##### 6.代码提交
```bash
# 提交暂存区的所有文件到本地仓库
$ git commit -m [message]
# 提交暂存区的指定文件到本地仓库
$ git commit [file1][file2] -m [message]
# 修改提交信息
$ git commit --amend(然后vi/vim) 或 
$ git commit --amend -m [message]
```
##### 7.代码推送

```bash
# 将本地仓库的代码推送到远程仓库
$ git push [主机] [remote-branch]
# 将本地仓库的代码推送到远程仓库，并实现追踪远程分支
$ git push -u [主机] [remote-branch]
```

##### 8.代码拉取

```bash
# 从远程分支拉取代码，并与本地分支合并
$ git pull [主机] [remote-branch]
```
##### 9.撤销工作区更改(不包含新增的文件)

```bash
# 撤销工作区的修改和删除操作
$ git checkout [file]
```
##### 10.储藏工作区代码

```bash
# 储藏工作区代码，不提交
$ git stash
# 查看储藏的列表
$ git stash list
# 应用储藏(不会影响储藏的堆栈)
$ git stash apply stash@{2}
# 移除堆栈上的的储藏内容
$ git stash drop stash@{2}
# 应用储藏(并弹出储藏堆栈中的内容)
$ git stash pop stash@{2}
```
##### 11.查看信息

```bash
# 显示版本历史
$ git log
# 显示文件的变更
$ git status
```

参考my brother文章：[https://juejin.im/post/5d2d9271f265da1b6e65d632](https://juejin.im/post/5d2d9271f265da1b6e65d632)
参考文章：[http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)
