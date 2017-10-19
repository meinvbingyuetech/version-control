- https://github.com/
- meinvbingyue/meinvbingyue@qq.com
- jason7862102


####用SSH地址拉项目就可以了


---


如果没有.ssh目录，打开Shell（Windows下打开Git Bash），创建SSH Key:
ssh-keygen -t rsa -C "meinvbingyue@qq.com"

登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容（有换行不怕）


$ cd ~/.ssh/
$ ll -a


---

如果弹出提示输入帐号密码的框，可以输入下面的代码，让程序在控制台里提示
```
unset SSH_ASKPASS
```

终极解决方法：
应该是远程库使用了https连接，改为ssh链接就行了

```
-> vim .git/config -> [remote "origin"] -> url=***
```

或

- git remote remove origin
- git remote add origin git@github.com:meinvbingyuetech/laravel.git

---

###SSH权限问题：
- 1. 用户home目录755权限
- 2. .ssh目录700权限
- 3. authorized_keys 600权限


###测试ssh能不能连到服务器
- ssh git@192.168.11.133
