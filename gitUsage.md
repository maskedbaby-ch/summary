# <center>git 使用</center>
无法登录github办法，进入 
```shell C:\Windows\System32\drivers\etc ```
在hosts文件末尾增加
```shell
#GitHub Start
140.82.112.3 github.com
140.82.114.4 gist.github.com
185.199.108.153 assets-cdn.github.com
185.199.108.133 raw.githubusercontent.com
185.199.108.133 gist.githubusercontent.com
185.199.108.133 cloud.githubusercontent.com
185.199.108.133 camo.githubusercontent.com
185.199.108.133 avatars.githubusercontent.com 
185.199.108.133 avatars0.githubusercontent.com
185.199.108.133 avatars1.githubusercontent.com
185.199.108.133 avatars2.githubusercontent.com
185.199.108.133 avatars3.githubusercontent.com
185.199.108.133 avatars4.githubusercontent.com
185.199.108.133 avatars5.githubusercontent.com
185.199.108.133 avatars6.githubusercontent.com
185.199.108.133 avatars7.githubusercontent.com
185.199.108.133 avatars8.githubusercontent.com
#GitHub End
```
## 1. github上创建仓库  
        Respositories >> New
## 2. 本地创建上传
```shell
    echo "default" >> README.md
    git init
    git add README.md
    git commit -m "upload readme"
    git branch -M main
    git remote add origin git@github.com:maskedbaby-ch/summary.git
    git push -u origin main
```
## 3. 问题
```shell
    git commit -m "docs:upload readme" 报错
```
报错如下:

<font color = red>

*** 请告诉我你是谁  
运行  
```shell
git config --global user.email "you@example.com"

git config --global user.name "Your Name"
```
</font>

<font color = green>
解决：没有添加账号导致，按照提示添加邮箱账号密码  
</font>  

**********************************************

```shell
    git push -u origin main 登陆出错
```  

报错如下:
<font color = red>
```shell
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.   

remote: Please see https://github.blog/   

2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
fatal: Authentication failed for 'https://github.com/maskedbaby-ch/summary.git/'
```
</font>

<font color = green>
解决：不再支持密码登陆，需要创建 token，使用 token 登陆
</font> 

*********************************************************
## 4. 使用免密码登陆
首先 ssh-keygen -t rsa -C "邮箱@163.com" 生成密钥
cat 生成的密钥并复制，密钥在 ~/.ssh/
到 github 的 setting，找到 SSH keys，把密钥复制进去
如果之前创建仓库使用的 https 可以使用
```shell
    git remote set-url origin git@github.com:maskedbaby-ch/summary.git
```
切换到ssh

******************************************************
## 5. 克隆项目
使用以下命令
```shell
    git@github.com:maskedbaby-ch/summary.git
```
## 6. 文件差异

使用可查看暂存区和工作区差异
```shell
    git diff
```
## 7. 版本回溯
查看历史提交记录

```shell
    git log
```
回溯到某个版本

```shell
    git reset [--soft | --mixed | --hard] [HEAD] #--soft 参数 用于回溯到某个节点
    git reset --soft 9f769310b5d03193abc1345746fab6f149e31acf
```

如果是--hard参数则是回退到上个版本

```shell
    git reset –hard HEAD~3 #回退到上上上个版本
    #HEAD 说明：
    # HEAD 表示当前版本
    # HEAD^ 上一个版本
    # HEAD^^ 上上一个版本
    # HEAD^^^ 上上上一个版本
    # 以此类推...
    # 也可以使用 ～数字表示
    # HEAD~0 表示当前版本
    # HEAD~1 上一个版本
    # HEAD^2 上上一个版本
    # HEAD^3 上上上一个版本
```

## 8. 分支 
* 显示当前分支 
```shell
    git branch   
```

* 创建一个新的分支 
```shell
    git branch <name>
```

* 切换分支
```shell
    git checkout <branch> #切换分支前，使用 git stash 暂存，来防止影响分支
    #git stash pop 使用 "git stash pop" 将可复原到最新的操作。指定 stash ID （如：stash@{1}），则可以恢复特定的操作
```
![Alt text](https://backlog.com/git-tutorial/tw/img/post/stepup/capture_stepup1_3_3.png "Stash")


* 建立同时切换分支
```shell
    git checkout -b <branch>
```

* 删除分支
```shell
    git branch -d <branch>  #删除时候，不能在要删除分支里，否则无法删除
```
* 合并分支
```shell
    git merge issue1   #合并某分之前，先切换到要合并到的分支
```





