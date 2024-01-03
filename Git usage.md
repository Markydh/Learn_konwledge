# Git 上传文件到github

```
1.千万你想要上传文件的目录下
cd <path you want to go>
2.创建git仓库
git init
3.关联远程仓库
git remote add origin git@github.com:Markydh/eee.git
4.同步远程仓库和本地仓库
git pull origin main
5.添加文件
git add <file_name>
6.上传文件
git commit -m "your description"
7.本地仓库修改（或者添加）的内容提交到远程仓库
git push origin master
```



# Git 删库

## 使用命令行删除Git目录

```
1. 先寻到要删除的文件目录
cd <path you want to go>
2. 进入文件夹后，列出可见和隐藏文件夹
ls -la
3.删除指定后缀文件
rm -rf .git
```

# Git 返回指定版本

git 查看历史版本

```
git log
```

```
git reset --hard <指定版本号>
```




# Git 分支操作

1. 查看分支

```
git branch
```

2. 创建分支

```
git branch <分支名>
```

3. 切换分支

```
git checkout <分支名>
```

4. 合并分支

```
git merge <分支名> <合并分支名>
```

5. 推送到远层仓库

```
git push
```

6. 删除分支

```
git branch -d <分支名>
```

7. 解决冲突

```
git pull --allow-unrelated-histories
```
![Image text](https://github.com/Markydh/Learn_konwledge/blob/main/Git%20usage.assets/截屏2023-12-26%2013.27.49-3568479-3568482-3568490.png)



# 遇到的问题

![Image text](https://github.com/Markydh/Learn_konwledge/blob/main/Git%20usage.assets/截屏2023-12-26%2015.50.21.png)

solve methods

​	这个问题可能是之前提交

1. 选择暂存，请记得在变基完成后，通过 `git stash pop` 恢复你的变更。

```
 git stash
```

2. 执行变基

```
git pull origin master --rebase
```

3. 拉取文件到github

```
git push origin master
```
