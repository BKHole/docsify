## 说明

- 分支名：dev
- 标签名：v1.0
- commit版本号：9fceb02
- 备注信息：'info'

文中例子所出现分支名，标签名均用以上指代，实际项目可自行取名；根据项目实际版本号选定commit版本号和添加备注信息。

## 初始化

```
git init // 初始化本地仓库
```

## 创建分支

```
git checkout -b dev // 创建并切换dev分支

git branch dev // 创建dev分支

git checkout dev // 切换dev分支
```

## 查看分支

```
git branch // 查看本地分支列表

git branch -a // 查看远程分支列表
```

## 本地提交

```
git add . // 项目根目录添加所有更改文件

git commit -m 'info' // 提交本地仓库并添加备注信息
```

## 合并分支

```
git checkout master // 切换master分支

git merge dev // 合并dev分支到master分支
```

## 删除分支

```
git branch -d dev // 删除本地仓库dev分支
```

## 关联远程仓库

> note: 无远程仓库地址时，添加关联

```
git remote add origin 远程仓库url       // 添加远程仓库地址
```

## 设置远程仓库

> note: 已有远程仓库地址时，修改设置

```
git remote set-url origin 远程仓库url   // 设置远程仓库地址
```

## 查看远程仓库地址

``` code
git remote -v
or
git remote get-url origin
```

## 推送远程仓库

```
git push origin master // 推送本地仓库到远程仓库master分支

git push origin dev // 推送本地仓库到远程仓库dev分支
```

## 拉取远程仓库

```
git pull origin master // 拉取远程仓库master分支到本地仓库
```

## 删除已提交文件夹

```
git rm -r --cached .idea // 删除.idea文件夹
```

## tag

```
git tag v1.0 // 添加标签v1.0

git tag -a v1.0 -m 'info' // 添加标签v1.0，并备注信息info

git tag -a v1.0 9fceb02 -m 'info' // 指定commit版本添加标签v1.0，并备注信息info

git show v1.0 // 查看v1.0 tag详细信息

git push origin v1.0 // 推送tag到远程仓库

git tag -d v1.0 // 删除本地仓库v1.0 tag

git push origin :refs/tags/v1.0 // 删除远程仓库v1.0 tag
```
