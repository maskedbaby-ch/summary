# git 仓库创建
## 1. github上创建仓库
    Respositories >> New
## 2. 本地创建上传
```c
echo "default" >> README.md
git init
git add README.md
git commit -m "upload readme"
git branch -M main
git remote add origin https://github.com/maskedbaby-ch/summary.git
git push -u origin main
```
## 3. 问题
```c
    git commit -m "upload readme" 报错
```
报错如下:

<font color=red>
    *** 请告诉我你是谁  

运行  
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
</font>

<font color=green>
解决：没有添加账号导致，按照提示添加邮箱账号密码  
</font>  

**********************************************

```c
    git push -u origin main 登陆出错
```  

报错如下:
<font color=red>
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.   

remote: Please see https://github.blog/   

2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
fatal: Authentication failed for 'https://github.com/maskedbaby-ch/summary.git/'
</font>

<font color=green>
解决：不再支持密码登陆，需要创建token，使用token登陆
</font> 

*********************************************************

