# Git

[toc]

以下命令请在Git Bash命令行窗口上执行

## Linux常用指令

`cd`改变目录

`cd..`回退到上一个目录

`pwd`显示当前工作路径

`ls`列出当前目录的所有文件

`touch`新建一个文件

`rm`删除一个文件

`mkdir`新建一个目录（文件夹）

`rm -r`删除一个文件夹

`mv`移动文件

`reset`重新初始化

`clear`清屏

`history`查看历史命令

`help`帮助

`exit`退出

`#`注释

## 必要配置

`git config -l`查看所有配置

`git config --system --list`查看系统方面的配置

`git config --global --list`查看全局配置

`git config --global user.name "[用户名]"`设置用户名

`git config --global user.email [邮箱]`设置邮箱

## 创建版本库

1. `git init`初始化仓库，生成隐藏的.git文件夹
2. `git add [filename]`将文件添加到暂存区
3. `git commit -m "注释"`将文件提交到仓库
4. `git status`检查文件提交情况

新建readme.txt文件，内容为"11111111"，执行命令结果如下

![image-20220325150053324](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325150053324.png)

修改readme.txt文件，增加"22222222"，但未提交，执行命令结果如下

![image-20220325150747087](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325150747087.png)

提交修改后的readme.txt文件

![image-20220325150930377](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325150930377.png)

## 版本回退

1. `git log`查看版本更新日志
   1. `git log --pretty=oneline`减少显示内容
2. `git reset --hard HEAD^`回退一个版本
   1. `^^`回退两个版本，也可以用`git reset --hard HEAD~100`回退100个版本
3. `cat [filename]`查看文件内容
4. `git reflog` 查看版本id
5. `git reset --hard [id]`回退到某一个版本id

修改readme.txt文件，增加"33333333"，并提交查看日志，执行命令结果如下

![image-20220325151140333](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325151140333.png)

回退到版本2，命令结果如下

![image-20220325151242301](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325151242301.png)

撤回回退，输入版本id，回到版本3，执行命令结果如下

![image-20220325151504992](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325151504992.png)

## 工作区和暂存区

工作区：电脑上看到的文件夹

版本库：.git隐藏文件夹，里面还有暂存区和分支master

`git add`是将文件c从工作区提交到暂存区

`git commit`是将文件从暂存区提交到分支

修改readme.txt，增加test.txt文件

![image-20220325152357884](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325152357884.png)

将暂存区的文件提交到分支

![image-20220325152519017](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325152519017.png)

## 撤销修改和删除文件

1. `git checkout -- [filename]`删除当前工作区文件
   1. 文件还处在工作区，输入命令回到版本库状态
   2. 文件处在暂存区，此时修改了文件，执行命令后回到暂存区的文件
2. `rm [filename]`可以删除文件
3. `git rm [filename]`删除版本库中的文件，然后`git commit -m "注释"`提交到版本库

修改readme.txt文件，增加"55555555"，文件仍在工作区，执行撤销命令结果如下

![image-20220325160249209](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325160249209.png)

在readme.txt文件中增加”66666666“后，进入暂存区，执行命令后结果如下

![image-20220325160606276](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325160606276.png)

增加文件b.txt，但是这是错误上传，需要删除，命令结果如下

![image-20220325161229973](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220325161229973.png)

## 远程仓库

1. `git remote add origin 网址`添加远程仓库
2. `git push -u origin master`第一次推送会将本地master分支与远程master关联
3. `git push origin master`后续使用，简化指令

![image-20220412161133996](https://enzhewu.oss-cn-hangzhou.aliyuncs.com/pic/image-20220412161133996.png)

4. `git remote -v`查看远程库信息
5. `git remote rm [name]`删除远程库与本地的关联关系，真正删除文件需要在GitHub上执行

