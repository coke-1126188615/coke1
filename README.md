
# Git 常用操作总结

理解 Git 的内部原理，分清楚工作区、暂存区、版本库，还有就是理解 Git 跟踪并管理的是修改，而非文件。

![Git常用操作总结](https://img.aotu.io/mamboer/git-flow.jpg)

用 Git 比较久了，之前一直在 Win 用的 TortoiseGit，现在命令行用的比较多，所以把一些指令总结一下，以便回顾和查询。  

理解这些指令，觉得最重要的是理解Git的内部原理，比如Git的分布式版本控制，分清楚工作区、暂存区、版本库，还有就是理解Git跟踪并管理的是修改，而非文件。

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#设置 "设置")设置[](https://aotu.io/notes/2015/11/17/Git-Commands/#设置)

```bash
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#提交 "提交")提交[](https://aotu.io/notes/2015/11/17/Git-Commands/#提交)

git tracked的是修改，而不是文件

![git-track](https://img.aotu.io/mamboer/git-trees.jpg)

```bash
#将“当前修改”移动到暂存区(stage)
$ git add somfile.txt
#将暂存区修改提交
$ git commit -m "Add somfile.txt."
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#状态 "状态")状态[](https://aotu.io/notes/2015/11/17/Git-Commands/#状态)

```bash
$ git status
$ git diff
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#回退 "回退")回退[](https://aotu.io/notes/2015/11/17/Git-Commands/#回退)

```bash
# 放弃工作区修改
$ git checkout -- file.name
$ git checkout -- .

# 取消commit(比如需要重写commit信息)
$ git reset --soft HEAD

# 取消commit、add(重新提交代码和commit)
$ git reset HEAD
$ git reset --mixed HEAD

# 取消commit、add、工作区修改(需要完全重置)
$ git reset --hard HEAD
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#记录 "记录")记录[](https://aotu.io/notes/2015/11/17/Git-Commands/#记录)

```bash
$ git reflog
$ git log
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#删除 "删除")删除[](https://aotu.io/notes/2015/11/17/Git-Commands/#删除)

```bash
$ rm file.name
$ git rm file.name
$ git commit -m "Del"
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#远程操作 "远程操作")远程操作[](https://aotu.io/notes/2015/11/17/Git-Commands/#远程操作)

```bash
$ git remote add origin git@github.com:michaelliao/learngit.git
# 第一次推送，-u(--set-upstream)指定默认上游
$ git push -u origin master
$ git push origin master
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#克隆 "克隆")克隆[](https://aotu.io/notes/2015/11/17/Git-Commands/#克隆)

```bash
$ git clone https://github.com/Yikun/yikun.github.com.git path
$ git clone git@github.com:Yikun/yikun.github.com.git path
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#分支操作 "分支操作")分支操作[](https://aotu.io/notes/2015/11/17/Git-Commands/#分支操作)

![about-merge](https://img.aotu.io/mamboer/git-merge.png)

```bash
# 查看当前分支
$ git branch

# 创建分支
$ git branch dev
# 切换分支
$ git checkout dev

# 创建并checkout分支
$ git checkout -b dev

# 合并分支
$ git merge dev

# 删除分支
$ git branch -d dev
```

### [](https://aotu.io/notes/2015/11/17/Git-Commands/#标签 "标签")标签[](https://aotu.io/notes/2015/11/17/Git-Commands/#标签)

```bash
$ git tag 0.1.1
$ git push origin --tags
```