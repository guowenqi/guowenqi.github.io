---
title: hexo+github搭建个人博客详细步骤
date: 2016-10-17 15:29:19
tags: [hexo]
categories: [hexo博客搭建与优化]
---
## 注册github账号
1、登录[github](https://github.com/)官网(github.com)。
如果你已经有账号，那么点击右上角的sign in直接登录。
如果没有账号，依次输入昵称、邮箱、密码，然后点击Sign up for GitHub进行注册，按照默认的设置完成注册，最后还要进行邮件确认,我们登录到自己的注册邮箱中，会有一个github发来的邮件，点击即可。
<!--more-->
## 建立远程仓库（repository）
1、登录第一步注册的github账号，点击Start a project，在Repository name下输入仓库名，记住仓库名必须是：username.github.io（username用你实际注册的github账号名替换）的格式，其他的保持默认即可，然后点击Create repository，到这里，你在github上的的一个仓库就已经建立成功。
## GIT下载和配置
1、下载：  
登录[git](https://git-scm.com/)官网(git-scm.com) ，下载和你的电脑系统相对应的版本（32位Windows，64位Windows，linux，Solaris，Mac OS X）。
2、安装：  
这里以Windows7系统为例，直接默认安装即可。
3、配置：  
在开始菜单-所有程序中打开Git文件夹下的Git Bash（或在光标不选中任何事物的情况下，点击鼠标右键，选择Git Bash Here），会打开如下界面：
![1][1]
4、创建本地仓库：  创建放置博客文件的文件夹（即仓库）：hexo文件夹。在硬盘根目录下创建文件夹，如我的hexo文件夹的位置为E:\hexo，名字和地方可以自由选择，当然最好不要放在中文路径下。之后进入文件夹，即E:\hexo内，点击鼠标右键，选择Git Bash，执行以下命令：
```
$ git init
```
（命令中的$符号只为了让教程和实际看起来一致，实际输入命令只需输入$后面的命令即可，下同)，会得到如下所示结果：
![2][2]
这时Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），可以发现当前目录下（即新建的本地仓库E:\hexo）多了一个.git的文件夹，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。如果你没有看到.git文件夹，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见。执行命令：
```
$ ls -ah
```
即可看到隐藏的.git文件夹，如下所示：
![3][3]
5、	配置ssh key：  为了把本地仓库（E:\hexo）生成的博客静态网页上传到github，还需要配置ssh key，输入以下命令:
```
$ ssh-keygen -t rsa -C "your_email@youremail.com" 
```
（your_email@youremail.com替换为你的邮箱），之后会要求确认路径和输入密码，我们这里使用默认的设置，一路回车就行，如果命令执行成功，会在C:\Users\Administrator目录下生成一个.ssh的文件夹（如果找不到.ssh文件夹在哪，可以输入以下命令查看.ssh文件夹的路径：$ ~/.ssh）。进入.ssh文件夹，使用Notepad++软件打开id_rsa.pub文件，复制全部内容（即生成的key）。（注意：千万不要使用Windows自带的记事本编辑任何文本文件。原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符，你会遇到很多不可思议的问题，比如，网页第一行可能会显示一个“?”，明明正确的程序一编译就报语法错误，等等，都是由记事本的弱智行为带来的。建议你下载Notepad++代替记事本，不但功能强大，而且免费！记得把Notepad++的默认编码设置为UTF-8 without BOM即可）打开github官网，登录第一步所创建的github账号，然后在页面右下角的Your repositories目录下，打开第二步创建的仓库（username.github.io） ，点击右上角的settings，左边选中SSH and GPG keys，右边选择New SSH key，Title可随便填写，Key：粘贴上面复制的key（即id_rsa.pub文件的全部内容），然后点击Add SSH key。之后会收到一封github官网发来的验证邮件，打开邮件链接进行确认即可。
为了验证是否成功，在git bash下输入命令：
```
$ ssh -T git@github.com
```
如果是第一次，会提示是否continue，输入yes就会看到：
You’ve successfully username, but GitHub does not provide shell access （username会显示为你的账号名称）
这就表示已成功连上github。
## Hexo的安装和配置
1、下载：  
登录[node.js](https://nodejs.org/en/)官网（nodejs.org/en） ,下载和你的电脑系统相对应的版本
2、安装：  
这里以Windows7系统为例，直接默认安装即可。
打开E:\hexo文件夹，鼠标右键选择Git Bash Here，依次执行以下命令：
```
$ npm install hexo-cli -g
$ hexo init
$ npm install
```
Hexo会自动在本地仓库（即E:\hexo）下下载搭建网站所需的所有文件。
接着执行命令：
```
$ hexo g
$ hexo s
```
然后用浏览器访问http://localhost:4000/，此时，你应该看到了一个漂亮的博客了，当然这个博客只是在本地的，别人是看不到的，hexo3.0使用的默认主题是landscape。（这是hexo的本地预览功能）
## 上传本地仓库（即博客）到github
1、设置username和email： 因为github每次commit都会记录他们，依次执行命令：
```
$ git config --global user.name "your name"  
$ git config --global user.email "your_email@youremail.com"
```
（your name替换为你的github用户名,your_email@youremail.com替换为你注册github账号时的邮箱）
2、编辑_config.yml文件： 编辑E：\hexo下的_config.yml文件（建议使用Notepad++）。在_config.yml文件的最下方，添加如下配置：
```
deploy:
    type: git
    repository: git@github.com:username/username.github.io.git
    branch: master
```
(username替换为你github的账号名称，注意：hexo的配置文件中任何":"后面都是带一个空格的，否则会报错)
3、上传：
将仓库部署到Github上，配置好_config.yml保存并关闭，为了能够使Hexo部署到GitHub上，需要安装一个插件，执行以下命令：
```
$ npm install hexo-deployer-git --save
```
然后，执行下列指令即可生成博客静态网页并完成部署：
```
$ hexo g
$ hexo d
```
如果上传成功，会显示INFO  Deploy done: git，到此，就大功告成了，在浏览器中输入username.github.io（username替换为github的仓库名），就可以看到自己的博客了。


  


  [1]: http://oevo99fcp.bkt.clouddn.com/posts/2016-10-17-1.png
  [2]: http://oevo99fcp.bkt.clouddn.com/posts/2016-10-17-2.png
  [3]: http://oevo99fcp.bkt.clouddn.com/posts/2016-10-17-3.png