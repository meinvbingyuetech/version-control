# 强制回退
```
git log
git reset --hard 2a4bad9f499039f2b1309f3c15f0d1b56ee70722
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
