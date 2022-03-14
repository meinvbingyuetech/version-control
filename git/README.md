[HX文档](https://hx.dcloud.net.cn/Tutorial/SourceControl/Git/README)

# 配置全局别名
```
git config --global alias.st status        # git st

git config --global alias.ck checkout
git config --global alias.com commit
git config --global alias.br branch
git config --global alias.ll pull
git config --global alias.pu push
```

# 创建新分支，同时在远程创建，并关联本地
```
git ck -b dev
git push origin dev
git branch --set-upstream-to=origin/dev dev
```

# 强制回退
```
git log
git reset --hard 2a4bad9f499039f2b1309f3c15f0d1b56ee70722
```

# 强制将本地的修改覆盖了远程仓库的版本
```
git push -f origin master
```

# 一些坑

当我们需要删除暂存区或分支上的文件, 同时工作区也不需要这个文件了, 可以使用

```
1 git rm 1.txt
2 git commit -m 'delete somefile'
3 git push
```

当我们需要删除暂存区或分支上的文件, 但本地又需要使用, 只是不希望这个文件被版本控制, 可以使用

```
git rm --cached 1.txt                         文件
git rm -r --cached .idea/                     文件夹
git commit -m 'delete remote somefile'
git push
```
