---
file_type: # Manual
file_catalogue:
CreateTime: 2022
---

#Missing 

```bash
git init
git clone
git rm -r --cached <FileName>
```


# Need to Solve 

1. What is Git
2. How to use Git
3. Git with `Github`
4. How to set the git on PyCharm and VScode

# Manual Link
[Fetching Title#2f91](https://www.runoob.com/git/git-tutorial.html)

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
#### <font color='#cc1111'># Updates were rejected because the tip of your current branch is behind</font>
```bash
git push origin master --force
```

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


[Fetching Title#6fk3](https://blog.csdn.net/m0_46278037/article/details/119628828)
[Fetching Title#n7mo](https://blog.csdn.net/qq_41102371/article/details/122213285)
[Github：加速方案汇总——解决由于国内网络环境导致GitHub打开慢或者打不开/克隆失败/下载慢等问题 - 知乎](https://zhuanlan.zhihu.com/p/445304091)
[Fetching Title#d2t6](https://blog.csdn.net/qq_36079972/article/details/100279562)


## Push Code to GitHub from PyCharm 
### Link
1. [Fetching Title#bsfw](https://blog.csdn.net/qq_38238112/article/details/122611153)
2. [Fetching Title#qcui](https://blog.csdn.net/duan_mo_ran/article/details/123332690)
3. [Fetching Title#td0m](https://blog.csdn.net/qq_55848322/article/details/123296707)
4. [Git添加空文件夹_秦时明月之君临天下的博客-CSDN博客_git 空文件夹](https://blog.csdn.net/weixin_41287260/article/details/118057704)
# Reference
1. [Git->GitHub_CSDN](https://blog.csdn.net/djydjy3333/article/details/121076848)


# Fast Note
[github 删除commit_faicm的博客-CSDN博客](https://blog.csdn.net/faicm/article/details/73438120)
[GitHub 删除某次 commit_ztenv的博客-CSDN博客_github删除commit记录](https://lianshaohua.blog.csdn.net/article/details/108336436?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-108336436-blog-73438120.pc_relevant_multi_platform_whitelistv1&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-108336436-blog-73438120.pc_relevant_multi_platform_whitelistv1&utm_relevant_index=1)


## Branch
```bash
git branch -a # check branch list
git branch <NewBranchName> # Create New Branch
# git branch -d -r branchname （删除远程分支）
删除远程分支命令：  
git push origin --delete name  
删除本地分支：  
git branch -d name  
查看所有分支:  
git branch -a
```

