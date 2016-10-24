---
title: git-for-windows安装后不显示图标的问题
date: 2016-10-24 10:24:24
tags: [hexo]
categories: [git-for-windows]
---
## 问题表现
桌面图标与右建菜单图标，所示是未知文件的图标，如下所示：
![][1]
<!--more-->

## 解决方法
复制Git/mingw64/share/git-gui/lib/git-gui.ico图标文件，放到Git/mingw64/share/git目录下，并改名为 git-for-windows.ico
修复之后的效果：
![][2]
 
## 问题原因
可能是git的windows安装包缺少相应的图标文件


  [1]: http://oevo99fcp.bkt.clouddn.com/posts/2016-10-24-1.png
  [2]: http://oevo99fcp.bkt.clouddn.com/posts/2016-10-24-2.png