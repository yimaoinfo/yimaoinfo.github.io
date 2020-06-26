---
title: 网站怎么使用nofollow
layout: post
---
## 认知nofollow

“nofollow” 标签是Google、Yahoo和微软公司前几年一起提出的一个标签，链接加上这个标签后就不会被计算权值，搜索引擎支持nofollow属性，在很大程度上抑制博客或论坛的垃圾留言。对站长来说是一件大好事。

![nofollow](https://wx3.sinaimg.cn/large/006cjkx2ly1g0c7g0pfnaj30ch09gdfv.jpg)

nofollow是HTML元标签(meta)的content属性和链接标签(a)的rel属性的一个值，告诉机器(爬虫)无需追踪目标页，为了对抗blogspam(博客垃圾留言信息)，Google推荐使用nofollow，告诉搜索引擎爬虫无需抓取目标页，同时告诉搜索引擎无需将的当前页的Pagerank传递到目标页。但是如果你是通过sitemap直接提交该页面，爬虫还是会爬取，这里的nofollow只是当前页对目标页的一种态度，并不代表其他页对目标页的态度。
## nofollow的使用 

nofollow有两种用法： 
1.用于meta元标签：`<meta name="robots" content="nofollow" />`，告诉爬虫该页面上所有链接都无需追踪。 

```html
  1、<meta name="robots" content="index,nofllow"/>
  允许抓取本页，允许跟踪链接（逗号必须是英文状态下的逗号）
  2、 <meta name="robots" content="noindex,follow"/>
  禁止抓取本页，但允许跟踪链接
  3、<meta name="robots" content="index,nofollow"/>
  允许抓取本页，但禁止跟踪链接
  4、<meta name="robots" content="noindex,nofollow"/>
  禁止抓取本页，同时禁止跟踪本页中的链接。
     注意：使用<meta>标签时，要放置在<head></head>标签之间
     
```

2.用于a标签：`<a href="login.php" rel="nofollow">登录</a>`,告诉爬虫该页面无需追踪。

## nofollow的作用 

nofollow主要有三个作用： 
1.防止不可信的内容，最常见的是博客上的垃圾留言与评论中为了获取外链的垃圾链接，为了防止页面指向一些拉圾页面和站点。 
2.付费链接：为了防止付费链接影响Google的搜索结果排名，Google建议使用nofollow属性。 
3.引导爬虫抓取有效的页面：避免爬虫抓取一些无意义的页面，影响爬虫抓取的效率。

PR修剪(Pagerank Sculpting) 
nofollow的滥用，一些SEO为了做到搜索引擎的最大优化，通过nofollow来控制PR的流动，可以很好的优化一些特定页面。当然这种优化比较适合一些已经积淀了相当数量PR的老站点。为了防止PR修剪和nofollow的滥用，Google已经减弱了nofollow的作用，以前的nofollow不仅仅不会造成PR流动，同时不会造成PR损失，现在的nofollow规定虽然也不会造成PR流向目标页，但是原本流向的目标页的将会损失掉。比方当前页PR为1，而且页面上有10个链接，其中一个是nofollow的链接，根据先前的nofollow的规定，每个非nofollow链接指向的目标页将获得1/9的PR，含nofollow的链接不能获得PR，而根据现在Google对nofollow的新规定，非nofollow链接指向的目标页只能获得1/10，nofollow链接同样不能获得PR，也就是损失了1/10的PR。

SEO建议 
nofollow在Google的作用已经很弱，所以SEO要控制站点的PR的流动，避免链接指向垃圾页面，只能靠人工审核的方法。

先来看个例子，nofollow标签的写法： 
一个正常的A标签如下： 
代码如下:

```
<a href=“http://www.xxx.com”>xxx</a>1
```

现在我加上nofollow标签，如下： 
代码如下:

```
<a href=“http://www.xxx.com” rel=“nofollow”>xxx</a>1
```

这样就顺利的告诉蜘蛛不要对此链接进行跟踪。当不想权重输给某个外部链接，但又不得不在内容上出现该链接时，那么就可以使用这样的方式屏蔽掉。

## nofollow真面目

1、Nofollow标签限制蜘蛛爬取链接，被加上nofollow标签的外链无权重传递作用 
有些网站为了避免被页面上的外部链接分走权重，于是对出现在页面上的外部链接进行了nofollow设置，那么这样的链接就没有权重传递效果，如果还没有链接诱饵的作用(比如搜搜问问)，那么就应该果断的停止该处外链的发布，让网站管理们玩单机去吧，比如网易博客、创业吧空间。

2、Nofollow标签的有无是交换友情链接时必须考察的因素之一 
我们都知道，换友情链接并不是为了从对方网站上获得那么丁点的点击流量，而是为了提高网站权重的效果，有些站长会在友情链接部分加上nofollow标签，导致该友情链接失去了本来的意义，这种行为是属于欺骗行为，当然有些站长在和你换友情链接的时候没有nofollow标签，等到换了一段时间偷偷的加上nofollow标签，要避免这种情况就要求你隔一段时间就将和自己换友情链接的网站好好的检查一遍过去，遇到这种情况就必须果断立刻马上撤掉对方的链接。

3、Nofollow标签只是防止权重输出，并不能避免权重损失，但能引导蜘蛛的爬行 
比如当你的页面上有5个外部链接，那么每个外部链接得到的权重为1/5，而你在其中的一个外部链接上添加了nofollow标签，使得蜘蛛不爬取这一个链接，那么剩余的4个外部链接得到的权重一样还是1/5，页面的权重一样会分给这5个链接，只是其中被设置了nofollow标签的链接所获得的权重是丢失而没有形成传递，这看似是一种“损人不利己”的行为，但是也有好处的，这样可以引导蜘蛛的爬行，让有带宽限制的蜘蛛在有限的时间，爬取到更多的页面。

4、Nofollow 和 External nofollow 
从字面上意思来看，nofollow是“不要追踪”，而extenal nofollow 则是“外部的不要追踪”，也许你已经看出来了，他们两根本就是同一个意思，external nofollow 只是nofollow比较规范的书写而已，不用纠结，他们是一个意思!

Nofollow标签还可以运用于很多地方，比如wordpress文章评论部分的运用，还有为了用户体验而引进的一些外部链接上的使用等等。Nofollow是一把双刃剑，需要花点时间去琢磨。

## nofollow插件

如何去安装nofllow插件？（以chrome浏览器为例）,打开chrome浏览器-点击扩展-更多扩展-打开了chrome应用市场，搜nofllow-安装添加