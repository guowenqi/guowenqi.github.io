---
title: MarkDown语法
date: 2016-10-12 13:52:34
tags:
---

![语法学习][1]


  [1]: http://oevo99fcp.bkt.clouddn.com/07a3e8552d9ade21e30583658273c9c3.jpg
  <!-- more -->
## 二级标题：Markdown语法
  
### 第一个三级标题
  标题 #~###### 井号的个数表示几级标题，即Markdown可以表示一级标题到六级标题
  
### 第二个三级标题
  分段： 两个回车
  换行 两个空格 + 回车
  4、引用 >
  5、列表 *，+，-，1.，选其中之一，注意后面有个空格
  6、代码区块 四个空格开头
  7、链接 [文字](链接地址)
  8、图片 ! [图片说明] (图片地址)，图片地址可以是本地路劲，也可以是网络地址
  9、强调 **文字**，__文字__，_文字_，*文字*
  
### 第三个三级标题：代码高亮
``` Pyhton
@requires_authorization
class SomeClass:
    pass

if __name__ == '__main__':
    # A comment
    print 'hello world'
```

### 第四个三级标题：C++代码高亮
``` C++
 #include<stdio.h>
 
 void mian()
{
    return 0;
}
```


### 第五个三级标题：超链接
  我的博客： [点击跳转](http://www.mway.top)
