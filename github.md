# git 基本操作
## 1 删除文件恢复
rm README
ls
ls -al
git status
git checkout README
ls -al
## 1. 再查看git仓库是状态
 git status
## 2.说明：只要将文件提交到git仓库中
## 2 版本回退
### 1. 没次的提交文件都叫版本，如果退回，会吧修改的提交到仓库中，都会保存在git的目录下。
### 2.退回上层命令.
 git reset --hard commitID
### 注意: 使用这个命令后,再使用git log命令不会查看到所有log的相关信息, 那么我们没有办法获取到后一个提交的CommitID.
## 3 从仓库中删除文件

### 1. 删除文件
 git rm filename
### 2. 再次提交
   git commit
## 4 从版本库中忽略文件
 touch git ignorG
## 5 版本之间的比较语句i
  git diff
  git diff commitID1 commitID2
## 6 patch的意思
### patch多指补丁的意思, 在这里更多的指程序有一些bug, 需要我们进行fixed, 那fixed源码文件就是patch.patch实际上是保存两个文件的差异.
## 7 git生成patch
 git format-patch -p1
 git 打patch
 git am patch-name

# git分支的操作
## 1 创建分支
  git branch branch-name
## 2 切换
  git checkout -b branch-name
## 3 显示分支
  git branch -av
## 4 分支切换
  git checkout branch-name
## 5 删除分支
  git branch -D branch-name
## 6合并分支 
  git checkout master
  git merge develop










































