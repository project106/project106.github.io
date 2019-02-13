## 简介

本文仅适用于Blog基于Github Repo的基础维护。如有高级需求，请联系手头的程序员(**人选只应该有一个, which is me😈**)。

## 使用

* 开始
	* [环境](#环境)
	* [开始](#开始)
	* [撰写博文](#撰写博文)
* 组件
	* [侧边栏](#侧边栏)
	* [迷你关于我](#mini-about-me)
	* [推荐标签](#featured-tags)
	* [好友链接](#friends)
	* [HTML5 演示文档布局](#keynote-layout)
* 评论
	* [评论](#comment)
* 高级部分
	* [标题底图](#header-image)


### 开始

可以通用修改 `_config.yml`文件来搭建博客配置:

```
# Site settings
title: Y&J              # 博客网站标题
SEOTitle:		# SEO 标题
description: "Hey"      # 随便说点，描述一下

# SNS settings      
github_username:        # github账号
jianshu_username:       # 简书ID。

# Build settings
# paginate: 10          # 一页准备放几篇文章
```

Jekyll官方网站还有很多的参数可以调，比如设置文章的链接形式...网址在这里：[Jekyll - Official Site](http://jekyllrb.com/) 中文版的在这里：[Jekyll中文](http://jekyllcn.com/).

### 撰写博文

要发表的文章一般以 **Markdown** 的格式放在这里`_posts/`，模板如下。

yaml 头文件长这样:

```
---
layout:     post
title:      Dummy title
subtitle:   Dummy title
date:       2016-12-13
author:     
header-img: img/realImg.jpg
catalog: 	 true
tags:
    - DummyTag
---

```

### 侧边栏
设置是在 `_config.yml`文件里面的`Sidebar settings`那块。

```
# Sidebar settings
sidebar: true              # 添加侧边栏
sidebar-about-description: "简单的描述"
sidebar-avatar:            # 大头贴，请使用绝对地址.注意：名字区分大小写！后缀名也是
```

侧边栏是响应式布局的，当屏幕尺寸小于992px的时候，侧边栏就会移动到底部。具体请见bootstrap栅格系统 <http://v3.bootcss.com/css/>

### Featured Tags

这个模块现在是独立的，可以呈现在所有页面，包括主页和发表的每一篇文章标题的头上。

```
# Featured Tags
featured-tags: true  
featured-condition-size: 1     # A tag will be featured if the size of it is more than this condition value
```

唯一需要注意的是`featured-condition-size`: 如果一个标签的 SIZE，也就是使用该标签的文章数大于上面设定的条件值，这个标签就会在首页上被推荐。
 
内部有一个条件模板 `{% if tag[1].size > {{site.featured-condition-size}} %}` 是用来做筛选过滤的.

### Social-media Account

在下面输入的社交账号，没有的添加的不会显示在侧边框中。

	# SNS settings
	RSS: false
	zhihu_username:     username
	facebook_username:  username
	github_username:    username
	# weibo_username:   username
	


### Friends

好友链接部分。这会在全部页面显示。

设置是在 `_config.yml`文件里面的`Friends`。

```
# Friends
friends: [
    {
        title: "Dummy Title",
        href: "https://dummy.url/"
    }
]
```


### Keynote Layout

HTML5幻灯片的排版：

![](https://camo.githubusercontent.com/f30347a118171820b46befdf77e7b7c53a5641a9/687474703a2f2f6875616e677875616e2e6d652f696d672f626c6f672d6b65796e6f74652e6a7067)

这部分是用于占用html格式的幻灯片的，一般用到的是 Reveal.js, Impress.js, Slides, Prezi 等等.我认为一个现代化的博客怎么能少了放html幻灯的功能呢~

其主要原理是添加一个 `iframe`，在里面加入外部链接。可以直接写到头文件里面去，详情请见下面的yaml头文件的写法。

```
---
layout:     keynote
iframe:     "http://huangxuan.me/js-module-7day/"
---
```

iframe在不同的设备中，将会自动的调整大小。保留内边距是为了让手机用户可以向下滑动，以及添加更多的内容。


### Comment

博客支持 [Gitalk](https://gitalk.github.io/) 评论系统，[支持 Markdwon 语法](https://guides.github.com/features/mastering-markdown/)

但是需要手动创建评论栏。

### Header Image

博客每页的标题底图可以自选，详情可以参照已有的post。

> 上传的图片最好先压缩，这里推荐 imageOptim 图片压缩软件，让你的博客起飞。

但是需要注意的是本模板的标题是**白色**的，所以背景色要设置为**灰色**或者**黑色**，总之深色系就对了。当然还可以自定义修改字体颜色，总之，用github pages就是可以完全的个性定制自己的博客。
