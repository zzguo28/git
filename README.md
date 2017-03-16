# git
多人协作项目使用git的规范

多人团队进行项目开发的工程中git建议使用的形式。。有待完善


第一步 拷贝项目到本地

git clone 地址

查看项目的分支情况

git branch

 * master
然后项目人员创建一个分支

git branch dev

git branch

dev
* master

切换分支 使用 git checkout

git checkout dev

在使用git branch查看分支状况
*dev
master
可以看到在dev分支上面

创建分支之后直接切换到新的分支
git checkout -b dev

查看整个项目的分支状况 使用 git checkout -a
    包含远程分支和本地的分支

当我们上传文件的时候上传到某个分支 需要使用 git push origin dev
    意思就是上传到dev分支上面

当我们想要把某个远程分支上面的项目拉倒本地的时候需要使用

此时只需执行git fetch origin dev:dev  将远程分支代码拉取到本地.

然后看一下状态 git branch -a

  解决上传文件之间的冲突

  1 善于使用git status 查看现在项目的整个状态
  然后我们会发现冲突的文件然后进行修改就行了

  2 使用git log 退回某个特定的版本

  git log 显示的内容是从最近到最远的提交日志

  也可使用简洁的方式 git log --pretty=oneline

  退回特定的时候 需要使用  git reset --hard HEAD^

  其中HEAD^ 表示上一个版本 HEAD^^表示退回上上一个以此类推
 
 如果你退回某个分支之后又想回到以前的某个分支的话 如果当前控制台没有关闭的话那么你还有机会，
 我们在git commit -m "可以显示ID的"的时候 这个命令会返回一个id，，我们只需要执行
 git reset --hard id值     这样就可以回到某个特定的版本了

 如果你忘记了是哪个分支的id 只要是commit的时候备注好了，，那么你还有机会。。。 git reflog 
 这样就可以访问每次提交时候的id了。。。。

 git diff 可以对比两次之间的差异


 最后合并分支


 git merge 用于合并指定分支到当前分支 

 git branch -d 合并的指定分支  删除合并的指定分支

 在使用git merge 的时候我们要善于 使用 git branch 和  git checkout  还有 git status

 这个合并所有分支的时候需要熟悉的人进行合并要不然会出事情的。。。



 每次提交的时候注释写好重要了   。。 注释   注释  注释。。。。重要的事情说三遍！！！！！！！！！！！！！

建议每个团队合作的人员都建立一个自己的项目分支

团队开发禁止在主干直接修改代码，一定要开分支，而且是远程分支进行开发。

创建分支可以打标签，git tag。

拉取代码时最好先git fetch再git merge而不是直接git pull。

提交代码和推送代码以及代码上线之前，一定要先和原来版本对比 git diff 。

提交代码加注释 这个注释一定要加好的
