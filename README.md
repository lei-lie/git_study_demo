# git_study_demo

git 学习笔记

## 本地初始化git仓库

```
# 创建空项目
mkdir git-demo
# 进入项目
cd git-demo
# 初始化git仓库
git init
```

### 向本地仓库添加文件

```
# 将本地添加或修改的文件提交到暂存区
git add <file> | git add .
# 将暂存区中的修改提交到本地仓库.git
git commit -m 'description'
```

## 查看本地仓库的状态
使用`git status`命令可以查看到本地仓库当前的状态

## 查看某个文件具体的修改

使用`git diff <file>`查看某个文件具体的修改

## 分支的创建

1.创建分支

```
git branch dev-1
```

2.切换分支

```
git checkout dev-1
```

`1，2`等价于 `git checkout -b dev`,创建`dev`分支并切换到`dev`

3.查看所有分支

```
git branch
```

分支前面带有`*`的表示当前分支

4.合并分支

```
git checkout main
git merge dev-1
```

5.删除指定分支

```
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
