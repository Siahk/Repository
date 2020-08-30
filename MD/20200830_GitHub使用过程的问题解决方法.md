# GitHub使用过程的问题解决方法

## 1.branch 'master' set up to track remote branch 'master' from 'origin'.

添加到本地仓库

```
git add .
```

添加提交描述

```
git commit -m '描述'
```

提交前先从远程仓库主分支中拉取请求

```
git pull origin master
```

把本地仓库代码提交

```
git push -u origin master
```

参考资料：[Github无法提交代码如何解决？](https://juejin.im/post/6844903840081248263)

## 2.failed to push some refs to

### 问题说明

在本地仓库直接添加一个文件，进行了`add`操作，没有进行`commit`操作，之后对该文件名称进行修改，并再次使用了`add`操作，这个使用`commit`操作就会出现push失败的问题

### 注意

**慎用变基，使用时要确定自己的分支后再操作，此处是以master分支为例，错误使用分支导致代码丢失**

### 解决方法

问题是由于远程库和本地库的不一致导致的，直接把远程库同步刀本地库就好了

```
git pull --rebase origin master
```

*指令意思：把远程库中的更新合并到本地库中，–rebase的作用是取消掉本地库中刚刚的commit，并把他们接到更新后的版本库之中*

参考资料：[git push错误failed to push some refs to的解决](https://blog.csdn.net/MBuger/article/details/70197532)

