﻿---
title: hexo+多说评论自定义CSS效果
date: 2016-10-17 17:08:04
tags: [hexo]
categories: [hexo博客搭建与优化]
---
进入[多说](http://duoshuo.com/)官网（duoshuo.com），登录账号，依次点击后台管理->设置，找到自定义CSS，将下面九段代码中的任意一段复制到自定义CSS文本框，即可实现多说评论的美化。
<!--more-->
## 效果一：
```
#ds-reset .ds-avatar img,#ds-reset .ds-avatar img:hover{ -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both;
-ms-animation-fill-mode: both; -o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s;
-moz-animation-duration: 0s; -ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s;
-webkit-animation-duration: 1s; -moz-animation-duration: 1s; -ms-animation-duration: 1s; -o-animation-duration: 1s;
animation-duration: 1s; } @-webkit-keyframes rotateInDownLeft { 0% { -webkit-transform-origin: left bottom; -webkit-transform:
rotate(-90deg); opacity: 0; } 100% { -webkit-transform-origin: left bottom; -webkit-transform: rotate(0); opacity: 1; } }
@-moz-keyframes rotateInDownLeft { 0% { -moz-transform-origin: left bottom; -moz-transform: rotate(-90deg); opacity: 0; } 100% {
-moz-transform-origin: left bottom; -moz-transform: rotate(0); opacity: 1; } } @-o-keyframes rotateInDownLeft { 0% {
-o-transform-origin: left bottom; -o-transform: rotate(-90deg); opacity: 0; } 100% { -o-transform-origin: left bottom; -o-transform:
rotate(0); opacity: 1; } } @keyframes rotateInDownLeft { 0% { transform-origin: left bottom; transform: rotate(-90deg); opacity: 0; }
100% { transform-origin: left bottom; transform: rotate(0); opacity: 1; } } #ds-reset .ds-avatar img{ -webkit-animation-name:
rotateInDownLeft; -moz-animation-name: rotateInDownLeft; -o-animation-name: rotateInDownLeft; animation-name: rotateInDownLeft; }
#ds-reset .ds-avatar img:hover{ -webkit-animation-name: rotateOutDownLeft; -moz-animation-name: rotateOutDownLeft; -o-animation-name:
rotateOutDownLeft; animation-name: rotateOutDownLeft; } @-webkit-keyframes rotateOutDownLeft { 0% { -webkit-transform-origin: left
bottom; -webkit-transform: rotate(0); opacity: 1; } 100% { -webkit-transform-origin: left bottom; -webkit-transform: rotate(90deg);
opacity: 0; } } @-moz-keyframes rotateOutDownLeft { 0% { -moz-transform-origin: left bottom; -moz-transform: rotate(0); opacity: 1; }
100% { -moz-transform-origin: left bottom; -moz-transform: rotate(90deg); opacity: 0; } } @-o-keyframes rotateOutDownLeft { 0% {
-o-transform-origin: left bottom; -o-transform: rotate(0); opacity: 1; } 100% { -o-transform-origin: left bottom; -o-transform:
rotate(90deg); opacity: 0; } } @keyframes rotateOutDownLeft { 0% { transform-origin: left bottom; transform: rotate(0); opacity: 1; }
100% { transform-origin: left bottom; transform: rotate(90deg); opacity: 0; } }
```
## 效果二：
```
#ds-reset .ds-avatar img,#ds-reset .ds-avatar img:hover{ -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both;
-ms-animation-fill-mode: both; -o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s;
-moz-animation-duration: 0s; -ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s;
-webkit-animation-duration: 0.7s; -moz-animation-duration: 0.7s; -ms-animation-duration: 0.7s; -o-animation-duration: 0.7s;
animation-duration: 0.7s; } @-webkit-keyframes bounceIn { 0% { opacity: 0; -webkit-transform: scale(.3); } 50% { opacity: 1;
-webkit-transform: scale(1.05); } 70% { -webkit-transform: scale(.9); } 100% { -webkit-transform: scale(1); } } @-moz-keyframes
bounceIn { 0% { opacity: 0; -moz-transform: scale(.3); } 50% { opacity: 1; -moz-transform: scale(1.05); } 70% { -moz-transform:
scale(.9); } 100% { -moz-transform: scale(1); } } @-o-keyframes bounceIn { 0% { opacity: 0; -o-transform: scale(.3); } 50% { opacity:
1; -o-transform: scale(1.05); } 70% { -o-transform: scale(.9); } 100% { -o-transform: scale(1); } } @keyframes bounceIn { 0% {
opacity: 0; transform: scale(.3); } 50% { opacity: 1; transform: scale(1.05); } 70% { transform: scale(.9); } 100% { transform:
scale(1); } } #ds-reset .ds-avatar img { -webkit-animation-name: bounceIn; -moz-animation-name: bounceIn; -o-animation-name:
bounceIn; animation-name: bounceIn; } @-webkit-keyframes bounceOut { 0% { -webkit-transform: scale(1); } 25% { -webkit-transform:
scale(.95); } 50% { opacity: 1; -webkit-transform: scale(1.1); } 100% { opacity: 0; -webkit-transform: scale(.3); } } @-moz-keyframes
bounceOut { 0% { -moz-transform: scale(1); } 25% { -moz-transform: scale(.95); } 50% { opacity: 1; -moz-transform: scale(1.1); } 100%
{ opacity: 0; -moz-transform: scale(.3); } } @-o-keyframes bounceOut { 0% { -o-transform: scale(1); } 25% { -o-transform: scale(.95);
} 50% { opacity: 1; -o-transform: scale(1.1); } 100% { opacity: 0; -o-transform: scale(.3); } } @keyframes bounceOut { 0% {
transform: scale(1); } 25% { transform: scale(.95); } 50% { opacity: 1; transform: scale(1.1); } 100% { opacity: 0; transform:
scale(.3); } } #ds-reset .ds-avatar img:hover{ -webkit-animation-name: bounceOut; -moz-animation-name: bounceOut; -o-animation-name:
bounceOut; animation-name: bounceOut; }
```
## 效果三：
```
#ds-reset .ds-avatar img,#ds-reset .ds-avatar img:hover{ -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both;
-ms-animation-fill-mode: both; -o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s;
-moz-animation-duration: 0s; -ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s;
-webkit-animation-duration: 0.7s; -moz-animation-duration: 0.7s; -ms-animation-duration: 0.7s; -o-animation-duration: 0.7s;
animation-duration: 0.7s; } @-webkit-keyframes rotateIn { 0% { -webkit-transform-origin: center center; -webkit-transform:
rotate(-150deg); opacity: 0; } 100% { -webkit-transform-origin: center center; -webkit-transform: rotate(0); opacity: 1; } }
@-moz-keyframes rotateIn { 0% { -moz-transform-origin: center center; -moz-transform: rotate(-150deg); opacity: 0; } 100% {
-moz-transform-origin: center center; -moz-transform: rotate(0); opacity: 1; } } @-o-keyframes rotateIn { 0% { -o-transform-origin:
center center; -o-transform: rotate(-150deg); opacity: 0; } 100% { -o-transform-origin: center center; -o-transform: rotate(0);
opacity: 1; } } @keyframes rotateIn { 0% { transform-origin: center center; transform: rotate(-150deg); opacity: 0; } 100% {
transform-origin: center center; transform: rotate(0); opacity: 1; } } #ds-reset .ds-avatar img{ -webkit-animation-name: rotateIn;
-moz-animation-name: rotateIn; -o-animation-name: rotateIn; animation-name: rotateIn; } @-webkit-keyframes rotateOut { 0% {
-webkit-transform-origin: center center; -webkit-transform: rotate(0); opacity: 1; } 100% { -webkit-transform-origin: center center;
-webkit-transform: rotate(150deg); opacity: 0; } } @-moz-keyframes rotateOut { 0% { -moz-transform-origin: center center;
-moz-transform: rotate(0); opacity: 1; } 100% { -moz-transform-origin: center center; -moz-transform: rotate(150deg); opacity: 0; } }
@-o-keyframes rotateOut { 0% { -o-transform-origin: center center; -o-transform: rotate(0); opacity: 1; } 100% { -o-transform-origin:
center center; -o-transform: rotate(150deg); opacity: 0; } } @keyframes rotateOut { 0% { transform-origin: center center; transform:
rotate(0); opacity: 1; } 100% { transform-origin: center center; transform: rotate(150deg); opacity: 0; } } #ds-reset .ds-avatar
img:hover{ -webkit-animation-name: rotateOut; -moz-animation-name: rotateOut; -o-animation-name: rotateOut; animation-name:
rotateOut; }
```
## 效果四：
```
#ds-reset .ds-avatar img,#ds-reset .ds-avatar img:hover{ -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both;
-ms-animation-fill-mode: both; -o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s;
-moz-animation-duration: 0s; -ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s;
-webkit-animation-duration: 0.7s; -moz-animation-duration: 0.7s; -ms-animation-duration: 0.7s; -o-animation-duration: 0.7s;
animation-duration: 0.7s; } @-webkit-keyframes rollIn { 0% { opacity: 0; -webkit-transform: translateX(-100%) rotate(-120deg); } 100%
{ opacity: 1; -webkit-transform: translateX(0px) rotate(0deg); } } @-moz-keyframes rollIn { 0% { opacity: 0; -moz-transform:
translateX(-100%) rotate(-120deg); } 100% { opacity: 1; -moz-transform: translateX(0px) rotate(0deg); } } @-o-keyframes rollIn { 0% {
opacity: 0; -o-transform: translateX(-100%) rotate(-120deg); } 100% { opacity: 1; -o-transform: translateX(0px) rotate(0deg); } }
@keyframes rollIn { 0% { opacity: 0; transform: translateX(-100%) rotate(-120deg); } 100% { opacity: 1; transform: translateX(0px)
rotate(0deg); } } #ds-reset .ds-avatar img{ -webkit-animation-name: rollIn; -moz-animation-name: rollIn; -o-animation-name: rollIn;
animation-name: rollIn; } @-webkit-keyframes rollOut { 0% { opacity: 1; -webkit-transform: translateX(0px) rotate(0deg); } 100% {
opacity: 0; -webkit-transform: translateX(100%) rotate(120deg); } } @-moz-keyframes rollOut { 0% { opacity: 1; -moz-transform:
translateX(0px) rotate(0deg); } 100% { opacity: 0; -moz-transform: translateX(100%) rotate(120deg); } } @-o-keyframes rollOut { 0% {
opacity: 1; -o-transform: translateX(0px) rotate(0deg); } 100% { opacity: 0; -o-transform: translateX(100%) rotate(120deg); } }
@keyframes rollOut { 0% { opacity: 1; transform: translateX(0px) rotate(0deg); } 100% { opacity: 0; transform: translateX(100%)
rotate(120deg); } } #ds-reset .ds-avatar img:hover{ -webkit-animation-name: rollOut; -moz-animation-name: rollOut; -o-animation-name:
rollOut; animation-name: rollOut; }
```
## 效果五：
```
#ds-reset .ds-avatar img,#ds-reset .ds-avatar img:hover{ -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both;
-ms-animation-fill-mode: both; -o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s;
-moz-animation-duration: 0s; -ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s;
-webkit-animation-duration: 0.7s; -moz-animation-duration: 0.7s; -ms-animation-duration: 0.7s; -o-animation-duration: 0.7s;
animation-duration: 0.7s; } @-webkit-keyframes swing { 20%, 40%, 60%, 80%, 100% { -webkit-transform-origin: top center; } 20% {
-webkit-transform: rotate(15deg); } 40% { -webkit-transform: rotate(-10deg); } 60% { -webkit-transform: rotate(5deg); } 80% {
-webkit-transform: rotate(-5deg); } 100% { -webkit-transform: rotate(0deg); } } @-moz-keyframes swing { 20% { -moz-transform:
rotate(15deg); } 40% { -moz-transform: rotate(-10deg); } 60% { -moz-transform: rotate(5deg); } 80% { -moz-transform: rotate(-5deg); }
100% { -moz-transform: rotate(0deg); } } @-o-keyframes swing { 20% { -o-transform: rotate(15deg); } 40% { -o-transform:
rotate(-10deg); } 60% { -o-transform: rotate(5deg); } 80% { -o-transform: rotate(-5deg); } 100% { -o-transform: rotate(0deg); } }
@keyframes swing { 20% { transform: rotate(15deg); } 40% { transform: rotate(-10deg); } 60% { transform: rotate(5deg); } 80% {
transform: rotate(-5deg); } 100% { transform: rotate(0deg); } } #ds-reset .ds-avatar img:hover{ -webkit-transform-origin: top center;
-moz-transform-origin: top center; -o-transform-origin: top center; transform-origin: top center; -webkit-animation-name: swing;
-moz-animation-name: swing; -o-animation-name: swing; animation-name: swing; }
```
## 效果六：
```
#ds-reset .ds-avatar img,#ds-reset .ds-avatar img:hover{ -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both;
-ms-animation-fill-mode: both; -o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s;
-moz-animation-duration: 0s; -ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s;
-webkit-animation-duration: 0.7s; -moz-animation-duration: 0.7s; -ms-animation-duration: 0.7s; -o-animation-duration: 0.7s;
animation-duration: 0.7s; } @-webkit-keyframes pulse { 0% { -webkit-transform: scale(1); } 50% { -webkit-transform: scale(1.1); }
100% { -webkit-transform: scale(1); } } @-moz-keyframes pulse { 0% { -moz-transform: scale(1); } 50% { -moz-transform: scale(1.1); }
100% { -moz-transform: scale(1); } } @-o-keyframes pulse { 0% { -o-transform: scale(1); } 50% { -o-transform: scale(1.1); } 100% {
-o-transform: scale(1); } } @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.1); } 100% { transform: scale(1);
} } #ds-reset .ds-avatar img:hover { -webkit-animation-name: pulse; -moz-animation-name: pulse; -o-animation-name: pulse;
animation-name: pulse; }
```
## 效果七：
```
#ds-reset .ds-avatar img,#ds-reset .ds-avatar img:hover{ -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both;
-ms-animation-fill-mode: both; -o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s;
-moz-animation-duration: 0s; -ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s; 
-webkit-animation-duration: 0.7s; -moz-animation-duration: 0.7s; -ms-animation-duration: 0.7s; -o-animation-duration: 0.7s; 
animation-duration: 0.7s; } @-webkit-keyframes wobble { 0% { -webkit-transform: translateX(0%); } 15% { -webkit-transform: 
translateX(-25%) rotate(-5deg); } 30% { -webkit-transform: translateX(20%) rotate(3deg); } 45% { -webkit-transform: translateX(-15%) 
rotate(-3deg); } 60% { -webkit-transform: translateX(10%) rotate(2deg); } 75% { -webkit-transform: translateX(-5%) rotate(-1deg); } 
100% { -webkit-transform: translateX(0%); } } @-moz-keyframes wobble { 0% { -moz-transform: translateX(0%); } 15% { -moz-transform: 
translateX(-25%) rotate(-5deg); } 30% { -moz-transform: translateX(20%) rotate(3deg); } 45% { -moz-transform: translateX(-15%) 
rotate(-3deg); } 60% { -moz-transform: translateX(10%) rotate(2deg); } 75% { -moz-transform: translateX(-5%) rotate(-1deg); } 100% { 
-moz-transform: translateX(0%); } } @-o-keyframes wobble { 0% { -o-transform: translateX(0%); } 15% { -o-transform: translateX(-25%) 
rotate(-5deg); } 30% { -o-transform: translateX(20%) rotate(3deg); } 45% { -o-transform: translateX(-15%) rotate(-3deg); } 60% { 
-o-transform: translateX(10%) rotate(2deg); } 75% { -o-transform: translateX(-5%) rotate(-1deg); } 100% { -o-transform: 
translateX(0%); } } @keyframes wobble { 0% { transform: translateX(0%); } 15% { transform: translateX(-25%) rotate(-5deg); } 30% { 
transform: translateX(20%) rotate(3deg); } 45% { transform: translateX(-15%) rotate(-3deg); } 60% { transform: translateX(10%) 
rotate(2deg); } 75% { transform: translateX(-5%) rotate(-1deg); } 100% { transform: translateX(0%); } } #ds-reset .ds-avatar 
img:hover{ -webkit-animation-name: wobble; -moz-animation-name: wobble; -o-animation-name: wobble; animation-name: wobble; }
```
## 效果八：
```
#ds-reset .ds-avatar img{ width:54px;height:54px; /*设置图像的长和宽，这里要根据自己的评论框情况更改*/ border-radius: 
27px;/*设置图像圆角效果,在这里我直接设置了超过width/2的像素，即为圆形了*/ -webkit-border-radius: 27px;/*圆角效果：兼容webkit浏览器*/
-moz-border-radius:27px; box-shadow: inset 0 -1px 0 #3333sf;/*设置图像阴影效果*/ -webkit-box-shadow: inset 0 -1px 0 #3333sf; 
-webkit-transition: 0.4s; -webkit-transition: -webkit-transform 0.4s ease-out; transition: transform 0.4s 
ease-out;/*变化时间设置为0.4秒(变化动作即为下面的图像旋转360读）*/ -moz-transition: -moz-transform 0.4s ease-out; } #ds-reset 
.ds-avatar img:hover{/*设置鼠标悬浮在头像时的CSS样式*/ box-shadow: 0 0 10px #fff; rgba(255,255,255,.6), inset 0 0 20px 
rgba(255,255,255,1); -webkit-box-shadow: 0 0 10px #fff; rgba(255,255,255,.6), inset 0 0 20px rgba(255,255,255,1); transform: 
rotateZ(360deg);/*图像旋转360度*/ -webkit-transform: rotateZ(360deg); -moz-transform: rotateZ(360deg); }
```
## 效果九：
```
#ds-reset .ds-avatar img:hover { -webkit-animation-fill-mode: both; -moz-animation-fill-mode: both; -ms-animation-fill-mode: both; 
-o-animation-fill-mode: both; animation-fill-mode: both; -webkit-animation-duration: 0s; -moz-animation-duration: 0s; 
-ms-animation-duration: 0s; -o-animation-duration: 0s; animation-duration: 0s; -webkit-animation-duration: 1s; 
-moz-animation-duration: 1s; -ms-animation-duration: 1s; -o-animation-duration: 1s; animation-duration: 1s; -webkit-transform-style: 
preserve-3d; -moz-transform-style: preserve-3d; -o-transform-style: preserve-3d; transform-style: preserve-3d; 
-webkit-backface-visibility: visible !important; -webkit-animation-name: flip; -moz-backface-visibility: visible !important; 
-moz-animation-name: flip; -o-backface-visibility: visible !important; -o-animation-name: flip; backface-visibility: visible 
!important; animation-name: flip; } @-webkit-keyframes flip { 0% {-webkit-transform: perspective(400px) 
rotateY(0);-webkit-animation-timing-function: ease-out;} 40% {-webkit-transform: perspective(400px) translateZ(150px) 
rotateY(170deg);-webkit-animation-timing-function: ease-out;} 50% {-webkit-transform: perspective(400px) translateZ(150px) 
rotateY(190deg) scale(1);-webkit-animation-timing-function: ease-in;} 80% {-webkit-transform: perspective(400px) rotateY(360deg) 
scale(.95);-webkit-animation-timing-function: ease-in;} 100% {-webkit-transform: perspective(400px) 
scale(1);-webkit-animation-timing-function: ease-in;} } @-moz-keyframes flip { 0% {-moz-transform: perspective(400px) 
rotateY(0);-moz-animation-timing-function: ease-out;} 40% {-moz-transform: perspective(400px) translateZ(150px) 
rotateY(170deg);-moz-animation-timing-function: ease-out;} 50% {-moz-transform: perspective(400px) translateZ(150px) rotateY(190deg)
scale(1);-moz-animation-timing-function: ease-in;} 80% {-moz-transform: perspective(400px) rotateY(360deg) 
scale(.95);-moz-animation-timing-function: ease-in;} 100% {-moz-transform: perspective(400px) 
scale(1);-moz-animation-timing-function: ease-in;} } @-o-keyframes flip { 0% {-o-transform: perspective(400px) 
rotateY(0);-o-animation-timing-function: ease-out;} 40% {-o-transform: perspective(400px) translateZ(150px) 
rotateY(170deg);-o-animation-timing-function: ease-out;} 50% {-o-transform: perspective(400px) translateZ(150px) rotateY(190deg) 
scale(1);-o-animation-timing-function: ease-in;} 80% {-o-transform: perspective(400px) rotateY(360deg) scale(.95); 
-o-animation-timing-function: ease-in;} 100% {-o-transform: perspective(400px) scale(1);-o-animation-timing-function: ease-in;} } 
@keyframes flip { 0% {transform: perspective(400px) rotateY(0);animation-timing-function: ease-out;} 40% {transform: 
perspective(400px) translateZ(150px) rotateY(170deg);animation-timing-function: ease-out;} 50% {transform: perspective(400px) 
translateZ(150px) rotateY(190deg) scale(1);animation-timing-function: ease-in;} 80% {transform: perspective(400px) rotateY(360deg)
scale(.95);animation-timing-function: ease-in;} 100% {transform: perspective(400px) scale(1);animation-timing-function: ease-in;} }
```
## 我的CSS
这是我的博客目前使用的CSS代码，如果你喜欢，直接拿去用吧
```
#ds-reset .ds-avatar img,
#ds-recent-visitors .ds-avatar img
{

width:54px;height:54px; /*设置图像的长和宽，这里要根据自己的评论框情况更改*/ 
border-radius: 27px;/*设置图像圆角效果,在这里我直接设置了超过width/2的像素，即为圆形了*/ 
-webkit-border-radius: 27px;/*圆角效果：兼容webkit浏览器*/ 
-moz-border-radius:27px; box-shadow: inset 0 -1px 0 #3333sf;/*设置图像阴影效果*/ 
-webkit-box-shadow: inset 0 -1px 0 #3333sf; 
-webkit-transition: 0.4s; 
-webkit-transition: 
-webkit-transform 0.4s ease-out; 
transition: transform 0.4s ease-out;/*变化时间设置为0.4秒(变化动作即为下面的图像旋转360读）*/ 
-moz-transition: -moz-transform 0.4s ease-out;
}

/*设置鼠标悬浮在头像时的CSS样式*/
#ds-reset .ds-avatar img:hover,
#ds-recent-visitors .ds-avatar img:hover
{
box-shadow: 0 0 10px #fff;
rgba(255,255,255,.6), inset 0 0 20px rgba(255,255,255,1);
-webkit-box-shadow: 0 0 10px #fff;
rgba(255,255,255,.6), inset 0 0 20px rgba(255,255,255,1);
transform: rotateZ(360deg);/*图像旋转360度*/
-webkit-transform: rotateZ(360deg);
-moz-transform: rotateZ(360deg);
}

/*最近访客头像竖着排，改成排成一列*/
#ds-recent-visitors .ds-avatar {float:left}

/*自定义评论框内的颜色，字体，大小*/
#ds-thread #ds-reset .ds-textarea-wrapper textarea, #ds-thread #ds-reset .ds-textarea-wrapper .ds-hidden-text 
{
font-family: ‘微软雅黑’ ‘Microsoft Yahei’!important;
font-size:15px;
letter-spacing:1px;
}

/*评论框整体的背景色*/
#ds-thread {background: #ffffff;}

/*评论框背景
#ds-thread #ds-reset .ds-textarea-wrapper textarea 
{
background: url(请填写背景图链接) right no-repeat;
}
*/

/*自定义发布按钮字体和渐变颜色*/
#ds-thread #ds-reset .ds-post-button
{
font-family: ‘微软雅黑’‘Microsoft Yahei’!important;
font-weight: bold;
font-size:12px;
background:none !important;
color:#49976b !important;
}
```
说明：
最近访客头像css样式和评论css样式统一设置，代码布局如下：
```
#ds-reset .ds-avatar img,#ds-recent-visitors .ds-avatar img
{
在这里定义你的多说头像样式css
}
```
最近访客头像css样式和评论css样式分开设置，代码布局如下：
```
#ds-reset .ds-avatar img
{
在这里定义你的多说评论头像样式
}

#ds-recent-visitors .ds-avatar img
{
在这里定义你的多说最近访客头像css样式
}
```
