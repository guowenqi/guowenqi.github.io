---
title: 多PC管理hexo博客
date: 2016-10-17 16:46:42
tags: [hexo]
categories: [hexo博客搭建与优化]
---
## hexo博客创建
1. 创建仓库，(将"Initialize this repository with a README"选中，目的：克隆初始化的远程仓库到本地)（仓库名必须为:username.github.io）

2. 创建两个分支：master 与 hexo，设置hexo为默认分支（因为我们只需要手动管理这个分支上的Hexo网站文件，master存放"hexo g"命令生成的静态网页）;

3. 配置公钥，ssh-keygen -t rsa -C "your_email@youremail.com" 

4. 添加公钥，为远程github的username.github.io仓库添加.ssh文件夹下的id_rsa.pub文件的所有内容（验证公钥是否成功ssh -T git@github.com）
<!--more-->
5. 设置username和email，git config --global user.name "your name" 和 git config --global user.email "your_email@youremail.com"

6. 克隆仓库到本地，任意位置通过Git bash执行git clone git@github.com:username/username.github.io.git拷贝仓库，在本地生成的仓库名为：username.github.io.git（进入本地仓库，使用git status 命令查看，当前分支应显示为hexo），如果想自定义本地仓库的名字，可以使用如下命令：git clone git@github.com:username/username.github.io.git hexo，本地仓库的名字就变为hexo(hexo可改成你想要的名字);

7. 任意位置新建一个空文件夹（文件夹名任意，最好为英文，我这里命名为example），然后在该文件夹下通过Git bash依次执行npm install hexo-cli -g、hexo init、npm install 和 npm install hexo-deployer-git --save;

8. 移动example文件夹里的所有内容到第6歩产生的username.github.io.git文件夹的根目录下

9. 配置username.github.io.git文件夹根目录下的_config.yml文件，deploy部分修改为如下所示：
```
deploy:
   type: git
   repository: git@github.com:username/username.github.io.git
   branch: master
```
10. 依次执行git add .（注意不要少了"."）、git commit -a -m "..."(...替换为提交信息)、git push origin hexo提交网站相关的文件;

11. 执行hexo clean、hexo g 、hexo d生成网站并部署到GitHub上.

通过以上配置，就可以在多PC上管理自己的博客了
## 博客的日常管理
当重装电脑之后，或者想在其他电脑上修改博客，可以使用下列步骤：

1. 安装必备软件，git、node.js

2. 配置公钥，ssh-keygen -t rsa -C "your_email@youremail.com" 

3. 添加公钥，为远程github的username.github.io仓库添加.ssh文件夹下的id_rsa.pub文件的所有内容（验证公钥是否成功ssh -T git@github.com）

4. 设置username和email，git config --global user.name "your name" 和 git config --global user.email "your_email@youremail.com"

5. 克隆仓库到本地，任意位置通过Git bash执行git clone git@github.com:username/username.github.io.git命令拷贝仓库，在本地生成的仓库名为：username.github.io.git（进入本地仓库，使用git status 命令查看，当前分支应显示为hexo），如果想自定义本地仓库的名字，可以使用如下命令：git clone git@github.com:username/username.github.io.git hexo，本地仓库的名字就变为hexo（hexo可改成你想要的名字）;

6. 进入第5歩所生成的文件夹，通过Git bash依次执行npm install hexo-cli -g、npm install 和 npm install hexo-deployer-git--save（注意：不能执行hexo init这条指令）

7. 写文章，现在就可以通过hexo new title（title是你文章的标题）命令来写文章了;

8. 依次执行git add .（注意不要少了"."）、git commit -a -m "..."、git push origin hexo提交网站相关的文件;

9.执行hexo clean、hexo g 、hexo d生成网站并部署到GitHub上.
## 配置过程中经常使用的命令
git status		//列出当前目录所有还没有被git管理的文件和被git管理且被修改但还未提交			  (git commit)的文件

git remote	//查看远程服务器名

git branch	//查看本地分支

git branch -r	//查看远程分支

Git branch -a 	//查看所有分支（包括本地和远程）

git add .		//追踪所有文件

git commit -a -m "..."	//跳过使用暂存区域，自动把所有已经追踪过的文件暂存起来并提交

git push		//上传

git clone		//克隆远程仓库到本地

git remote add origin git@github.com:username/username.github.io.git	//与远程仓库链接

git push -u origin master 	//-u 第一次提交让git记住本地仓库与远程仓库的连接,以后可							 以不要