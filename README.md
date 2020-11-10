# git_study_demo

git 学习笔记

## 分支的创建

1.创建分支

```
git branch dev-1
```

2.切换分支

```
git checkout dev-1
```

1，2等价于 `git checkout -b dev`,创建dev分支并切换到`dev`

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
