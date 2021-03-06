# git_study_demo

`git` 学习笔记

## 本地初始化git仓库

```javascript
# 创建空项目
mkdir git-demo
# 进入项目
cd git-demo
# 初始化git仓库
git init
```

### 向本地仓库添加文件

```javascript
# 将本地添加或修改的文件提交到暂存区
git add <file> | git add .
# 将暂存区中的修改提交到本地仓库.git
git commit -m 'description'
```

## 查看本地仓库的状态

使用`git status`命令可以查看到本地仓库当前的状态

## 查看某个文件具体的修改

使用`git diff <file>`查看某个文件具体的修改

## 版本回退

1. 查看修改记录

```javascript
git log
```

![image-20201124120548988](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20201124120548988.png)

得到上图的显示从最近到最远的提交日志

2.版本回退

```javascript
git reset --hard HEAD^
```

`git`中，使用`HEAD`表示当前版本，上一个版本使用`HEAD^`,上上一个版本是`HEAD^^`,往上100个版本`HEAD~100`

`--hard`参数

3.查看版本回退是否成功

```javascript
cat <file>
```

4.恢复到回退之前的版本

```javascript
git reset --hard <回退之前版本的commit Id>
```

`commit ID`不需要写全，只需要前几位即可

如果找不到回退之前的`commit Id`还可以通过`git reflog`命令查找

![image-20201124122521119](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20201124122521119.png)

## 查看工作区和版本库里面最新版本的区别

```javascript
git diff HEAD -- <file>
```

## 撤销修改

```javascript
git checkout -- file
```

撤销某个文件在工作区的全部修改，撤销状态：

一种是文件自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是文件已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态；

注意：`git checkout -- file`命令中的`--`很重要，没有`--`，就变成了“切换到另一个分支”的命令

### 把暂存区的修改撤销掉（unstage），重新放回工作区

```javascript
git reset HEAD <file>
```

`it reset`命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用`HEAD`时，表示最新的版本



## 分支的创建

1.创建分支

```javascript
git branch dev-1
```

2.切换分支

```javascript
git checkout dev-1
```

`1，2`等价于 `git checkout -b dev`,创建`dev`分支并切换到`dev`

3.查看所有分支

```javascript
git branch
```

分支前面带有`*`的表示当前分支

4.合并分支

```javascript
# 切换到主分支
git checkout main
# 将主分支和dev-1分支进行合并
git merge dev-1
```

5.删除指定分支

```javascript
git branch -d dev-1
```

## 小结

查看分支：`git branch`

创建分支：`git branch <name>`

切换分支：`git checkout <name>`或者`git switch <name>`

创建+切换分支：`git checkout -b <name>`或者`git switch -c <name>`

合并某分支到当前分支：`git merge <name>`

删除分支：`git branch -d <name>`

## 解决冲突

冲突解决办法

`git merge dev`

在合并过程中出现冲突，定位到相应的冲突文件，保留自己需要的代码后执行`git add` 和 `git commit`,最后删除分支

查看分支合并图

```javascript
git log --graph
```

