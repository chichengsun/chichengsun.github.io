## 概述

### 定义

   Hyper Text Markup language超文本标记语言，用于描述页面结构的语言

   Cascading Style Sheets层叠式样式表，用于描述页面长什么样子

### 学习态度

1. 心态平和
2. 多练习
3. **不要你以为懂了，就可以不练习，这是IT领域常常出现的幻觉**

### 一些术语

1. web  --->  互联网
2. **w3c  ---> 万维网联盟，非盈利性的组织，为互联网提供各种标准**
3. XML  ---> 可扩展的标记语言，Extension Markup Language，用来定义文档结构，相对于HTML而言，他可以自定义标签
4. **MDN  ---> 可以查一些资料，官方定义和解释**

### 浏览器

  包括：

1. shell：外壳
2. **core：内核  ---> (渲染引擎，js引擎，其他模块)**

### 主流浏览器

| 主流浏览器    | 内核                                                         |
| ------------- | :----------------------------------------------------------- |
| IE            | trident                                                      |
| Firefox       | Gecko                                                        |
| Google chrome | Webkit(谷歌和苹果联合开发的)/blink(与苹果公司分歧后，自己研发的) |
| Safari        | Webkit                                                       |
| Opera         | presto(以前)/blink(现在)                                     |

## HTML核心1

### 基础知识

读者可以自己去看[html5元素周期表](http://www.html5star.com/manual/html5label-meaning/)

元素（也就是常说的标签） = 起始标记 + 结束标记 + 元素内容 + 元素属性

属性 = 属性名 + 属性值

属性的分类：

1. 局部属性：某些元素特有
2. 全局属性：每个元素都有

有些元素没有结束标记，这样的元素叫做：**空元素**

空元素的写法有两种：

1. ~~~html
   <img src="">html5
   ~~~

2. ~~~html
   <img src="" />以前的写法
   ~~~

元素的关系：

1. 父元素（爸爸）
2. 子元素（儿子）
3. 祖先元素（爹）
4. 子孙元素（孙子）
5. 兄弟元素（哥哥姐姐弟弟妹妹）

~~~html
<!DOCTYPE html>
    文档声明，告诉浏览器，当前浏览器使用的HTML的标准是5；不写的话，将导致浏览器进入怪异渲染模式，可能显示不正常
<html lang="en">
    根元素，一个页面只有一个，并且该元素是所有元素的父元素或祖先元素，HTML5中没有强制写这个元素
    lang="en"表示language，全局属性，表示该元素内部的文字是使用哪一种自然语言书写的
    lang="cmn-hans"表示中国官方语言，简体（simple）汉语（han）/也可以这么写lang=“zh-CN”但是已经过时了
<head>文档头部，不会显示在页面上
    meta元素表示文档的元数据：附加属性
    <meta charset="UTF-8">charset
    是局部属性，告诉网页用的是哪一个字符编码表，也就是UTF-8,相当于一个字典
    比如说中国使用的是GB2312，台湾是GBK
    UTF-8是Unicode的一个版本，也就是万国码，包含所有的语言
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    适配手机端的
    <title>Document</title>
    表示的是网页标题
</head>
<body>
    文档体
</body>
</html>
~~~

### 语义化

每个元素都有本身的含义

1. a元素：链接（当然还有别的作用，但是用的最多的是链接）
2. p元素：段落
3. h1：一级标题

元素与展示效果无关

1. 元素展示到页面上应该由css来控制

2. 因为浏览器带有默认的css样式，所以每个元素都有一些默认的样式

3. 比如你写h1的时候，里面的内容就会显示很大，并且加粗，这些都是css控制的，可以改的

4. 重要：选择什么元素，取决于内容的含义，而不是展示的效果**

### 为什么要语义化

为了优化搜索引擎（SEO）

>  搜索引擎比如：百度，Google，bing，等等，每隔一段时间，搜索引擎会从整个互联网中，抓取页面的源代码。

为了让浏览器理解网页

>  比如说：阅读模式，语音模式

### 文本元素

#### h元素

标题：head

有六个：h1~h6

#### p元素

段落：paragraph

> 乱数假文，没有任何实际意思的文字，使用lorem触发

#### span元素

官方解释：无语义的容器

以前：有些元素会独占一行（块级元素），有些元素不会（行级元素）

但是现在，在html5中，已经放弃这种叫法了,[mdn中的原话](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Block-level_elements):

> HTML 标准中块级元素和行内元素的区别至高出现在 4.01 标准中。在 HTML5，这种区别被一个更复杂的[内容类别](https://developer.mozilla.org/zh-CN/docs/HTML/Content_categories)代替。”块级“类别大致相当于 HTML5 中的[流内容](https://developer.mozilla.org/zh-CN/docs/HTML/Content_categories#Flow_content)类别，而”行内“类别相当于 HTML5 中的[措辞内容](https://developer.mozilla.org/zh-CN/docs/HTML/Content_categories#Phrasing_content)类别，不过除了这两个还有其他类别。

#### pre元素

预格式化文本元素

> 空白折叠：在源代码中的连续空白字符（空格，换行，制表符,等等），在页面显示的时候，会被折叠为一个空格

**在pre元素中的内容不会触发空白折叠，也就是说pre元素中的内容会按照源码的形式显示在页面上**

该元素通常用于在网页中显示源代码

pre元素的本质：他有一个默认的css样式（white-space:pre;）

> 显示代码的时候，通常套在code元素的里面，code表示代码区域

### html实体

实体字符：[HTML  Entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity)

实体字符通常用于在页面中显示一些特殊的字符，因为有些单词或者字母是由特殊含义，不能直接在页面中显示，实体字符的写法有两种方式：

1. &单词;
2. &#数字;

一般使用第一种方式。

常用的：

1. 小于号<：**& l t ;**(==由于markdown会识别，所以我写的时候中间加了空格，实践上是没有的，希望不要带来误解==)
2. 大于号>：**& g t ;**(和上面一样)
3. 空格：**& n b s p ;**(non-breaking space 因为普通的元素的内容会触发空白折叠，所以如果当你想要输出多个空格的时候，就要用到这个)
4. &符号：**& a m p ;**

### a元素

超链接

href：hyper reference：通常表示跳转地址

~~~ html
<a href=""></a>
~~~

用途：

1. 跳转地址（跳到这个页面之外）

   ~~~ html
   <a href="https://www.baidu.com">百度一下</a>
   ~~~

2. 跳转到某个锚点（在这个页面进行跳转）

   这是很常见的，比如说“点击回到顶部”，还有一些目录，可以点击到那个位置

   id属性：是一个全局属性，是元素在文档中的唯一标识

   ~~~ html
   <a href="#chapter">章节二</a>
   <p id="chapter"></p>
   ~~~

3. 功能链接

   点击触发某个功能

   1. 执行js代码

      ~~~ html
      <a href="javascript:alert('你好！')">点击弹出你好</a>
      ~~~

   2. 发送邮件

      ~~~ html
      <a href="mailto:nihao@qq.com">点击发送邮件</a>
      ~~~

   3. 打电话

      ~~~ html
      <a href="tel:12345678912">点击打电话</a>
      ~~~

a元素里面还有一个属性，target，控制打开的页面的窗口位置

如果你将前面的代码运行了，你就会发现每次跳转都是在当前的窗口，也就是覆盖了之前的内容，这个其实就是target控制的

现在只讲两种属性:

~~~ html
<a href="" target="_self"></a>这个是默认的，也就是在当前页面内打开，覆盖当前页面
<a href="" target="_blank"></a>这个就是在新窗口打开
~~~

### 路径的写法

首先你要了解站内资源和站外资源。

1. 站内资源：当前网站的资源

2. 站外资源：非当前网站的资源

第二个你要了解两种路径：绝对路径和相对路径。站内资源可以使用绝对路径，也可以使用相对路径；但是站外资源只能使用绝对路径。

#### 绝对路径的写法：

~~~ 
协议://主机名:端口号/路径
schema://host:port/path
~~~

协议名有很多，比如：**http，https，file等等**

主机名：域名或者IP地址

端口号：**如果协议是http，那么默认的端口号是80；如果协议是https，默认的端口号是443.可以省略。**

**当跳转地址和当前地址的协议名是一样的时候，可以省略协议名**

#### 相对路径的写法：

以./开头，./表示当前资源所在的目录；../表示返回上一级目录。

相对路径中./可以省略

### 图片

~~~ html
<img src="https://wx1.sbimg.cn/2020/07/04/2lICV.jpg" alt="李一桐女神" title="好看吗">//应用站外资源
<img src="img/2lICV.jpg" alt="李一桐女神" title="好看吗">//引用站内资源
~~~

alt属性：当图片资源失效时，就会使用该属性的文字代替图片显示

#### 与a元素一起使用

~~~html
<a href="https://baike.baidu.com/item/%E6%9D%8E%E4%B8%80%E6%A1%90/19299474?fr=aladdin">
     <img src="https://wx1.sbimg.cn/2020/07/04/2lICV.jpg" alt="李一桐女神" title="好看吗">
</a>
~~~

#### 与map元素一起使用

~~~ html
<a href="https://baike.baidu.com/item/%E6%9D%8E%E4%B8%80%E6%A1%90/19299474?fr=aladdin">
        <img usemap="#liyitong" src="https://wx1.sbimg.cn/2020/07/04/2lICV.jpg" alt="李一桐女神" title="好看吗">
</a>
<map name="liyitong">
    <area shape="circle" coords="360,204,48" href="https://www.baidu.com" alt="">
    <area shape="rect" coords="140,37,623,74" href="https://www.baidu.com" alt="">
    <area shape="poly" coords="601,371,123,456,123,159" href="https://www.baidu.com" alt="">
</map>
~~~

网页中的坐标原点是左上角，向右x增加，向下y增加

map元素，特定的区域点击触发效果。circle是圆形，360，204是圆心的坐标，48是半径，单位是像素；rect是矩形，140，37是左上角坐标，623，74是右下角坐标；poly是多边形，需要依次写出每个点的坐标。

这里可以使用qq截图来进行测量距离，但是你如果用的是笔记本，你打开设置，会发现这个

![2r9mR.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/2r9mR.png)

就是说默认是放大了，这样用qq截图的时候，就不是很准。那么这个时候，你要么把它调成100%，要么使用一些专业的测量工具，              比如ps，pxcook。

#### 与figure元素一起使用

指代，定义，通常用于把图片，图片标题，描述包裹起来

子元素：figcaption

### 多媒体元素

分为video和audio，也就是视频和音频。

#### video

~~~ html
<video controls="controls" src="video/1.mp4"></video>
~~~

**这里面有个属性，controls，取值只能为controls**

这里再拓展一下，某些属性的取值只有两种，第一种是不写，也就是不适用这个属性；第二种是取值为属性名，比如上面的controls。这种属性叫做布尔属性。

而且在HTML5中，这种属性可以不写属性值。如下面所示：

~~~ html
<video controls src="video/1.mp4"></video>
~~~

**还有一个属性，也是布尔属性，autoplay：自动播放**

但是这里要说的是，有些浏览器不允许自动播放，据说是怕吓到用户（你打开一个网页，然后突然有声音出来了，可能会吓到用户）那么这个时候就要用到另外的一个属性，**muted：静音播放。muted也是一个布尔属性。**

~~~ html
<video controls muted src="video/1.mp4"></video>
~~~

还有一个属性，**loop，也是一个布尔属性，循环播放。**

#### audio

和视频完全一致。参考上面

这里讲一下兼容性的问题

1. 旧版本的浏览器不支持这两个元素
2. 不同的浏览器支持的音视频格式可能不一样

视频有两种，mp4 或者webm，音频就只有一种mp3。所以一般开发的时候是这么写的：

~~~ html
<video controls autoplay muted loop>
    <source src="1.mp4"> \
    <source src="1.webm">
    <p>
        对不起，您的浏览器不支持该video元素，请点击这里下载最新版本的浏览器
    </p>
</video>
~~~

如果浏览器不支持mp4 ，就会执行下面的webm，如果两种都不支持，就会输出下面的那句话。

### 列表元素

分为有序列表和无序列表

#### 有序列表

ol : ordered list 

li : list item 

这里面有个属性，type，有五种取值：

- a 表示小写英文字母编号
- A表示大写英文字母编号
- i 表示小写罗马数字编号
- I 表示大写罗马数字编号
- 1 表示数字编号（默认）

~~~ html
<ol type="1">
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ol>
~~~

> **Note:** 这个属性在 HTML4中弃用，但是在 HTML5 中被重新引入。除非列表中序号很重要（比如，在法律或者技术文件中条目通常被需要所引用），否则请使用 CSS [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type) 属性替代。

其实还有一个属性，reversed，也就是倒序显示。是一个布尔属性。

~~~ html
<ol type="1" reversed>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ol>
~~~

#### 无序列表

ul : unordered list 

和有序列表一样，只需要将ol改成ul即可。

~~~ html
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
~~~

无序列表常用于**制作菜单** 和 **新闻列表**

#### 定义列表

通常用于一些术语的定义

dl : definition list 

有两种属性：

1. dt : definition title
2. dd : definition description

~~~ html
<dl>
    <dt>HTML</dt>
    <dd>
        超文本标记语言
    </dd>
    <dt>元素</dt>
    <dd>
        组成HTML的部分,xxxxxxx
    </dd>
</dl>
~~~

### 容器元素

==很重要！==

该元素代表一个区域，内部用于放置其他的元素

#### div元素

没有语义，没有任何的默认的样式。

那么这个就是和语义化是相反的，所以在HTML5中新加了很多语义化容器元素

#### 语义化容器元素

##### header元素

通常用于表示页头，也可以用于表示文章的头部

> **HTML `<header>` 元素**用于展示介绍性内容，通常包含一组介绍性的或是辅助导航的实用元素。它可能包含一些标题元素，但也可能包含其他元素，比如 Logo、搜索框、作者名称，等等。

##### footer元素

通常用于表示页脚，也可以用于表示文章的尾部

> **HTML <footer> 元素**表示最近一个[章节内容](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Sections_and_Outlines_of_an_HTML5_document#Defining_Sections_in_HTML5)或者[根节点](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Sections_and_Outlines_of_an_HTML5_document#Sectioning_root)（sectioning root ）元素的页脚。一个页脚通常包含该章节作者、版权数据或者与文档相关的链接等信息。

##### article元素

通常用于表示整篇文章，也就是文章正文

> **HTML `<article>`**元素表示文档、页面、应用或网站中的独立结构，其意在成为可独立分配的或可复用的结构，如在发布中，它可能是论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。

##### section元素

通常用于表示文章的章节

> **HTML <section>元素**表示一个包含在HTML文档中的独立部分，它没有更具体的语义元素来表示，一般来说会有包含一个标题。

##### aside元素

通常用于表示侧边栏

> **HTML `<aside>` 元素**表示一个和其余页面内容几乎无关的部分，被认为是独立于该内容的一部分并且可以被单独的拆分出来而不会使整体受影响。其通常表现为侧边栏或者标注框（call-out boxes）。

### 元素包含关系

以前： 块级元素可以包含行级元素，行级元素不可以包含块级元素，a元素除外

现在的元素包含关系非常复杂，元素的包含关系是由元素的内容类别决定。这些包含关系可以上[MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTML) 上查

一般的话，你记住下面的**关键点**，是不会出错的，如果真的错了，你就上mdn上查。

**关键点：**

1. 容器元素可以包含任何元素
2. a元素几乎可以包含任何元素
3. 某些元素有固定的子元素（ul>li ol>li dl>dt,dd）
4. 标题元素和段落元素不能相互嵌套，并且不能包含容器元素

## CSS基础1

### 为网页添加样式

~~~ css
h1{
    color: red;
    background-color: lightblue;
    text-align: center;
}
~~~

这样的一个形式就叫做CSS规则
CSS规则： 选择器 + 声明块

#### 选择器

##### 元素选择器

~~~ css 
p{
    color: red;
}
~~~

比如说这个，可以**选择文档中所有的同名元素**

##### id选择器

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        #test{             //先写上一个井号，然后写id名
            color: red;
        }
    </style>
</head>
<body>
    <p id="test">你好</p>
    <p>你好</p>
</body>
</html>
~~~

比如说这个，选中的是第一个p元素，将“你好”修改成红色。

##### 类选择器（最常用）

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .test{       //先写上一个英文的句号，然后写类名
            color: red;
        }
    </style>
</head>
<body>
    <p class="test">你好</p>
</body>
</html>
~~~

当有多个class的时候，你可以这样写：

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .test{
            color: red;
        }
        .big{
            font-size: 3em;
            text-align : center;
        }
    </style>
</head>
<body>
    <p class="test big">你好</p>
</body>
</html>
~~~

#### 声明块

也就是上面的打括号里面的内容

声明块中包含很多的声明（属性），每一个声明（属性）表达了某一个方面的样式，而每一个声明（属性）又包括属性名和属性值。如上面的color: red;   以属性名开头，以分号结尾。

#### CSS代码书写位置

##### 内部样式表

书写在style中，如下：

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        书写在这里
    </style>
</head>
<body>
    
</body>
</html>
~~~

##### 内联样式表

~~~ html
<p style="color:red;background-color: lightblue;text-align:center;">你好</p>
~~~

直接书写在元素的style中

##### 外部样式表（这是以后做开发，用的最多的方式）

也就是将样式写在单独的文件里面，文件的后缀名为.css,如图：

![CCasJ.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/CCasJ.png)

那么现在读者可能在想，怎样才能让html的文件使用这个样式表呢？

只需要在html文件中的头部加入link这个元素，注意，这个元素是个空元素，里面的地址写法参考前面的路劲写法。

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="css.css">
</head>
<body>
    <p class="test">你好</p>
</body>
</html>
~~~

里面的rel="stylesheet"表示链接的类型，是一个样式表。所以你应该可以想到，link元素不仅可以连接css文件，这里不多说。

##### 为什么推荐使用外部样式表

1. 外部样式可以解决多页面样式重复的问题
2. 有利于浏览器缓存，提高页面的加载速度
3. 代码分离，有利于阅读和后期的维护

### 常见的样式声明

#### color

元素内部的文字颜色，有多种方式：

**预设值：**已经设置好的单词，比如说red，blue等等

**三原色，色值：**光学三原色（红，绿，蓝），每个颜色可以使用0~255之间的数字来表达，有两种书写方式：

第一种rgb法：

~~~ css
color:rgb(0~255,0~255,0~255);
其中r代表red，g代表green，b代表blue。
其实还有一种方式：
color:rgba(0~255,0~255,0~255,0~1);
a代表是透明度，比如说0.1。
~~~

第二种方式，hex（16进制）表示法： 

~~~ css
color:#008c8c;
每两个数字代表色值，依次是红，绿，蓝，最小为00，最大为ff
而且当三对数字中两个数字相同的时候，可以写成一个，比如#00ffcc;可以写成#0fc;
~~~

​       **一些常见的颜色：**

​       淘宝红：#ff4400(#f40)

​       黑色：#000000(#000)

​       白色：#ffffff(#fff)

​       红色：#ff0000(#f00)

​       绿色：#00ff00(#0f0)

​       蓝色：#0000ff(#00f)

​       紫色：#ff00ff(#fof)

​       青色：#00ffff(#0ff)

​       黄色：#ffff00(#ffo)

​       灰色：#cccccc(#ccc)

#### background-color

元素背景颜色

#### font-size

元素内部文字的大小

有两种单位：

1. **px,是一个绝对单位**，可以简单地理解成文字所占高度的像素
2. **em,是一个相对单位**，相对于父元素的字体大小（也就是父元素的多少倍）

每个元素都必须有字体大小，如果没有设置字体大小，那么就要继承父元素的字体大小，如果父元素也没有，就继续向上继承，如果没有父元素，则使用**基准字号**

**基准字号**就是浏览器的设置里面的字体大小

#### font-weight

文字的粗细程度，取值可以为数字，也可以为预设值

>  strong和em元素默认是加粗

##### 预设值

1. normal（默认），也就是正常的字体，相当于数字值400
2. bold，粗体，相当于数字值700
3. bolder，定义比继承值更重的值
4. lighter,定义比继承值更轻的值

##### 数字值

取值范围：100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900 

#### font-family

文字类型，简单点说就是我们常说的字体

另外，你的计算机中必须有你设置的字体，这样才会生效

基于这一点，就出现了下面这种写法：

~~~ css
font-family:arial,consolas,微软雅黑
~~~

如果用户电脑中没有第一种字体，就会向后匹配，知道匹配到为止。

~~~ css
font-family:arial,consolas,微软雅黑,sans-serif
~~~

其实用的最多的是这种，也就是在最后面加上一个**sans-serif：表示非衬线字体**，也就是文字的边缘没有修饰，一般的电脑里面都有一种非衬线字体。这么写也是为了匹配大众。对应的还有**衬线字体**，也就是文字的边缘加了修饰，比如宋体

#### font-style

字体样式，通常用它来设置斜体

> em元素和i元素，默认的样式是斜体；但是在使用过程中，通常用它来表示一个图标（icon）

取值：

**normal：** 指定文本字体样式为正常的字体 

**italic：** 指定文本字体样式为斜体。对于没有设计斜体的特殊字体，如果要使用斜体外观将应用oblique 

**oblique：** 指定文本字体样式为倾斜的字体。人为的使文字倾斜，而不是去选取字体中的斜体字 

#### text-decoration

这里面包括text-decoration-line，text-decoration-style，text-decoration-color，我们这里讲的是第一个。

文本修饰，简单点就是给文本加线

> a元素，默认加了下划线

> del元素，表示错误的内容，默认加了中划线

> s元素，表示过期的内容，也是默认加了中划线

取值：

**none：** 指定文字无装饰 

**underline：** 指定文字的装饰是下划线 

**overline：** 指定文字的装饰是上划线 

**line-through：** 指定文字的装饰是贯穿线 

**blink：** 指定文字的装饰是闪烁。 

#### text-indent

首行文本缩进，单位可以实px，也可以是em

#### line-height

每行文本的高度，也就是我们常说的行高，这个值越大，每行文本的距离越大

**设置行高为容器的高度，可以让单行文本垂直居中**

行高可以设置为纯数字值，表示相对于当前元素的字体大小

#### width

宽度，单位是px

#### height

高度，单位是px

#### letter-spacing

表示文字间隙，单位可以是px，也可以是em

#### text-align

元素内部文字的水平排列方式。

常用的三个：

**left：** 内容左对齐。 

**center：** 内容居中对齐。 

**right：** 内容右对齐。

### 选择器

选择器可以帮你精准的选中你想选中的元素

#### 简单选择器

##### ID选择器

##### 元素选择器

##### 类选择器

> 以上三个在前面已经讲过（为网页添加样式），所以这里就不再讲了

##### 通配符选择器

~~~ css
*{
    xxxxx:xxxxxx;
}
~~~

这个选中的是所有的元素，也就是说这里面的内容对所有的元素都有效

##### 属性选择器

这个是根据属性名和属性值来选择元素

~~~ css
选中所有具有href属性的元素
[href]{
    xxxxx:xxxxx;
}
选中所有属性href的属性值为https://www.baidu.com的元素
[href="https://www.baidu.com"]{
    xxxxx:xxxxx;
}
~~~

当然这个用法还有很多，读者可以自己去查[mdn 属性选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors)

##### 伪类选择器

选中某些元素的某些状态，写法是加一个冒号

1. hover 

   表示鼠标悬停在上面会发生什么变化

   ~~~ css
   这样写选中的所有的元素
   :hover{
      xxxxx:xxxxx;
   }
   这样写选中的就是a元素
   a:hover{
      xxxxx:xxxxx;
   }
   ~~~

2. active

   激活状态，也就是当鼠标按下的时候会发生什么变化

   ~~~ css
   :active{
   	xxxxx:xxxxx;
   }
   ~~~

3. link

   超链接未被访问时的状态

4. visited

   超链接被访问过的状态

​       当然还有很多，读者可以自己去查[伪类选择器 mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes)

​       （别名）爱恨法则：love ，hate

**如果你全部都要写，那么就要遵循一定的顺序，link,visited,hover,active，以这样的顺序来写。**

##### 伪元素选择器

生成并选中某个元素内部的第一个子元素或者最后一个子元素，写法是加两个冒号

> 目前的话，只讲两个

1. before

   意思是在span元素最前面生成一个没有名字的子元素

   ~~~ css
   span::before{
   	content:"《";//里面有个属性为content，意思是加一个文本
   }
   ~~~

2. after

   意思是在审判元素最后面生成一个没有名字的子元素

   ~~~ css
   span::after{
   	content:"》";
   }
   ~~~

#### 选择器的组合

##### 并且

多个选择器连一起写，中间不加任何东西

~~~html
<p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Atque ex quia doloribus quae amet ea.</p>
<p class="red">Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum suscipit iure ea at harum assumenda.</p>
p{
	text-indent:2em;//选中的是所有的p元素
}
p.red{
	color:red;//选中的是类名为red的p元素
}
~~~

##### 后代（用的非常多）

多个选择器连在一起写，中间加空格

~~~ html
<div>
    <ul>
        <li>Lorem.</li>
        <li>Quam.</li>
        <li>Porro!</li>
        <li>Consequatur!</li>
    </ul>
</div>
~~~

~~~ css
div ul li{
	color:red;
}
~~~

##### 子元素

多个选择器连在一起写，中间加>

~~~ html
<div class="abc">
    <p class="red"></p>
</div>
~~~

~~~ css
.abc>.red{
    color:red;
}
~~~

##### 相邻兄弟元素

多个选择器写在一起，中间加+

**选择的是之后的一个兄弟元素**

~~~ html
<div class="abc">
    <p>你好</p>
    <p class="red">你好</p>
    <p>你好</p>
</div>
~~~

~~~ css
.abc .red+p{
    color:red;
}
~~~

选中的是最后一个p元素

##### 兄弟元素

多个选择器写在一起，中间加~

~~~ html
<div class="abc">
    <p>你好</p>
    <p class="red">你好</p>
    <p>你好</p>
    <p>你好</p>
    <p>你好</p>
    <p>你好</p>
</div>
~~~

~~~ css
.abc .red~p{
    color:red;
}
~~~

选中的是后面所有的兄弟元素

#### 选择器的并列

多个选择器，中间用逗号隔开
一般在代码有重复的时候使用

~~~ css
.red{
    color:red;
}
p{
    color:red;
    font-size: 10px;
}
~~~

可以写成

~~~ css
.red,p{
    color:red;
}
p{
    font-size: 10px;
}
~~~

### 层叠

我们知道css叫做层叠样式表，那么现在我们就来说明什么叫做层叠

在说明这个之前，我们首先要了解的是声明冲突

**声明冲突：**同一个样式，多次引用到同一个元素里面

**层叠：**解决声明冲突的过程，是浏览器自动完成的（**权重计算**）

**那么现在我们就要了解这个过程，有三种比较方式，最后只有一种能胜出，比较顺序如下：**

#### 比较重要性

作者样式表：开发者书写的样式

**重要性从高到低：**

1. 作者样式表中的!important样式，如：

   ~~~ css
   color:red;!important
   ~~~

2. 作者样式表中的普通样式

3. 浏览器默认样式表中的样式

#### 比较特殊性

当**比较重要性**不能比较出来的时候，就是用这个

依据就是看选择器

总体规则：选择器选中的范围越窄，越特殊

具体规则：通过选择器，计算出一个四位数（xxxx）

**千位：**如果为内联样式（行间样式），千位为1；否则为0

**百位：**等于选择器中所有id选择器的数量

**十位：**等于选择器中所有的类选择器，属性选择器，伪类选择器的数量

**个位：**等于选择其中所有元素选择器，伪元素选择器的数量

==注意：这个四位数是256进制==

| 选择器                         | 权重值（256进制） |
| ------------------------------ | ----------------- |
| !important                     | Infinity          |
| 行间样式（内联样式）           | 1000              |
| id选择器                       | 100               |
| 类选择器/属性选择器/伪类选择器 | 10                |
| 元素选择器/伪元素选择器        | 1                 |
| 通配符                         | 0                 |



#### 比较源次序

如果上面的还是不能比较出来，就要用到最后一个了，也就是比较**源码的次序**

==代码书写靠后的胜出==

#### 应用

##### 重置样式表

书写作者样式表，覆盖浏览器的默认样式表（因为不同的浏览器的默认样式表不一样）

**常见的重叠样式表：**normalize.css，reset.css，meyer.css

##### 爱恨法则

为什么要按照顺序写，也就是这样link>visited>hover>active

这是出于人们的需求，利用了层叠的知识

### 继承

==子元素会继承父元素的**某些css属性**==

通常，和文字相关的属性都能被继承

所以一般字体相关的设置再body里面

~~~ css
body{
	font: italic 1.2em "Fira Sans", serif;
}
~~~

### 属性值的计算过程

浏览器渲染一个页面，是一个元素一个元素依次渲染，顺序按照页面的树形目录结构进行

**渲染每个元素的前提条件是：该元素的所有css属性必须有值**

一个元素，从所有的属性没有值，到所有的属性都有值，这个过程就叫做css属性值计算过程。这个过程有四个步骤：

1. **确定声明值**

   参考样式表中没有冲突的声明，作为css属性值

2. **层叠冲突**

   对样式表中有声明冲突的使用层叠规则，确定css属性

3. **使用继承**

   **对仍然没有值的属性**，若可以使用继承，则继承父元素的值

4. **使用默认值**
   **对仍然没有值的属性**，使用默认值（因为每一个css属性都有一个默认值）

下面出个题：问你这两段文字分别是什么颜色？

~~~ html
div{
	color:red;
}
<div>
    <a href="">
        举个例子
    </a>
    <p>
        举个例子
    </p>
</div>
~~~

**原因：**这里就要用到刚才学的知识，a元素是有声明的（本来要上传截图的，但是他说图片违规了，我笑了），既然上传不了，读者可以自己在电脑上看，按照上面的顺序，如果有声明，就不会用到继承，所以第一段文字不是红色。然后看p元素，它是没有声明的，也不会发生层叠，所以他会用到继承，所以第二段文字是红色。**这也就是为什么a元素不继承**

**特殊的两个css取值：**

~~~ css
inherit//强制继承，可以解决上面的问题
~~~

~~~ css
initial//初始值，将该属性的值设置为默认值
~~~

### 盒模型

每个元素再页面中都会生成一个矩形区域，这个区域就叫做盒子

盒子模型：

1. 行盒：display属性值为inline的元素
2. 块盒：display属性值为block的元素

**行盒在页面中不换行，块盒独占一行**

display默认值为inline

行盒display属性默认是inline，块盒默认是block，但是是可以改的，毕竟它只是一个css属性

默认的块盒：容器元素，h1~h6，p元素

默认的行盒：span，img，a，video，audio

#### 盒子的组成部分

无论是行盒还是块盒，都具有以下的组成部分，从内到外分别是：

1. **内容   content**

   width，height设置的是**盒子内容的宽高**

   内容部分通常叫做整个盒子的**内容盒**

2. **填充（内边距）  padding**

   盒子边框到盒子内容的距离，有四个值：

   padding-left,pading-right,padding-top,padding-bottom

   可以简写：padding:xxxx;可以同时设置多个值

   | 数字个数 | 意思                  |
   | -------- | --------------------- |
   | 一个值   | 代表四个方向          |
   | 两个值   | 代表上下   左右       |
   | 三个值   | 代表上   左右    下   |
   | 四个值   | 代表上  右   下    左 |

   填充区  +   内容区  =   填充盒    padding-box

3. **边框   border**

   边框包含三个属性，边框宽度（border-width），边框样式（border-style），边框颜色（border-color）

   边框有四个方向

   默认情况下，border-width为0，border-style为none，border-color默认是字体的颜色。

   border-style有很多的取值，读者可以自行[查看取值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-style)

   速写：border:宽度  样式   颜色

   边框  +   填充区   +   内容  = 边框盒   border-box

4. **外边距  margin**

   边框到其他盒子的距离，有四个方向，取值同padding

### 盒模型的应用

#### 改变宽高范围

默认情况下，（宽度）width，（高度）height设置的是内容盒宽高

> 页面重构师   将psd文件（也就是设计稿）制作成为静态页面

衡量设计稿尺寸的时候，往往使用的是边框盒，而width和height设置的是内容盒的宽高，有两种解决方法：

1. 精确计算

   也就是自己根据设计稿算出来内容盒的高度和宽度

2. CSS3

   CSS3中有一个属性：box-sizing(设置宽高时，设置的是哪一个部分的宽高)

   有两个取值，border-box和content-box（默认值）

#### 改变背景覆盖范围

~~~ css
div{
    width:100px;
    height:100px;
    background-color:#008c8c;
    padding:30px;
    border:5px dashed red;
}
<div>
 
</div>
~~~

读者可以试着运行一下，你会发现背景覆盖的范围是**边框盒**

可以通过background-clip来改变，有三个值，border-box（默认值），padding-box，content-box

#### 溢出处理

如果没有设置宽高，盒子的大小是会随着内容儿改变的，也就是内容是不会溢出的，但是如果人为的设置了宽高，盒子太小了，就会溢出，但是溢出的内容是可以看到的，比如这样：

![CqKIG.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/CqKIG.png)

有个属性：overflow，又来处理溢出的内容，有四个值：

1. visible

   默认值，也就是溢出可见的

2. hidden

   溢出隐藏

3. scroll

   加一个滚动条

4. auto

   需要的时候（也就是溢出的时候）加滚动条

**当然这是一个速写属性，具体的可以单独设置x和y轴，overflow-x,overflow-y**

#### 断词规则

word-break，这是一个css属性，**它影响文字在什么位置被截断（通俗一点就是，比如说上面那个溢出图，为什么要在那些地方换行）**

取值：

1. normal

   普通，CJK（也就是中国，日本，韩国）字符在文字处截断，非CJK字符（在单词处截断）

2. break-all

   截断所有。所有的字符都在文字处截断

3. keep-all

   保持所有。所有的字符都在单词处截断

#### 空白处理

有个属性：white-space，它有一个值为nowrap。表示当容器不够时，不换行

还有一个属性：text-overflow，它有一个值为ellipsis，表示当容器不够时，最后用三个小圆点表示

~~~ css
white-space:nowrap;
overflow:hidden;
text-overflow:ellipsis;
~~~

这是个三件套，效果就是：

![UJOzfx.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/UJOzfx.png)

当文本写不下的时候，有三个小圆点表示

### 行盒的盒模型

常见的行盒：包含具体内容的元素

比如：span，strong，i，img，video，audio

#### 显著的特点

1. 盒子沿着内容延申

2. **行盒不能设置宽高**

   所以你只能通过字体大小，行高，字体类型间接调整

3. 内边距

   水平方向上有效，垂直方向上不会实际占据空间

4. 边距

   水平方向上有效，垂直方向上不会实际占据空间

5. 外边距

   水平方向上有效，垂直方向上不会实际占据空间

#### 行块盒

display:inline-block

1. 不独占一行
2. 盒模型中所有的尺寸都有效

> 空白折叠发生在行盒（行块盒）内部或者行盒（行块盒）之间

#### 可替换元素和非可替换元素

大部分元素，页面上显示的结果，取决于元素内容，称为非可替换元素

少部分元素，页面上显示的结果，取决于元素属性，称为可替换元素

可替换元素：img，video，audio

**绝大部分的可替换元素为行盒**

==可替换元素类似于行块盒，盒模型中所有尺寸均有效==

另外，这里讲到一个属性，object-fit，它有五种取值：

- contain

  被替换的内容将被缩放，以在填充元素的内容框时保持其宽高比。 整个对象在填充盒子的同时保留其长宽比，因此如果宽高比与框的宽高比不匹配，该对象将被添加“[黑边](https://zh.wikipedia.org/wiki/黑邊)”。

- cover

  被替换的内容在保持其宽高比的同时填充元素的整个内容框。如果对象的宽高比与内容框不相匹配，该对象将被**剪裁**以适应内容框。

- fill

  被替换的内容正好填充元素的内容框。整个对象将完全填充此框。如果对象的宽高比与内容框不相匹配，那么该对象将被**拉伸以适应内容框**。

- none

  被替换的内容将**保持其原有的尺寸**。

- scale-down

  内容的尺寸与 `none` 或 `contain` 中的一个相同，取决于它们两个之间谁得到的对象尺寸会更小一些。



## CSS基础2

### 视觉格式化模型

盒模型：规定单个盒子的规则

**视觉格式化模型（布局规则）**：页面中多个盒子的排列规则

视觉格式化模型，大体上将页面中盒子的排列分为三种方式：

1. 常规流
2. 浮动
3. 绝对定位

#### 常规流

也叫做文档流，普通文档流，常规文档流

所有元素，默认情况下，都属于常规流布局

**总体规则**：块盒独占一行，行盒水平依次排列

**包含块（container block）**：每个盒子都有它的包含块，包含块决定了盒子的活动范围

**绝大部分情况下：盒子的包含块，为其父元素的内容盒**

**块盒**

1. 每个块盒的总宽度，必须刚好等于包含块的宽度

   宽度的默认值为**auto：将剩余的空间吸收掉**

   margin的取值也可以为auto，不过不是默认值，margin的默认值为0

   **width的吸收能力比margin强**

   **若宽度，边距，内边距，外边距计算后，仍然有剩余的空间，则剩余的空间被（当然，这个和排列有关，如果是从右到左排列，就是margin-left）margin-right全部吸收**

   ==在常规流中，块盒在其包含块中居中，可以定宽，然后左右margin设置为auto==

   ~~~ css
   .parent{
       width:300px;
       height:300px;
       background:#008c8c;
       padding:30px;
   }
   .child{
       height:100px;
       width:100px;
       margin-left:auto;
       margin-right:auto;
       background:#ccc;
   }
   html里面的内容我就没写，很简单，就是有两个div，包含关系
   ~~~

   如图：

   ![UdhdAI.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/UdhdAI.png)

2. 每个块盒垂直方向上的auto值

   height：auto，表示适应内容的高度

   margin：auto，表示0

3. 百分比取值

   padding，宽高，margin可以取值为百分比

   以上的百分比是相对于**包含块的宽度**

   **高度的百分比：**

   **包含块的高度取决于子元素的高度**

   ~~~ css
   .parent{
       width:300px;
       background:#008c8c;
       padding:30px;
   }
   .child{
       width:100px;
       margin-left:auto;
       margin-right:auto;
       background:#ccc;
       height:50%;
   }
   ~~~

   比如说这样，父元素没有设置高度，所有父元素的高度适应子元素内容，也就是说跟子元素有关，但是这里子元素height：50%，说明子元素的高度跟父元素有关，这就相互矛盾了，所以如果是这样，设置百分比是无关。

   **包含块的高度不取决于子元素的高度**

   百分比相对于父元素的高度

4. 上下外边距的合并

   两个常规流块盒，==**上下外边距相邻**==，会进行合并

   如果是两个不同的外边距，则取最大值

   ~~~ css
   div{
       width:100px;
       height:100px;
       background:#000;
       margin:50px;
   }
   <div>
   </div>
   <div>
   </div>
   ~~~



​       如图：

​        ![Uw9pzF.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/Uw9pzF.png)

#### 浮动

##### 应用场景

1. 文字环绕
2. 横向排列

##### 浮动基本特点

修改float属性，有两种取值：

- left，左浮动，元素在包含块中靠上靠左
- right，右浮动，元素在包含块中靠上靠右

默认值为none，也就是不浮动，即常规流

1. **当一个元素设置为浮动后，元素会变成块盒**（修改display属性为block）
2. 浮动元素的包含块和常规流一样，是父元素的内容盒

##### 盒子尺寸

1. 宽度为auto时，表示适应内容宽度
2. 高度为auto时，和常规流一样，适应内容的高度
3. margin为auto时，表示的是0
4. 边框，内边距，百分比设置和常规流一样

##### 盒子的排列

最基本的就是上面所说的：

- 左浮动的盒子靠上靠左排列

- 右浮动的盒子靠上靠右排列

- **浮动盒子在包含块中排列时，会避开常规流块盒**

- **常规流块盒在排列时，会无视浮动的盒子（也就是当浮动的盒子不存在，占领浮动盒子的位置）**

- **行盒在排列时，会避开浮动的盒子**

  > 如果文字没有在行盒中，则浏览器会自动生成一个行盒包裹文字，该行盒叫做匿名行盒

- 外边距合并不会发生

##### 高度坍塌

高度坍塌的原因：常规流盒子的自动高度（也就是没有设置高度，随着内容而增大），在计算时，不会考虑浮动的盒子

解决方式是清除浮动，涉及到一个css属性，clear，有四种取值：

- none，默认值
- left，清除左浮动，该元素必须出现在所有左浮动盒子的下方
- right，清除右浮动，该元素必须出现在所有右浮动盒子的下方
- both，清除左右浮动，该元素必须出现在所有浮动盒子的下方

1. 在所有的浮动元素下面加一个元素，元素里面清除浮动，即可（这个方法不太好，因为加了一个没有意义的元素）

2. 在浮动元素的父元素里面加一个伪元素

   ~~~ css
   xxx::after{
       content:"";
       display:block;
       clear:both;
   }
   ~~~

   这是一个三件套，用来解决高度坍塌的问题。也就是哪个元素高度坍塌了，就在哪个元素里面加个伪元素::after，然后用这个三件套。**==所以你写代码的时候，只要使用到浮动，你就要记住高度坍塌的问题，并使用这个三件套来解决高度坍塌的问题==**

#### 定位

手动控制元素在包含块中的精准位置

涉及的css属性是：position，有几种取值：

- static，默认值（可以认为是不定位）
- relative，相对定位
- absolute，绝对定位
- fixed，固定定位

一个元素，只要position的值不是static，就认为该元素是一个定位元素

定位元素会脱离文档流（**浮动元素也脱离了文档流**，相对定位除外）

**一个脱离了文档流的元素，有以下特点：**

1. 文档流中的元素摆放时，会忽略脱离了文档流的元素
2. 文档流中元素计算自动高度的时候，会忽略脱离了文档流的元素

##### 相对定位

不会导致元素脱离文档流，只是让元素在原来的位置上进行偏移

**特点：**

1. 保留原来的位置进行定位
2. 相对与自己原来的位置进行定位

可以通过四个css属性来设置位置：

- top
- bottom
- left
- right

相对定位下，盒子的偏移不会对其他的盒子产生任何影响

而且在设置位置时，不要设置冲突的属性，比如：

~~~ css
left:50px;
right:50px;
~~~

这样就冲突了，但是浏览器默认是left和top优先级高，所以尽管这样设置没有太大的问题，但还是不要这样设置

##### 绝对定位

1. 宽高为auto时，适应内容
2. **包含块变化：找祖先元素中第一个定位元素，该元素的填充盒为它的包含块；若找不到，则它的包含块为整个网页（初始化包含块）**

**特点：**

1. 脱离原来的位置进行定位

   > 就是说如果一个元素变成绝对定位，那么这个元素之前占的位置就会空出来，这个时候页面又要重新排列了

2. 相对于最近的有定位的祖先元素进行定位，如果没有，则相对文档定位

**一般用相对定位作为参照，绝对定位用来定位**

##### 固定定位

包含块：固定是视口（浏览器的可视窗口，通俗点讲，就是你看到的页面的矩形区域）

这个东西一般用于广告（无论你怎么滚动页面，它就在那儿不动），因为是相对于**视口**进行定位

其他的东西跟绝对定位一样、

##### 定位下的居中

某个方向上：

1. 定宽（水品方向上），定高（垂直方向上）
2. 将左右（上下）的距离设置为0
3. 将左右（上下）margin设置为auto

绝对定位和固定定位i中，margin为auto时，会自动吸收剩余的空间

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            margin:0;
            padding:0;
        }
        .item{
            width:100px;
            height:100px;
            background:#008c8c;
            position:fixed;
            top:0;
            left:0;
            right:0;
            bottom:0;
            margin:auto;
        }
    </style>
</head>
<body>
	<div class="item"></div>
</body>
</html>
~~~

如图：

![CV80k.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/CV80k.png)

##### 多个定位元素重叠时

前面我们可以看到：

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
    	.item{
            height:100px;
            width:100px;
            background:#008c8c;
            border:2px solid black;
        }
        .position{
            left:100px;
            top:100px;
            position:absolute;
        }
    </style>
</head>
<body>
	<div class="item"></div>
    <div class="item position"></div>
    <div class="item"></div>
</body>
</html>
~~~

运行出来是这样的：

![UWY17n.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/UWY17n.png)

你会发现，盒子出现了重叠

这里就应用到了一个css属性，z-index，`z-index` 属性设定了一个定位元素及其后代元素或 flex 项目的 z-order。 当元素之间重叠的时候， **z-index 较大的元素会覆盖较小的元素在上层进行显示**。[z-index mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/z-index)

==只有定位元素设置z-index才会有效==

z-index可以为负数，如果是负数，在遇到常规流 ，浮动元素的时候，会被覆盖

##### 补充

绝对定位和固定定位一定是块盒（不是块盒的，会变成块盒）

绝对定位和固定定位元素不能浮动

没有外边距合并

### 更多的选择器

#### 更多的伪类选择器

##### first-child，last-child

选中第一个子元素/选中最后一个子元素

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
    	li:first-child{
            color:red;
        }
    </style>
</head>
<body>
	<ul>
        <li>Lorem.</li>
        <li>Velit.</li>
        <li>Voluptatibus.</li>
        <li>Officia?</li>
        <li>Ad!</li>
        <li>Delectus?</li>
        <li>Laboriosam!</li>
        <li>Fuga.</li>
        <li>Reprehenderit!</li>
        <li>Mollitia!</li>
    </ul>
</body>
</html>
~~~

如图：![dEpXE8.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/dEpXE8.png)

详情可以到官网了解，[first-child mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-child)

> 另外补充一点，还有一个伪类，first-of-type/last-of-type
>
> a:first-child{
>
> ​	color:red;**选中的是a元素，并且a元素必须是第一个子元素**
>
> }
>
> a:first-of-type{
>
> ​	color:red;**选中的是子元素中的第一个a元素**
>
> }

##### nth-child,nth-of-type

选中指定位置的元素

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
    	li:nth-child(3){
            color:red;
        }
    </style>
</head>
<body>
	<ul>
        <li>Lorem.</li>
        <li>Velit.</li>
        <li>Voluptatibus.</li>
        <li>Officia?</li>
        <li>Ad!</li>
        <li>Delectus?</li>
        <li>Laboriosam!</li>
        <li>Fuga.</li>
        <li>Reprehenderit!</li>
        <li>Mollitia!</li>
    </ul>
</body>
</html>
~~~

如图：![dVB7mF.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/dVB7mF.png)

> 当然括号里面也可以些变量，比如2n，2n+1
>
> 另外有一个**even**关键字，和2n一样，表示偶数
>
> 还有个关键字**odd**，和2n+1一样，表示奇数

#### 更多的伪元素选择器

##### first-letter

选中元素中第一个字母或者文字

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
    	p::first-letter{
            color:red;
            font-size:2em;
            font-weight:bold;
        }
    </style>
</head>
<body>
	<p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repellat, ducimus.</p>
</body>
</html>
~~~

如图：![dVy7g1.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/dVy7g1.png)

##### first-line

选中的是第一行的文字元素

效果很简单，这里就不举例子了

##### selection

选中被用户框选的文字

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
    	p::selection{
            color:red;
            background:#008c8c;
        }
    </style>
</head>
<body>
	<p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repellat, ducimus.</p>
</body>
</html>
~~~

如图：![dV2ciF.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/dV2ciF.png)

### 更多的样式

#### 透明度

1. 第一种是用到一个css属性，**opacity**，他设置的是整个元素（也就是盒子里面的所有的东西）的透明度，取值从0~1（0就是完全透明）
2. 第二种是在设置颜色的时候设置，也就是**rgba**

#### 鼠标

使用css属性**cursor**设置

这里没有作过多的介绍，读者可以自行上官网查看，[cursor mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/cursor)

> 当然鼠标还可以设置为一个图标（一般是以ico为后缀名的图片）
>
> 比如：cursor:url(img/target.ico),auto;
>
> 后面加上一个auto，效果和font-family是一样的，如果前面的那张图片失效了，就会使用的浏览器的样式

#### 盒子的隐藏

第一种是**display:none;**也就是不生成盒子

第二种是**visibility:hidden;**生成盒子，只是从视觉上移除盒子，盒子仍然占据着空间

#### 背景图

首先，img元素是属于HTML的概念，背景图是属于css的概念 

1. 当图片属于网页内容时，必须使用img元素
2. 当图片仅用于美化页面，必须使用背景图

##### 涉及的CSS属性

1. **background-image**

   ~~~ html
   <style>
       div{
           width:100px;
           height:100px;
           backgroung-image:url(imgs/xxxx.jpg);
           这里有个需要注意的点，如果这个样式是写在单独的css文件里面，那么这个路径就是相对于这个css文件
           如果写的是内部样式，也就是写在html文件中，那么这个路径就是相对于这个html文件
       }
   </style>
   ~~~

2. ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           body{
                background-image:url("../img/奥运五环.ico");
           }
       </style>
   </head>
   <body>
   </body>
   </html>
   ~~~

   由于这个图片非常小，所以：![dmBMg1.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/dmBMg1.png)

   ==也就是说默认情况下，背景图会在横坐标和纵坐标中进行重复==，当然这个是可以控制的，需要用到另外一个css属性

   **background-repeat**,这是一个速写属性，分为background-repeat-x和background-repeat- y

   | **单值**  | **等价于双值**      |
   | --------- | ------------------- |
   | repeat-x  | repeat no-repeat    |
   | repeat-y  | no-repeat repeat    |
   | repeat    | repeat repeat       |
   | space     | space space         |
   | round     | round round         |
   | no-repeat | no-repeat no-repeat |

   在双值语法中, 第一个值表示水平重复行为, 第二个值表示垂直重复行为. 下面是关于每一个值是怎么工作的具体说明:

   | **repeat** | 图像会按需重复来覆盖整个背景图片所在的区域. 最后一个图像会被裁剪, 如果它的大小不合适的话. |
   | ---------- | ------------------------------------------------------------ |
   | space      | 图像会尽可能得重复, 但是不会裁剪. 第一个和最后一个图像会被固定在元素(element)的相应的边上, 同时空白会均匀地分布在图像之间. [`background-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position)属性会被忽视, 除非只有一个图像能被无裁剪地显示. 只在一种情况下裁剪会发生, 那就是图像太大了以至于没有足够的空间来完整显示一个图像. |
   | round      | 随着允许的空间在尺寸上的增长, 被重复的图像将会伸展(没有空隙), 直到有足够的空间来添加一个图像. 当下一个图像被添加后, 所有的当前的图像会被压缩来腾出空间. 例如, 一个图像原始大小是260px, 重复三次之后, 可能会被伸展到300px, 直到另一个图像被加进来. 这样他们就可能被压缩到225px.译者注: 关键是浏览器怎么计算什么时候应该添加一个图像进来, 而不是继续伸展. |
   | no-repeat  | 图像不会被重复(因为背景图像所在的区域将可能没有完全被覆盖). 那个没有被重复的背景图像的位置是由[`background-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position)属性来决定. |

3. **background-size**

   预设值：cover，contain

   `cover`

   > 缩放背景图片以完全覆盖背景区，可能背景图片部分看不见。和 `contain` 值相反，`cover` 值尽可能大的缩放背景图像并保持图像的宽高比例（图像不会被压扁）。该背景图以它的全部宽或者高覆盖所在容器。当容器和背景图大小不同时，背景图的 左/右 或者 上/下 部分会被裁剪。

   `contain`

   >  缩放背景图片以完全装入背景区，可能背景区部分空白。`contain` 尽可能的缩放背景并保持图像的宽高比例（图像不会被压缩）。该背景图会填充所在的容器。当背景图和容器的大小的不同时，容器的空白区域（上/下或者左/右）会显示由 background-color 设置的背景颜色。

   也可以设置数值和百分数，这样来设置：background-size:横向  纵向;

4. **background-position**

   设置背景图的位置

   预设值：center left right bottom top

   可以这样：background-position:center;代表横向和纵向居中；也可以这样：background-position:center left;代表横向居中，纵向靠左

   也可以设置为数值或者百分数，数值的话，有两个，比如background-position:100px 100px;代表背景图距离容器左边100px，距离容器上面100px

5. **background-attachment**

   通常使用他控制背景图是否固定

   取值：

   `fixed`

   此关键属性值表示背景相对于视口固定。即使一个元素拥有滚动机制，背景也不会随着元素的内容滚动。

   `local`

   此关键属性值表示背景相对于元素的内容固定。如果一个元素拥有滚动机制，背景将会随着元素的内容滚动， 并且背景的绘制区域和定位区域是相对于可滚动的区域而不是包含他们的边框。

   `scroll`

   此关键属性值表示背景相对于元素本身固定， 而不是随着它的内容滚动（对元素边框是有效的）。

6. **背景图和背景颜色混合使用**

   就是盒子中没有背景图的地方，用颜色来替代

   > 另外说到，background，这是一个速写属性，包括了前面所说的那些

## HTML进阶

### iframe元素

**通常用于在网页中嵌入另外一个页面**

~~~ html
<iframe src="https://www.baidu.com" frameborder="0"></iframe>
~~~

![duC00J.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/duC00J.png)

iframe元素是**可替换元素**

可替换元素的特点：

1. 通常为行盒
2. 通常显示的内容取决于元素的属性
3. css不能完全控制它的样式
4. 具有行块盒的特性

另外这里讲一个之前学过的属性target的另一种用法：

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        iframe{
            width:100%;
            height:500px;
            border:2px solid black;
        }
    </style>
</head>
<body>
    <a href="https://www.baidu.com" target="myiframe">百度</a>
    <a href="https://www.douyu.com" target="myiframe">斗鱼</a>
    <a href="https://www.taobao.com" target="myiframe">淘宝</a>
    <iframe name="myiframe" src="https://www.baidu.com" frameborder="0"></iframe>
</body>
</html>
~~~

以前我们打开一个新网页是在当前的视口上打开或者新开一个页面打开，上面这种写法，就可以在iframe元素盒子中打开，如图：

![target的用法](https://i.loli.net/2020/08/18/UJsINV2TSMwcPCL.gif)

### 在页面中使用flash

需要用到**object**，**embed**（他们都是可替换元素）这两个元素，当然这两个任选一个即可

#### object

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        object{
            width:100%;
            height:640px;
        }
    </style>
</head>
<body>
    <object data="./example.swf" type=""></object>
</body>
</html>
~~~

> swf是Macromedia公司的动画设计软bai件Flash的专用格式du，是一种支持矢量和点阵图形的动画文件格式，被广泛应zhi用于网页设计，动画制作等领域，swf文件通常也被称为Flash文件

object 元素里面有一个子元素，**param**，用来设置参数

~~~ html
<object data="./example.swf" type="">
        <param name="quality" value="high">
    </object>
~~~

![dKeKrq.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/dKeKrq.png)

#### embed

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        embed{
            width:100%;
            height:640px;
        }
    </style>
</head>
<body>
    <embed src="./example.swf" quality="high" type="">
</body>
</html>
~~~

embed元素里面没有子元素，那么设置参数的时候，只能在元素里面写，效果和上面的一样

由于不同的浏览器的兼容性不一样，所以一般这样写：

~~~ html
<object data="./example.swf" type="">
    <param name="" value="">
    <embed src="./example.swf" quality="high" type="">
</object>
~~~

### 表单元素

指的是一系列用于收集用户信息的元素

#### input元素

~~~ html
<input type="">
~~~

**type属性**：用来表示输入框的类型

**value属性**：用来表示输入框的值

**placeholder**属性：用来显示提示的文字，文本框没有内容的时候显示（比如我们常见的请输入账号或者邮箱）

下面主要讲一下type的取值：

1. text

   ~~~ html
    <input type="text">
   ~~~

   这个是普通的文本输入框

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           input{
               width:200px;
               height:20px;
               position:absolute;
               left:0;
               top:0;
               right:0;
               bottom:0;
               margin:auto;
           }
       </style>
   </head>
   <body>
       <input type="text" placeholder="请输入账号或者邮箱">
   </body>
   </html>
   ~~~

   如图：![input type_text.gif](https://i.loli.net/2020/08/19/Nw6eXbuAylFK9SY.gif)

2. password

   ~~~ html
   <input type="password">
   ~~~

   这个是密码框，也就是你写的字符是看不见的

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           input{
               width:200px;
               height:20px;
               position:absolute;
               left:0;
               top:0;
               right:0;
               bottom:0;
               margin:auto;
           }
       </style>
   </head>
   <body>
       <input type="password" placeholder="请输入账号或者邮箱">
   </body>
   </html>
   ~~~

   如图：![d1c6c6.gif](https://s1.ax1x.com/2020/08/19/d1c6c6.gif)

3. date

   ~~~ html
   <input type="date">
   ~~~

   这是一个日期选择框，**注意：有兼容性问题**

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           input{
               width:200px;
               height:20px;
               position:absolute;
               left:0;
               top:0;
               right:0;
               bottom:0;
               margin:auto;
           }
       </style>
   </head>
   <body>
       <input type="date">
   </body>
   </html>
   ~~~

   如图：![d1W8VU.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d1W8VU.png)

4. search

   ~~~ html
   <input type="search">
   ~~~

   这是一个搜索框，举个例子，你在手机上百度搜索东西的时候，你会发现，在你打完字后，键盘的回车变成了开始（当然不同的输入法可能会有所不同，不过应该差不了多少），**注意：同样的也有兼容性**

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           input{
               width:200px;
               height:20px;
               position:absolute;
               left:0;
               top:0;
               right:0;
               bottom:0;
               margin:auto;
           }
       </style>
   </head>
   <body>
       <input type="search">
   </body>
   </html>
   ~~~

   如图：就是多了个叉叉![d1IBNT.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d1IBNT.png)

5. range

   ~~~ html
   <input type="range"
   ~~~

   这是一个滑块

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           input{
               width:200px;
               height:20px;
               position:absolute;
               left:0;
               top:0;
               right:0;
               bottom:0;
               margin:auto;
           }
       </style>
   </head>
   <body>
       <input type="range">
   </body>
   </html>
   ~~~

   如图：需要配合js来显示数值![d1TwfU.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d1TwfU.png)

6. color

   ~~~ html
   <input type="color">
   ~~~

   这是一个颜色选择器

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           input{
               width:200px;
               height:20px;
               position:absolute;
               left:0;
               top:0;
               right:0;
               bottom:0;
               margin:auto;
           }
       </style>
   </head>
   <body>
       <input type="color">
   </body>
   </html>
   ~~~

   如图：![d3RKZ8.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3RKZ8.png)

7. number

   ~~~ html
   <input type="number">
   ~~~

   这是一个数字输入框

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
       <style>
           input{
               width:200px;
               height:20px;
               position:absolute;
               left:0;
               top:0;
               right:0;
               bottom:0;
               margin:auto;
           }
       </style>
   </head>
   <body>
       <input type="number">
   </body>
   </html>
   ~~~

   如图：![d3RIWd.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3RIWd.png)

8. checkbox

   ~~~ html
   <input type="checkbox">
   ~~~

   这是一个多选框

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
   </head>
   <body>
       爱好：<input type="checkbox">
   </body>
   </html>
   ~~~

   如图：![d3hTSJ.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3hTSJ.png)

   **有时候页面上有多个多选框，这个时候就要从逻辑上把他们分开，就需要在input元素中加上一个name属性，用来分开不同的多选框**

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
   </head>
   <body>
       爱好：
       计算机<input name="loves" type="checkbox">
       音乐<input name="loves" type="checkbox">
       电影<input name="loves" type="checkbox">
       历史<input name="loves" type="checkbox">
       人文<input name="loves" type="checkbox">
   </body>
   </html>
   ~~~

9. radio

   ~~~ html
   <input type="radio">
   ~~~

   这是一个单选框，要是想默认选中的话，就是用**checked**这个布尔属性

   ~~~ html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
   </head>
   <body>
       性别：
       男<input name="sex" type="radio">
       女<input name="sex" type="radio">
   </body>
   </html>
   ~~~

   如图：**注意：这里必须使用刚才介绍的name属性，不然就不是单选框**![d35NUf.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d35NUf.png)

10. file

    ~~~ html
    <input type="file">
    ~~~

    这是一个选择文件的框

    ~~~ html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <input type="file">
    </body>
    </html>
    ~~~

    如图：![d3oD7q.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3oD7q.png)

> input元素还可以用于制作按钮，但是是很过时的用法，一般不用这种方法，后面的时候会讲到新方法
>
> 当type的值为reset，submit，button的时候，input分别表示重置按钮，提交按钮，普通按钮

#### select元素

下拉列表选择框，通常跟option元素配合使用

~~~ html
<select name="" id="">
     <option value=""></option>
</select>
~~~

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    请选择城市：
    <select name="" id="">
        <option value="">成都</option>
        <option value="">北京</option>
        <option value="">武汉</option>
        <option value="">长沙</option>
    </select>
</body>
</html>
~~~

如图：![d3bgaR.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3bgaR.png)

另外，这个也可以有默认显示的，在那想要默认现实的option中写上一个布尔属性selected

#### textarea元素

文本域，也叫做多行文本框

~~~ html
<textarea name="" id="" cols="30" rows="10"></textarea>
~~~

> 其中cols代表有30列，rows代表有10行

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    请填写简介：
    <textarea name="" id="" cols="30" rows="10"></textarea>
</body>
</html>
~~~

如图：

![d3OJqe.png](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3OJqe.png)

#### 按钮元素

**button**

里面有个type属性，有三种取值：reset，button，submit，默认值是submit

~~~ html
<button> </button>
~~~

它的用法比input作为按钮方便，并且多样性

#### 表单状态

readonly属性：是一个布尔属性，是否只读，不会改变表单显示的样式

disabled属性：是一个布尔属性，是否禁用，会改变表单的显示样式

#### 配合表单元素使用的其他元素

##### label

是一个普通元素，通常配合单选框盒多选框使用

不用这个元素，我们选择的时候，只能通过点圆点来选择，也就是这样：![d3xwTg.gif](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3xwTg.gif)

如果我们使用label这个元素，就可以通过点文字来选择

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    请选择性别：
    <input id="male" type="radio" name="gender">
    <label for="male">男</label>
    <input id="female" type="radio" name="gender">
    <label for="female">女</label>
</body>
</html>
~~~

**通过for属性来进行关联，for里面写的是配合的id名字，比如说男是和第一个input配合的**

如图：![d3zGEF.gif](https://gitee.com/chichengsun/pictureBed/raw/master/img/d3zGEF.gif)

**上面这种方式叫做显示关联，还有一种隐式关联**：

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    请选择性别：
    <label>
        <input id="male" type="radio" name="gender">
        男
    </label>
    <label>
        <input id="female" type="radio" name="gender">
        女
    </label>
</body>
</html>
~~~

==另外注意这种方式，如果想使用隐式关联的话，就必须把label里的for属性删掉，不然是不行的，读者可以试试==

##### datalist

数据列表

该元素本身不会显示到页面，通常用于和普通文本框配合

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <input list="browser" type="text">
    <datalist id="browser">
        <option value="Chrome">谷歌浏览器</option>
        <option value="Edge">微软浏览器</option>
        <option value="Firefox">火狐浏览器</option>
        <option value="Safari">苹果浏览器</option>
        <option value="IE">IE浏览器</option>
    </datalist>
</body>
</html>
~~~

如图：![dGCvgH.gif](https://gitee.com/chichengsun/pictureBed/raw/master/img/dGCvgH.gif)

##### form元素

通常会将整个表单元素放置在form元素内部，作用是当提交表单时，会将form元素内部的表单的内容以合适的方式提交到服务器

form元素对开发静态页面没有什么意义，具体的操作请[自行查看](https://ke.qq.com/webcourse/index.html#cid=414780&term_id=100494778&taid=3622766259885116&vid=5285890796464903835)

##### fieldset元素

表单分组

具体的操作请[自行查看](https://ke.qq.com/webcourse/index.html#cid=414780&term_id=100494778&taid=3622766259885116&vid=5285890796464903835)

### 美化表单元素

#### 新的伪类

##### focus

表示元素聚焦时的样式

![桌面](https://gitee.com/chichengsun/pictureBed/raw/master/img/%E6%A1%8C%E9%9D%A2.gif)

由于每个浏览器的默认聚焦样式不同，所以我们需要使用focus伪类选择器来覆盖掉浏览器的默认聚焦样式

##### checked

单选框或者多选框被选中的时候的样式

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        input:checked+label{
            color:red;
        }
    </style>
</head>
<body>
    <input type="radio" name="sex" id="male">
    <label for="male">男</label>
    <input type="radio" name="sex" id="female">
    <label for="female">女</label>
</body>
</html>
~~~

如图：![checked](https://gitee.com/chichengsun/pictureBed/raw/master/img/checked.gif)

#### 常见用法

##### 重置表单元素的样式

因为不同的浏览器的默认样式不一样，所以我们有必要重置

~~~ css
input,button,textarea,selection{
    border:none;
}
input:focus,
selection:focus,
button:focus,
textarea:focus{
    outline:none;
    outline-offset:none;
}
~~~

##### 设置textarea是否可以调整尺寸

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <textarea name="" id="" cols="30" rows="10"></textarea>
</body>
</html>
~~~

没有设置之前，默认是可以调整的：![textarea](https://gitee.com/chichengsun/pictureBed/raw/master/img/textarea.gif)

![image-20200821145357754](https://gitee.com/chichengsun/pictureBed/raw/master/img/image-20200821145357754.png)

textarea里面有个属性：resize，有六种取值：

1. both

   默认值，两个方向都可以调整

2. none

   两个方向都不可以调整

3. horizontal

   只能水平调整

4. vertical

   只能垂直调整

   另外两个值不管

##### 文本框边缘到内容的距离

举个例子

~~~ html
<input type="text">
~~~

方法一：

~~~ css
<style>
    input{
        padding:0 10px;
    }
</style>
~~~

![文本框和内容的距离](https://gitee.com/chichengsun/pictureBed/raw/master/img/%E6%96%87%E6%9C%AC%E6%A1%86%E5%92%8C%E5%86%85%E5%AE%B9%E7%9A%84%E8%B7%9D%E7%A6%BB.gif)

方法二：

~~~ css
<style>
    input{
        text-indent:1em;
    }
</style>
~~~

![文本框内容的距离2](https://gitee.com/chichengsun/pictureBed/raw/master/img/%E6%96%87%E6%9C%AC%E6%A1%86%E5%86%85%E5%AE%B9%E7%9A%84%E8%B7%9D%E7%A6%BB2.gif)

##### 控制单选和多选的样式

首先你要知道，一般页面上好看的单选框或者时多选框都不是使用input元素，都是自己做的

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .radio{
            width:12px;
            height:12px;
            border:1px solid #999;
            border-radius:50%;
            cursor:pointer;
        }
        .radio.checked{
            border-color:#008c8c;
        }
        .radio.checked::after{
            content:"";
            display:block;
            width:6px;
            height:6px;
            background:#008c8c;
            border-radius:50%;
            margin-left:3px;
            margin-top:3px;
        }
    </style>
</head>
<body>
    <div class="radio checked">

    </div>
</body>
</html>
~~~

如图：![image-20200821222344596](https://gitee.com/chichengsun/pictureBed/raw/master/img/image-20200821222344596.png)

完整的如下：

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .radio-item .radio{
            width:12px;
            height:12px;
            border:1px solid #999;
            border-radius:50%;
            cursor:pointer;
            display:inline-block;
        }
        .radio-item input:checked+.radio{
            border-color:#008c8c;
        }
        .radio-item input:checked~span{
            color:#008c8c;
        }
        .radio-item input:checked+.radio::after{
            content:"";
            display:block;
            width:6px;
            height:6px;
            background:#008c8c;
            border-radius:50%;
            margin-left:3px;
            margin-top:3px;
        }
        input{
            display:none;
        }
    </style>
</head>
<body>
    <label class="radio-item">
        <input type="radio" name="gender">
        <span class="radio"></span>
        <span>男</span>
    </label>
    <label class="radio-item">
        <input type="radio" name="gender">
        <span class="radio"></span>
        <span>女</span>
    </label>
</body>
</html>
~~~

![自己做的单选框](https://gitee.com/chichengsun/pictureBed/raw/master/img/%E8%87%AA%E5%B7%B1%E5%81%9A%E7%9A%84%E5%8D%95%E9%80%89%E6%A1%86.gif)

### 表格元素

在CSS技术出现之前，网页通常使用表格布局，后台管理系统可能会使用表格布局

一般一个网站分为前台和后台：

前台：面向用户

后台：面向管理员，对界面要求不高，对功能性要求高

表格为什么不再适用于网页布局？

> 渲染速度太慢

table包括caption（表格标题），thead（表头），tbody（表格主体），tfoot（表尾），这四个里面包括tr（表格行），表格行里面包括th（标题单元格），td（单元格）

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        table{
            width:100%;
            border-collapse:collapse;
        }
        table caption{
            font-size:2em;
            font-weight:bold;
            margin:1em 0;
        }
        th,td{
            border:1px solid black;
            text-align:center;
            padding:20px;
        }
        thead tr{
            background:#008c8c;
            color:#fff;
        }
        tbody tr:nth-child(odd){
            background:#eee;
        }
        tbody tr:hover{
            background:#ccc;
        }
        tbody tr td:first-child{
            color:#f40;
        }
        tfoot td{
            text-align:right;
            padding-right:20px;
        }
    </style>
</head>
<body>
    <table>
        <caption>这是表格的标题</caption>
        <thead>
            <tr>
                <th>1</th>
                <th>2</th>
                <th>3</th>
                <th>4</th>
                <th>5</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
            <tr>
                <td>数据1</td>
                <td>数据2</td>
                <td>数据3</td>
                <td>数据4</td>
                <td>数据5</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="5">合计：xxxx</td>
            </tr>
        </tfoot>
    </table>
</body>
</html>
~~~

> 合并行或者列要使用rowspan或者colspan属性，如上面的colspan="5"

![image-20200822105109180](https://gitee.com/chichengsun/pictureBed/raw/master/img/image-20200822105109180.png)

## CSS进阶1

### @规则（at-rules）

at-rules:@规则，@语句，CSS语句，CSS指令

#### import

~~~ css
@import "路径";
~~~

导入另外一个css文件

~~~ css
@import "reset.css";
~~~

#### charset

~~~ css
@charset "utf-8";
~~~

==这里有个注意的点：如果你使用了这个，那么这一行代码必须写在css文件的第一行==

### web字体和图标

#### web字体

如果用户电脑上没有安装相应的字体，则会强制让用户下载此字体（当然这个过程用户是看不见的）

**使用@font-face指令制作一个新字体**

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* 制作一个新字体，名字叫做"Youzai Ti" */
        @font-face{
            font-family:"Youzai Ti";/* 这是给你的这个字体取一个名字 */
            src:url(./font/悠哉字体.ttf)
        }
        P{
            font-family:"Youzai Ti";
        }
    </style>
</head>
<body>
    <p>长夜将至，我从今开始守望</p>
</body>
</html>
~~~

![image-20200823101135806](https://gitee.com/chichengsun/pictureBed/raw/master/img/image-20200823101135806.png)

#### 字体图标

iconfont.cn，这是一个非常好用的图标网站，这一小节具体的操作方式大家可以[自行查看](https://ke.qq.com/webcourse/index.html#cid=414780&term_id=100494778&taid=3622783439754300&vid=5285890796465035914https://ke.qq.com/webcourse/index.html#cid=414780&term_id=100494778&taid=3622783439754300&vid=5285890796465035914)

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./icon/iconfont.css">
</head>
<body>
    <div class="iconfont icon-ditu"></div>
    <div class="iconfont icon-yonghu"></div>
</body>
</html>
~~~

~~~ html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="//at.alicdn.com/t/font_2022651_kud5wtxp1tj.css">
</head>
<body>
    <div class="iconfont icon-ditu"></div>
    <div class="iconfont icon-yonghu"></div>
</body>
</html>
~~~

~~~ html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        @font-face {
            font-family: 'iconfont';
            /* project id 2022651 */
            src: url('//at.alicdn.com/t/font_2022651_kud5wtxp1tj.eot');
            src: url('//at.alicdn.com/t/font_2022651_kud5wtxp1tj.eot?#iefix') format('embedded-opentype'),
                url('//at.alicdn.com/t/font_2022651_kud5wtxp1tj.woff2') format('woff2'),
                url('//at.alicdn.com/t/font_2022651_kud5wtxp1tj.woff') format('woff'),
                url('//at.alicdn.com/t/font_2022651_kud5wtxp1tj.ttf') format('truetype'),
                url('//at.alicdn.com/t/font_2022651_kud5wtxp1tj.svg#iconfont') format('svg');
        }
        .iconfont{
            font-family:"iconfont";
            font-style:normal;
        }
    </style>
</head>

<body>
    <div class="iconfont">&#xe627;</div>
    <div class="iconfont">&#xe640;</div>
</body>

</html>
~~~