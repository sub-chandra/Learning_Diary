---
file_type: Manual # Manual
file_catalogue: CS
CreateTime: 2022
---

#Missing 


# Install
## Windows
Download Package: [Official](https://gitforwindows.org/)   or [Mirror](https://npm.taobao.org/mirrors/git-for-windows/)。
## Linux (`CentOS`)
```bash
yum remove git # Remove old version

# Install Dependencies
yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel 
yum install gcc-c++ perl-ExtUtils-MakeMaker

# Download Package and Install
# Package will newer. Check it!!!
cd /usr/src
wget https://www.kernel.org/pub/software/scm/git/git-2.7.3.tar.gz 
tar xf git-2.7.3.tar.gz
cd git-2.7.3

# Compile
make configure
./configure --prefix=/usr/git # Config
make profix=/usr/git
make install

# Environment
echo 'export PATH=$PATH:/usr/git/bin' >> /etc/profile
source /etc/profile

# Check Version
git --version
```
# Setting 
```bash
git --version # Check Git Version
# Global Setting
git config # Check the option of command 'config'
git config --help # Config Document 
# User Profile
git config --global user.name "<UserName>" 
git config --global user.email <MailAddress>

# Editor
git config --global core.editor emacs

# Check Config
git config --list # Check All
git config user.name # Check Certain Config
```
# Basic Operator
## Local
```bash
git init   # Initiation the Repository
git add .
git commit -m "Massage"

# Delete
git rm -r --cached <FileName> # Delete cache space file
git rm <FileName> # Delete file both on workspace and cache

# Branch
git branch # Check Local Branch
git branch -a # All Branch (Local & Remote)
git branch -r # Remote Branch
```

## Remote

```bash
git clone  #
git pull
git push
git push -u origin master
git remote -v
```

### Use GitHub as Remote Repository
```bash
# Create SSH Key


```
# Need to Solve 

1. What is Git
2. How to use Git
3. Git with `Github`
4. How to set the git on PyCharm and VScode
5. HEAD



`git clone`  where you use, where is the file
```bash
git clone https://github.com/aaa/bbb.git "$GOPATH/src/github.com/aaa"
```



# Github
>The step to pull or push repositories.

## Basic Setting
```bash
# Generate ssh-key
$ ssh-keygen -t rsa -C "github-subscribe-email" 
# Enter three times
# The key may create at C:/Users/Lenovo/.ssh/id_rsa.pub
vim C:/Users/Lenovo/.ssh/id_rsa.pub
vim /root/.ssh/id_rsa.pub

# ==Next Step:== 
# => Sign in `GitHub` 
# => Account => Settings 
# => SSH keys => New SSH key
# => Paste the key

# Test Connect
$ ssh -T git@github.com 
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
You've successfully authenticated, but GitHub does not provide shell access => Means Success
```



```bash
$ echo "# .py" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
# git branch -M "main"
$ git remote add origin git@github.com:sub-chandra/.py.git
$ git push -u origin master
```

# Problem
## Command Mean 
1. [git push origin和git push -u origin master的区别是什么 - 大数据 - 亿速云](https://www.yisu.com/zixun/594033.html)
2. 

## Error
git push 远程仓库名 远程分支名 --force
### `git push`
#### <font color='#cc1111'>The file will have its original line endings in your working directory</font>
1.  `warning: LF will be replaced by CRLF in database/migrations/2017_07_04_1004`
```bash
$ git config --global core.autocrlf false
```
#### <font color='#cc1111'>Remote: error: GH007: Your push would publish a private email address.</font>
==Step:==
=> Sign GitHub
=> Setting =>emails
=> *Uncheck*  Keep my email address private


>[!ERROR] <font color='#cc1111'>Updates were rejected because the tip of your current branch is behind</font>
>```bash
>git push origin master --force
>```



### `git pull`
#### `git pull` 指定文件夹
```bash
$ git config core.sparsecheckout true
$ git checkout master -- Missing src/main/resources/mybatis/mappers/CategoryMapper.xml # --with a space
# add file in .git/info/sparse-checkout
$ git pull origin master

# Easy Way
$ git fetch
$ git checkout origin/master -- <pathforfile>
```




# Use Git in Software
## Pycharm
## VScode


# Fast Note
## Branch
```bash
git branch -a # check branch list
git branch <NewBranchName> # Create New Branch
# git branch -d -r branchname （delete remote branch） 
git push origin --delete name  
# Delete Local Branch
git branch -d name  
# Check all Branch
git branch -a
```



# Link
##  Tutorial
[Git 教程 | 菜鸟教程 (runoob.com)](https://www.runoob.com/git/git-tutorial.html)
## Others
[20 个最常用的 Git 命令用法说明及示例 (baidu.com)](https://baijiahao.baidu.com/s?id=1651596943483969859&wfr=spider&for=pc)
[github 删除commit_faicm的博客-CSDN博客](https://blog.csdn.net/faicm/article/details/73438120)
[GitHub 删除某次 commit_ztenv的博客-CSDN博客_github删除commit记录](https://lianshaohua.blog.csdn.net/article/details/108336436?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-108336436-blog-73438120.pc_relevant_multi_platform_whitelistv1&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-108336436-blog-73438120.pc_relevant_multi_platform_whitelistv1&utm_relevant_index=1)
[Git->GitHub_CSDN](https://blog.csdn.net/djydjy3333/article/details/121076848)
[利用Pycharm上传代码到GitHub_有追求的人的博客-CSDN博客_pycharm上传代码到github](https://blog.csdn.net/qq_38238112/article/details/122611153)
[【如何使用 PyCharm 将代码上传到GitHub上（遇到的坑)】_段墨染的博客-CSDN博客_pycharm上传代码到github](https://blog.csdn.net/duan_mo_ran/article/details/123332690)
[pycharm中配置Git教程_방 화 우的博客-CSDN博客_pycharm配置git](https://blog.csdn.net/qq_55848322/article/details/123296707)
 [Git添加空文件夹_秦时明月之君临天下的博客-CSDN博客_git 空文件夹](https://blog.csdn.net/weixin_41287260/article/details/118057704)
[Git（4）-- 如何退出 git log 和 git commit 状态_BugMiaowu2021的博客-CSDN博客_git log怎么退出](https://blog.csdn.net/m0_46278037/article/details/119628828)
[能访问github网页但git clone不下来_诺有缸的高飞鸟的博客-CSDN博客_gitclone不下来](https://blog.csdn.net/qq_41102371/article/details/122213285)
[Github：加速方案汇总——解决由于国内网络环境导致GitHub打开慢或者打不开/克隆失败/下载慢等问题 - 知乎](https://zhuanlan.zhihu.com/p/445304091)
[Git-提交时On branch master Your branch is up to date with_涎涎的博客-CSDN博客](https://blog.csdn.net/qq_36079972/article/details/100279562)
