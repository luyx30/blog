# 修改Git提交历史中的author等信息

前提：重置本项目用户的信息

```bash
git config user.name '张三'
git config user.email 'zhangsan@126.com'
```

使用`git rebase`方案

首先回到当前分支第一个commit

```bash
git rebase -i --root
```

然后，弹出编辑器，移动到需要修改的commit处，按字母e，变成可编辑状态，将picked修改为edit，然后wq，退出vi。

执行提交修改命令

```bash
git commit --amend --reset-author
```

之后，通过continue命令回到正常状态

```bash
git rebase --continue
```

查看日志，确定是否修改成功

```bash
git log
```

最后，强制push到远程仓库

```bash
git push origin main -f  
```
