---
layout: post
title: 如何建立Github Pages自己的博客
categories: GitHub
description: 如何傻瓜式建立自己的github pages博客
keywords: GitHub Pages,GitHub
---
## 前言
写博客的地方很多，比如CSDN、简书等等。但是Github Pages可以定制下自己博客的外观，随心随意，github有很多很多开源优秀项目，可以学习，自己的博客还可以装逼啊。

### 1.在github创建一个仓库
```
    用户名.github.io
```
仓库的名字必须是 `githubname.github.io `

例如(我的github名mojingman)：`mojingman.github.io`

### 2.下载仓库到本地

(1)先下载GitHubDesktopSetup.exe

[GitHubDesktopSetup下载](https://desktop.githubusercontent.com/releases/1.5.0-2f0c701f/GitHubDesktopSetup.exe) 完成之后安装登录自己的github账号

(2)`clone`刚刚创建的仓库到本地

![clone-code](/images/posts/github/clone-code.png)


### 3.找自己喜欢的博客模板

 [github page官方建站指导](https://pages.github.com)介绍要让自己的博客变的很漂亮可以使用[Jekyll](https://jekyllrb.com/)，[了解如何设置Jekyll](https://jekyllrb.com/docs/)。

我比较懒，没有去自己从头配置Jekyll，然后直接用的别人配置好的。你可以在github上搜索下jekyll page，有很多很好看的模板，你可以`fork`到自己的github.我用的模板是[码志](https://github.com/mzlogin/mzlogin.github.io)

### 4.替换代码

* `fork`别人的模板仓库到自己github之后下载到本地(过程和第2步一样)。

![](/images/posts/github/fork-code)

* 把fork模板仓库的所有的文件夹复制到自己创建的仓库

* 通过github客户端提交代码到 github 

![commit-code](/images/posts/github/push-code)

* 访问`name.github.io`,例如 [mojingman.github.io](mojingman.github.io)看自己所用模板


### 5.修改信息以及配置
  
上面的步骤只是把别人的模板拿过来自己用，但是里面所有的数据都是别人，要修改成自己的数据或者自己配置，根据你所应用模板的文件夹具体修改，我这里只说明我所有模板的修改。

`_data` 文件夹下三个文件分别对应博客页面链接、关于的类容，可以通过TXT等工具打开直接修改成自己的信息，可以增加删除相关数据

`_drafts`文件夹下是博客草稿

`_includes`博客页面头和脚公共的主要布局，html自己有兴趣可以进行修改

`_layouts`对应博客首页、分类、维基、链接、关于页面的布局

`_posts`自己博客基本上全在这个文件夹，除了`template.md`文件其他文件都可以删除，因为其他都是别人的博客

`_wiki`维基页面的博客都在此文件夹下

`assets\images`文件下有个二维码可以换成自己的

`images`博客里面的图片以及图片资源都在此文件夹下

`pages`博客页面显示内容在此文件夹下，可以修改成自己的信息

`favicon.ico`网站 logo，可以换成自己的

`_config.yml`整个博客的主要配置文件

小结: 主要要修改的文件有：

①`_data`下所有文件

②`assets\images`二维码图片

③`_includes/sidebar-qrcode.html`文件第一行代码：`{% if site.url contains 'mojingman.github.io' %}`中的`mojingman.github.io`修改成自己的

④`pages` 页面显示内容可以修改成自己想要显示的文字，主要修改`about.md`文件，其他看自己

⑤`_config.yml`里`Main Configs、Author` 全部修改成自己的信息。

**评论模块：** 目前支持 disqus、gitment 和 gitalk，选用其中一种就可以了，推荐使用 gitalk。我用的是 gitalk , Gitalk 需要一个 Github Application，[点击这里申请](https://github.com/settings/applications/new)。
![](/images/posts/github/register-blog)
点击创建

获取` Client ID` 和 `Client Secret`
![](/images/posts/github/show-bolg.png)

修改`_config.yml`下 Comments内容

```
    gitalk:
    owner: mojingman
    repo: mojingman.github.io
    clientID: Client ID
    clientSecret: Client Secret
```
**注意: ** owner 是你的 name，repo 是你博客仓库名，若果你不做评论模块修改，那用的评论就是我的。

要删除 `posts`,`_drafts`,`_wiki`,images文件夹下除了 template.md 以外的所有文件，然后添加你自己的内容，该删除的删除，该修改的修改全部完成之后，上传所有的代码，如何上传代码上面有讲，至此所有配置完成了。这个个人微博搭建是在别人的模板基础上进行的，没有去看 Jekyll 的配置。你们有兴趣可以自己学习，傻瓜教程。

**[在线预览 &rarr;](https://mojingman.github.io)**

## 怎么写博客

通过Markdown编辑器,网上找了很多编辑器比较好的一款是MarkdownPad，[点击此处下载资源](http://www.markdownpad.com/download.html)