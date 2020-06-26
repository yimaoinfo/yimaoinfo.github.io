---
title: 如何禁止搜索引擎转码
layout: post
---
## 禁止百度搜索转码

　　方法一：在网页头部的`<head>`标签中添加

```html
<meta http-equiv="Cache-Control" content="no-transform" />
```

，该代码是百度的转码声明中提供的，如果不想使用百度在移动浏览器上面的转码的话，可以使用这段代码禁止百度搜索转码。

​	方法二 :HTTP Response中显式声明Cache-control为no-transform

　　方法三：在百度站长平台添加移动适配规则，那么百度搜索结果跳转就会按照移动适配规则来跳转。

## 禁止神马搜索转码

　　方法一：在网页头部的`<head>`标签中添加

```html
<meta http-equiv="Cache-Control" content="no-siteapp" />
```

，该代码是神马的转码声明中提供的，使用代码可以禁止神马搜索转码，代码完全是学习百度的。

​	方法二: HTTP Response中显式声明Cache-control为no-siteapp

　　方法三：在神马站长平台添加移动适配规则，可能大多数站长只知道百度站长平台，其实神马搜索引擎也早就推出了站长平台的。

## 禁止搜狗、好搜搜索转码

　　之所以要把搜狗、好搜放在一起说，就是因为这两个搜索引擎都没有禁止转码的代码，只能通过站长平台的移动适配来确保不被转码。

　　方法：登录各自的站长平台，在站长平台中添加移动适配规则即可。

## 移动适配

  搜索引擎转码是因为页面url指向pc端和移动端不能适配，移动适配提升搜索用户在百度移动搜索的检索体验,会给对应PC页面的手机页面在搜索结果处有更多的展现机会,需要站点向搜索引擎提交主体内容相同的PC页面与移动页面的对应关系,即为移动适配。 
  为此，搜索引擎站长平台提供“移动适配”服务， 
   如果您同时拥有PC站和手机站，且二者能够在内容上对应，即主体内容完全相同，您可以通过移动适配工具进行对应关系提交。 
   站长通过移动适配工具提交pattern级别或者url级别的PC页与手机页对应关系，若可以成功通过校验，将有助于移动搜索将移动用户直接送入对应的手机页结果。积极参与“移动适配”，将有助于您的手机站在移动搜索获得更多流量,同时以更佳的浏览效果赢取用户口碑。

### 百度

**标注Meta声明**
　　站点如果自行适配有困难，可以在PC页面中做简单改造，百度协助实现适配效果。即：站长在站点PC页的源代码头部嵌入一行或多行Meta信息，由Meta信息来指明该PC页对应的手机页的URL，以及该URL对应页面的格式，百度将根据用户终端类型选择最适合展示的页面。（无对应关系的PC页面无需添加Meta ）

1.Meta声明格式：<meta name="mobile-agent" content="format=*[wml|xhtml|html5]*; url=**url**">
　　注：A、加粗字体部分是需要站点自定义的内容。
　　　　　[wml|xhtml|html5]——根据手机页的协议语言，选择其中的一种。
　　　　　url=url——后者代表当前PC页所对应的手机页url，两者必须是一一对应关系

Meta声明示例：

```html

<meta name="mobile-agent" content="format=html5;url=http://3g.sina.com.cn/">
<meta name="mobile-agent" content="format=xhtml;url=http://sina.cn/">    
```

2.站长需要将Meta声明放在PC页源代码内部，如下：

```html
<head>
<meta name="mobile-agent" content="format=html5;url=http://3g.sina.com.cn/">
　　……
</head>
```

生效情况：标注Meta声明这一适配方案仅在百度移动搜索中生效，即只有当用户通过百度移动搜索访问站点时，适配才会生效；通过其他渠道则不生效。在标注准确对应关系无误的情况下，大约需要七天左右的时间生效，老旧页面会有延迟。但百度不保证一定能在移动搜索结果中按照您标注的对应关系进行替换。

**同时还可以使用如下Meta标签协议规范：**

```html
●如果该网页只适合在电脑上进行浏览，例如（http://www.sina.com.cn/ ），在html中加入如下meta：
<meta name="applicable-device" content="pc">
●如果该网页只适合在移动设备上进行浏览，例如（http://3g.sina.com.cn/ ），在html中加入如下meta：
<meta name="applicable-device" content="mobile">
●如果网页采用了响应式网页设计，例如（http://cdc.tencent.com/）
自适应设计有其一般原则：在head添加以下代码并且使用<picture>元素处理自适应图片:
<meta name="viewport" content="width=device-width, initial-scale=1.0">
不需要经过url自适配跳转就可以根据浏览器的屏幕大小自适应的展现合适的效果，同时适合在移动设备和电脑上进行浏览，在html中加入如下meta：
<meta name="applicable-device" content="pc,mobile">
```
**对应关系**--跳转适配

在此配置中，每个pc版网址都具有一个对应的不同网址，用于提供针对移动设备进行优化的内容。为了帮助我们的算法了解单独的移动版网址，我们建议您使用以下注释：
在pc版网页上，添加指向对应移动版网址的特殊链接 rel="alternate" 标记。这有助于发现网站的移动版网页所在的位置。
　　在移动版网页上，添加指向对应pc版网址的链接 rel="canonical" 标记。

例如，假设pc版网址为http://www.example.com/page-1 , 且对应的移动版网址为 http://m.example.com/page-1 ,那么此示例中的注释如下所示：

在pc版网页(http://www.example.com/page-1) 上，添加：　　

```html
<link rel="alternate" media="only screen and (max-width: 640px)"     href="http://m.example.com/page-1" >
```

而在移动版网页(http://m.example.com/page-1) 上，所需的注释应为:

```html
<link rel="canonical"href="http://www.example.com/page-1" >
```

Canonical标签其他用法参考 <a href="https://ziyuan.baidu.com/wiki/112/" rel="nofollow" >百度已支持Canonical标签</a>

**站长平台适配规则**

站长平台提交方式,及其他适配规则   <a href ="https://ziyuan.baidu.com/college/courseinfo?id=156&page=4" rel="nofollow" >参考百度站长官方</a>  <a href="https://ziyuan.baidu.com/college/courseinfo?id=156" rel="nofollow" >移动搜索</a>

### 神马

供站长提交pc->wap对应关系，神马搜索根据对应关系将收录的PC页替换为wap页

标注Meta声明

**1)含义：**站长做PC和wap网页自适配有困难，可以在PC网页源码的Meta字段添加PC和wap的页面对应关系，神马根据用户终端给出适合展示的页面。

**2)Meta声明格式：**

```html
<meta name="mobile-agent" content="format=[wml|xhtml|html5]; url=url">
```

，红色部分由站点填充具体内容。

**3)Meta声明举例：**

```html
<meta name ="mobile-agent" content="format=xhtml; url=http://sina.cn/">
```

**其他适配规则**

其他适配规则<a href="http://zhanzhang.sm.cn/open/adapterGuide" rel="nofollow" >参考神马搜索官方</a>

### 搜狗

搜狗适配官方给了几个链接请参考 <a href="http://zhanzhang.sogou.com/index.php/help/web2wap" rel="nofollow" >开放适配帮助</a>,  <a href="http://zhanzhang.sogou.com/index.php/help/columnist?id=5&fr=toolhelp" rel="nofollow" >搜狗移动适配</a>

到了最后可能大部分人都会说那我们知道移动适配是否生效呢？别急这点搜狗官方给出的几个判断特点为：**在替换后的搜索结果旁增加手机icon标记；替换后的搜索结果摘要下方的域名变为手机域名。**可能有一部分站点会遇到现实pc域名但是点击后跳转到wap站点的情况，这类情况属于正常现象，因为搜狗已经主动给你做了对应，但是千万不能偷懒不做平台适配，这个时候你更应该做好适配关系进一步保证移动适配的顺利。

### 360 so

360有两种方法

**pc url与wap url的对应(仅限提交5000对url)**

```
提供一个txt文档，文档中数据为两列，中间用tab键隔开，第一列为PC版URL ,第二列为PC页面对应的移动版页面。
以站点www.yimao.info为例：
http://www.yimao.info/	http://m.yimao.info/
http://www.yimao.info/findlawyers/	http://m.yimao.info/findlawyer/
http://www.yimao.info/question/	http://m.yimao.info/question/
```

**pc url pattern与wap url pattern的对应**

#### 提供一个txt文档，文档中数据为两列，中间用tab键隔开，第一列为PC版URL pattern,第二列为PC页面对应的移动版pattern。

```
 pc_url_pattern：表示PC页pattern，在PC页url的基础上，首先确定url中哪些路径或参数是可替换的。然后根据其类型，使用正则匹配符号(\d+)或者(\w+)表示该路径或参数。(\d+)表示“纯数字”字符串，(\w+)表示“数字”或“字母”以及“下划线”混合组成的字符串。
wap_url_pattern：表示wap版式的手机页pattern，在手机页url的基础上，根据可替换参数在对应的PC页pattern中出现的顺序，依次用\1，\2，……表示该参数。

以站点www.yimao.info为例：
http://www.yimao.info/question/(\d+).aspx http://m.yimao.info/question/\1.aspx
http://www.yimao.info/lawyer/(\w+)/ http://m.yimao.info/lawyer/\1/
http://www.yimao.info/case/add.aspx?toguid=(\w+)-(\w+)-(\w+)-(\w+)-(\w+)/ http://m.yimao.info/findlawyer/add.aspx?guid=\1-\2-\3-\4-\5/
```

参考<a href="http://zhanzhang.so.com/sitetool/urlmap/submit" rel="nofollow" >官方文档</a>

