---
title: hexo+NEXT主题之博客优化
date: 2016-10-17 17:31:14
tags: [hexo]
categories: [hexo博客搭建与优化]
---
## 说明
hexo版本：3.2.2
主题：NEXT主题
主题版本：5.0.1
## 关闭换行符警告：
执行hexo d命令时，会产生警告如下：warning: LF will be replaced by CRLF
执行命令
```
git config --global core.autocrlf false
```
<!--more-->
false表示取消自动转换功能。适合纯Windows
true表示提交代码时把CRLF转换成LF，签出时LF转换成CRLF。适合多平台协作
input表示提交时把CRLF转换成LF，签出时不转换。适合纯Linux或Mac
说明：
LF为换行符，CR为回车符。Windows结束一行用CRLF，Mac和Linux用LF。Git默认在你提交时自动地把行结束符CRLF转换成LF，而在签出代码时把LF转换成CRLF
补充：
Git还提供了一个换行符检查功能core.safecrlf，可以在提交时检查文件是否混用了不同风格的换行符。可以用同样的命令更改设置。
选项如下：
false - 不做任何检查
warn - 在提交时检查并警告
true - 在提交时检查，如果发现混用则拒绝提交
建议使用最严格的 true 选项
## 设置头像：
将选中的图标文件放到your-hexo-site/themes/source/images目录下，命名为avatar.png，然后编辑站点配置文件，新增字段
```
avatar: /images/avatar.png
```
## 网站LOGO：
将选中的图标文件放到your-hexo-site/source目录下，命名为favicon.ico
## rss订阅：
执行命令
```
npm install hexo-generator-feed --save
```
编辑主题配置文件，增加字段：
```
feed:
  type: atom
  path: atom.xml
  limit: 20
  hub:
```
## 打赏功能：
将自动生成的微信收款和支付宝收款二维码图标文件放到your-hexo-site/source目录下，命名为wechatpay.png、alipay.png（分别是微信和支付宝）编辑主题配置文件，增加字段：
```
reward_comment: 坚持原创技术分享，您的支持将鼓励我继续创作！
wechatpay: /wechatpay.png
alipay: /alipay.png
```
注：代码中的中文字可随意更改

## 阅读全文按钮：
方法一：编写文章时，在文章中插入&lt;!-- more --&gt;，在哪里插入就从哪里截断

方法二：编辑主题配置文件，修改字段：
```
auto_excerpt:
  enable: false
  length: 150（可自行设置）
```
将enable设为true，之后每篇文章会自动在150处截断

## 创建标签、分类、关于页面：
执行命令：
```
hexo new  page ""
```
命令中双引号中可填tags、categories、about，该命令会在your-hexo-site/source文件夹下生成tags、categories、about三个文件夹，分别编辑三个文件夹里的文件
tags文件夹里的index.md文件加上字段：
```
type: "tags"
```
categories文件夹里的index.md文件加上字段：
```
type: "categories"
```
about文件夹里的index.md文件加上关于自己的简介，可随便填写

接着编辑主题配置文件，修改menu字段如下：
```
menu:
  home: /
  categories: /categories  
  about: /about 
  archives: /archives  
  tags: /tags
# commonweal: /404.html
```
注：如果要在这三个页面不显示多说评论，可以分别在index.md这三个文件里添加字段：
```
comments: false
```
## 多说评论：
编辑主题配置文件，修改两个字段如下：
```
duoshuo_shortname: xxx
```
注：登录多说，依次点击后台管理->设置，得到自己所设的域名，xxx.duoshuo.com
```
duoshuo_info:  
ua_enable: true 
admin_enable: true  
user_id: xxx
admin_nickname: Administrator
```
注：登录多说，依次点击个人资料->自己的昵称，查看当前网页的网址，网址最后的一长串数字就是user_id，例：http://duoshuo.com/profile/xxx/；其中xxx就是你的user_id，Administrator可随意更改

## 多说评论显示方式：
登录多说，依次点击后台管理->所管理的网站->设置，可以设置多说评论显示方式

## 多说分享功能：
编辑主题配置文件，修改字段如下：
```
duoshuo_share: true
```
## 文章阅读次数：
登录LeanCloud，依次点击昵称->控制台->创建一个新的应用，创建一个CLASS，其中CLASS的名称必须为Counter，然后点击应用Key，获得app_id 和 app_key的值，
然后编辑主题配置文件，修改字段如下：
```
leancloud_visitors:
enable: true
app_id: xxx
app_key: xxx
```
然后在LeanCloud官网，点击设置->安全中心，填写web安全域名（所建个人博客网站的网址）,填写web安全域名时，一定要填对，否则无法计数
（疑问：只有网站中文章数大于等于两篇时，才不会在首页每按一次刷新，文章阅读数量就加一的现象）

## 不蒜子统计：
方法一：
显示站点UV和站点PV值，不显示单页面PV（文章阅读数），以免和LeanCLoud统计的文章阅读数重复，编辑主题配置文件，修改字段如下：
```
busuanzi_count:
# count values only if the other configs are false 
enable: true
# custom uv span for the whole site 
site_uv: true
site_uv_header: <i class="fa fa-user"></i>
site_uv_footer:
# custom pv span for the whole site
site_pv: true 
site_pv_header: <i class="fa fa-eye"></i>
site_pv_footer:
# custom pv span for one page only
page_pv: false
page_pv_header: <i class="fa fa-file-o"></i>
page_pv_footer:
```
方法二：
主题配置文件不变，修改your-hexo-site/themes/next/layout/_partials/footer.swig文件，在文件结尾处增加如下代码：
```
&nbsp;&nbsp;|&nbsp;&nbsp;本页点击 <span id="busuanzi_value_page_pv"></span> 次
&nbsp;&nbsp;|&nbsp;&nbsp;本站总点击 <span id="busuanzi_value_site_pv"></span> 次
&nbsp;&nbsp;|&nbsp;&nbsp;您是第 <span id="busuanzi_value_site_uv"></span> 位访客
<script async src="https://dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js">
</script>
```
## 热评文章：
编辑主题配置文件，增加字段：
```
duoshuo_hotartical: true
```
## Local Search搜索：
执行命令
```
npm install hexo-generator-search --save 
```
然后编辑站点配置文件，增加字段如下：
```
search:
  	path: search.xml
  	field: post
```
再编辑字段URL，将URL设为自己网站的网址，例如：url: http://username.github.io(不能省略http)

## 部署到coding上：
1.登录coding官网，新建仓库
2.配置ssh公钥：
```
ssh-keygen -t rsa -C "your_email"
```
3.验证公钥：
```
ssh -T git@git.coding.net
```
4.验证用户：
```
$ git config --global user.name "your name"  
$ git config --global user.email "your_email@youremail.com"
```
5.编辑站点配置文件，修改deploy（部署）字段如下：
```
deploy:
  type: git
  repo: 
     github: git@github.com:username/username.github.io.git,master
     coding: git@git.coding.net:username/username.git,master
```
## 添加默认没有的个人社交链接：
编辑主题配置文件的social字段，增加你要添加的社交名称和URL，例：
```
Weibo: http://t.qq.com/guowenqi663
```
然后访问[Font Awesome](http://fontawesome.io/icons/)()(fontawesome.io)，找到喜欢的图标，记录下图标后的关键字，再编辑字段social_icons，增加你要添加的社交名称和图标关键字，例：
```
Weibo:tencent-weibo
```
## 生成站点地图：
执行命令
```
npm install hexo-generator-sitemap --save 
npm install hexo-generator-baidu-sitemap --save
```
然后编辑主题配置文件，增加字段如下：
```
sitemap:
    path: sitemap.xml
baidusitemap:
	path: baidusitemap.xml
```
## 底栏显示百度和谷歌站点地图链接：
修改your-hexo-site/themes/next/layout/_partials/footer.swig文件，增加如下代码：
```
&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;<span><a href="/sitemap.xml">Google网站地图</a></span>
&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;<span><a href="/baidusitemap.xml">百度网站地图</a></span>
```
## 百度自动推送：
修改/themes/next/layout/_partials/footer.swig文件，在文件结尾处增加如下代码：
```
<script>
(function(){
    var bp = document.createElement('script');
    var curProtocol = window.location.protocol.split(':')[0];
    if (curProtocol === 'https') {
        bp.src = 'https://zz.bdstatic.com/linksubmit/push.js';        
    }
    else {
        bp.src = 'http://push.zhanzhang.baidu.com/push.js';
    }
    var s = document.getElementsByTagName("script")[0];
    s.parentNode.insertBefore(bp, s);
})();
</script>
```
注：通过实现不蒜子统计、底栏显示百度和谷歌站点地图链接、百度自动推送三个功能对your-hexo-site/themes/next/layout/_partials/footer.swig文件的修改，footer.swig文件的最终内容为：
```
<div class="copyright" >
  {% set current = date(Date.now(), "YYYY") %}
  &copy; {% if theme.since and theme.since != current %} {{ theme.since }} - {% endif %}
  <span itemprop="copyrightYear">{{ current }}</span>
  <span class="with-love">
    <i class="fa fa-heart"></i>
  </span>
  <span class="author" itemprop="copyrightHolder">{{ config.author }}
  
&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;<span><a href="/sitemap.xml">Google网站地图</a></span>
&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;<span><a href="/baidusitemap.xml">百度网站地图</a></span>
  
  </span>
</div>

<div class="powered-by">
  {{ __('footer.powered', '<a class="theme-link" href="http://hexo.io">Hexo</a>') }}
</div>

<div class="theme-info">
  {{ __('footer.theme') }} -
  <a class="theme-link" href="https://github.com/iissnan/hexo-theme-next">
    NexT.{{ theme.scheme }}
  </a>
</div>

&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;本站总点击 <span id="busuanzi_value_site_pv"></span> 次
&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;您是第 <span id="busuanzi_value_site_uv"></span> 位访客
<script async src="https://dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js">
</script>

<script>
(function(){
    var bp = document.createElement('script');
    var curProtocol = window.location.protocol.split(':')[0];
    if (curProtocol === 'https') {
        bp.src = 'https://zz.bdstatic.com/linksubmit/push.js';        
    }
    else {
        bp.src = 'http://push.zhanzhang.baidu.com/push.js';
    }
    var s = document.getElementsByTagName("script")[0];
    s.parentNode.insertBefore(bp, s);
})();
</script>

```
## 向百度和谷歌提交站点地图：
[戳我](http://www.joryhe.com/2016-05-31-baidu_google_both_tijiao.html)
## 音乐插件：
在about页面添加音乐播放功能
登录网易云音乐，找到喜欢的歌曲，点击生成外链播放器，复制生成的代码，，编辑your-hexo-site/source/about文件夹下的index.md文件，将外链播放器代码复制进来
## hexo博客版权声明：
编辑主题配置文件，修改字段如下
```
creative_commons: by-nc-sa
```
## 最近文章：
## 图床：
## 豆瓣收藏秀：
按照第8条：创建标签、分类、关于页面，创建一个新的页面，登录豆瓣收藏秀，复制生成的豆瓣秀代码，编辑该页的index.md文件，将豆瓣秀的代码复制进来
## 首页标题的优化：
使你的网站首页标题会更符合网站名称 - 网站描述的习惯，修改your-hexo-site/themes/next/layout/index.swig文件，将下面代码：
```
{% block title %} {{ config.title }} {% endblock %}
```
更改为：
```
{% block title %} {{ config.title }} - {{ theme.description }} {% endblock %}
```
可以把关键词也显示在Title标题里，可改成：
```
{% block title %} {{ theme.keywords }} - {{ config.title }} - {{ theme.description }} {% endblock %}
```
关键词可以在主题配置文件，keywords字段填写
## 最近访客：
在关于页面添加最近访客功能，编辑your-hexo-site/source/about文件夹下的index.md文件，增加代码：
```
>最近访客
<div class="ds-recent-visitors" data-num-items="28" data-avatar-size="42" id="ds-recent-visitors"></div>
```
登录多说，后台管理->设置->基本设置->自定义CSS,在css增加代码如下：
```
#ds-recent-visitors .ds-avatar {float:left}
```
这样修改css样式，可以让最近访客图标竖着排变为按行排列
## 相册页：
hexo new page "photos",然后在your-hexo-site/source文件夹下能够找到photos文件夹，进入文件夹，编辑index.md文件，添加字段：
```
type: photos
```
然后编辑主题配置文件，在menu菜单下添加上photos页，修改如下：
```
menu:
  home: /
  categories: /categories
  about: /about
  archives: /archives
  tags: /tags
  #commonweal: /404.html
  photos: /photos
```
如果语言选择是zh-hans的话，进入your-hexo-site/themes/next/languanges文件夹，编辑zh-Hans.yml文件，在menu菜单里添加photos对应的中文名称，修改如下：
```
menu:
  home: 首页
  archives: 归档
  categories: 分类
  tags: 标签
  about: 关于
  search: 搜索
  commonweal: 公益404
  photos: 相册
```
然后为相册页在菜单下的链接添加图标，访问[Font Awesome](http://fontawesome.io/icons/)(fontawesome.io)，找到喜欢的图标，记录下图标的关键字，再编辑主题配置文件，增加photos的图标，修改menu_icons字段如下：
```
menu_icons:
  enable: true
  #KeyMapsToMenuItemKey: NameOfTheIconFromFontAwesome
  home: home
  about: user
  categories: th
  tags: tags
  archives: archive
  commonweal: heartbeat
  photos: photo
```
上传图片
编辑your-hexo-site/source/photos/index.md文件，增加代码如下：
```
{% raw %}
<style>
.photo img{
  border: 1px solid #999;
  height:150px;
  width: 150px;
}
.photo li{
    margin: 10px;
    float: left;
    list-style: none;
}
</style>

<div class="photo">
{% endraw %}

* ![](URL)
* ![](URL)
* ![](URL)

{% raw %}
</div>
{% endraw %}
```
注：URL替换为你的图片链接

