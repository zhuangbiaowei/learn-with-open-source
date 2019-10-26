# 3. 选择一个开源项目

<!-- toc -->

## 3.1. 到哪里寻找开源项目

### 开源基金会

大部分开源项目都来自于开源社区，而大部分开源社区背后都有基金会在运作，比较知名的有Apache基金会（以Java技术为主的开源软件），Linux基金会（专注于Linux系统的开源软件），Eclipse基金会（专注于基于Eclipse IDE的开源软件），Jboss基金会（专注于JAVA EE方面的开源项目）等。每个基金会都会有目前该基金会正在进行的项目列表，我们可以从其中寻找自己感兴趣的项目。

* Apache：[https://projects.apache.org/projects.html?name](https://projects.apache.org/projects.html?name)
* Linux：[http://www.linuxfoundation.org/programs](http://www.linuxfoundation.org/programs)
* Eclipse：[http://www.eclipse.org/projects/listofprojects.php](http://www.eclipse.org/projects/listofprojects.php)
* Jboss：[http://www.jboss.org/projects](http://www.jboss.org/projects)

### 开源项目托管网站

另外，每个开源项目都需要有自己的管理平台，各大基金会的开源项目也不例外，因此，各个开源项目的托管网站是也是一个寻找开源软件的好去处。

目前在业界比较知名的项目托管网站主要有SourceForge，GitHub。

微博上的@OpenERP_Jeff 补充说：[launchpad](https://launchpad.net/)是一个很重要的开源hosting网站，著名的开源项目有ubuntu、mysql和zope。项目计划、蓝图、代码库、bug管理、翻译都很完整。

| 服务提供商                                    | SVN  | Git  | Mercurial | 介绍                                       |
| ---------------------------------------- | ---- | ---- | --------- | ---------------------------------------- |
| [Google Code](http://code.google.com/)   | 支持   | 支持   | 支持        | Google Code属于“富二代”，其在速度上，使用体验上都优于其他几个托管网站，其中最值得一提的是其丰富的帮助文档，许多文档还有中文版本。因此，对于初学者来说，比较容易上手，也可以获得一个很好的学习机会。当然，因为都是google.com的域名，所以时不时的会访问不了管理界面，原因大家懂的。另外，因为使用简单方便，相应的其在功能上就相对较弱一点。但是应付一般的项目还是绰绰有余。注：**已经于2016年4月1日关闭了** |
| [Sourceforge](http://http//sourceforge.net/) | 支持   | 支持   | 支持        | SourceForge可以算是开源界的托管始祖，很多古老的，知名的开源项目都托管在它上面，其对开源界的贡献估计可以和Apache对 Java界的贡献相提并论了。因此，其在功能上经过了长时间的考验，大家想要的功能都能找到。不过，因为强大，其上手难度也相对较高，而且全英文界面，对于英文较弱的同学来说也是一件很痛苦的事。 |
| [Github](http://github.com/)             | 支持   | 支持   | 不支持       | GitHub属于托管界的新贵，伴随着Git的蓬勃发展而发展。越来越多的开源软件使用Github托管。最近因Rails漏洞被Hacker黑了也让其处于媒体的风口浪尖。这个事件从一个侧面反映了其在业界的影响力。 |
| [CodePlex](http://www.codeplex.com/)     | Yes  | Yes  | Yes       | 微软的开源项目基地                                |
| [BitBucket](https://bitbucket.org/)      | No   | Yes  | Yes       | Python的项目在上面比较多                          |
| [launchpad](https://launchpad.net/)      | No   | No   | No        | 使用[bzr](http://bazaar.canonical.com/)管理代码，项目很多，如Ubuntu等，中国大陆访问速度巨慢无比 |

维基百科有一个词条，列出了非常非常多的开源托管服务的比较：

* [Comparison of open source software hosting facilities](http://en.wikipedia.org/wiki/Comparison_of_open_source_software_hosting_facilities)
* [自由软件主机服务比较](http://zh.wikipedia.org/wiki/%E8%87%AA%E7%94%B1%E8%BD%AF%E4%BB%B6%E4%B8%BB%E6%9C%BA%E6%9C%8D%E5%8A%A1%E6%AF%94%E8%BE%83)

### 技术社区

像ITeye、InfoQ、OSChina、CSDN等国内知名的技术社区都非常关心开源软件的发展，在社区新闻、月刊等载体上都有最新的，流行的开源软件介绍。同时在社区，还有一个很大的好处，你会找到很多志同道合的朋友，这可是学习过程中的一大乐事。

### 各大科技公司的研究院

Google的BigTable论文，Amazon的Dynamo论文开启了目前火热的云计算时代，各大科技公司对技术领域的引领能力毋庸置疑，同时，很多公司也是开源运动的忠实支持者，像国外的Google、Facebook、Yahoo、国内的淘宝、百度、~~盛大~~、豆瓣等，连曾经的坚决反对者 Microsoft也开始通过赞助Apache基金会扭转自己在开源界的形象。关注各大科技公司的研究院最新的开源软件可以了解目前整个业界的技术趋势，而且他们开源的软件的未来发展前景都比较看好，因此，是一个寻找开源软件的有效途径。

### 谷歌编程之夏(Google Summer of Code)

我个人觉得GSoC是一个寻找开源项目的好地方。原因有以下几点：

1. GSoC有一个[历年来的参与者列表](https://www.google-melange.com/archive/gsoc)([https://www.google-melange.com/archive/gsoc](https://www.google-melange.com/archive/gsoc))，这个列表中的有各种各样的开源组织可以让想参与的人挑选（今年的列表上有180个组织）。
2. 参与者列表上的组织是经过一定的审核才选出来的，选拨出来的组织一般质量比较好，社区活跃度也很高。
3. 列表上的组织为了吸引参加人员，一般在项目的主页上会有专门的wiki为参加人员导航(比如这个[DragonFlyBSD项目](http://www.dragonflybsd.org/docs/developer/gsoc2012student/)([http://www.dragonflybsd.org/docs/developer/gsoc2012student/](http://www.dragonflybsd.org/docs/developer/gsoc2012student/)))，很适合新手快速了解这个项目。
我想即使无法参加GSoC本身，通过GSoC的预热也是一个很不错的机会，可以让想要参与开源项目的人有一个很好的入口。

注：本小节来自于Ashi的邮件，在此表示感谢！

### 搜索引擎

如果您对某类技术特别感兴趣，或者遇到某个技术难题想找业界成熟的解决方案，搜索引擎（Google，Bing等）都是一个不错的工具，其在我们寻找开源软件的过程中也起同样的作用。通过一些关键词的罗列就能帮助我们找到感兴趣的开源项目。

### 博客和微博

关注各个领域大牛们的博客和微博，他们会紧跟技术节奏给我们推荐他们领域最新的开源软件，甚至会为我们讲解这些开源软件的底层实现原理，带领我们入门，这是多么高尚的行为啊。

关注各大科技公司的博客和微博，他们也会经常透露自己的开源计划，以及分析业界的一些开源软件在自己公司内部的应用，这对我们深入了解一个开源软件的技术价值有很大的帮助。

### 微信公众号



### 技术问答网站

这是最直接的一个方式，在知乎、StackOverflow、Quora等问答网站直接请人推荐几款开源软件，工程师的热情会让你受宠若惊的，很有可能向你推荐某个开源软件的就是这个开源软件的创始人。

### 维基百科

在维基百科上，有很多辛勤的人们，在整理着各种相关的资料，例如：

* [http://en.wikipedia.org/wiki/Open-source_software](http://en.wikipedia.org/wiki/Open-source_software)
* [http://en.wikipedia.org/wiki/List_of_open_source_software_packages](http://en.wikipedia.org/wiki/List_of_open_source_software_packages)
* [http://en.wikipedia.org/wiki/Comparison_of_open_source_software_hosting_facilities](http://en.wikipedia.org/wiki/Comparison_of_open_source_software_hosting_facilities)

等等，在其中搜索相关的词条，还能发现很多的宝藏。

## 3.2. 什么样的开源项目适合初学者

### 缘起

说实话，在当初列这个提纲的时候，我并没有想好如何写这一节。但是，开放地做事情，就常常会有奇妙的事情发生，佛家称之为“助缘”，各种对这件事情有帮助的缘分，都会在不经意间出现。

一位叫李军的朋友，给我发来邮件，信中写道：“我想是否我们能够通过沟通，然后你再对我有些了解，给我指出点建议，并且是详细的建议，我看学apache开源框架应该不错的，不知道我是否适合，谢谢。期待你的回复。”

在与他的往来邮件中，我也真的将这一节渐渐地想清楚了。另外，在与李军的讨论中，我还发现，需要开辟一个专门的章节，讨论：“学习开源项目，能够提升软件开发中的哪些能力。”

在此，我想对李军表示感谢，更希望有越来越多的朋友，参与到这个文档的讨论中来，相信它会变得越来越完善。

### 明确自己的目的

选择一个开源软件，首先要明确的，是自己的动力何在。是出于兴趣？还是出于工作需要？比如，有人对于搜索引擎特别感兴趣，想了解搜索引擎是怎么做出来的？那么首先可以考虑先寻找一些专业的书籍，来了解一些关键的知识点。如果对于某一领域的知识点，缺乏必要的了解，可能完全无法理解一个项目里的代码。在掌握初步的知识以后，自然可以去找Lucene、Sphinx来学习。也可能是出于工作需要，比如平时是用PHP开发Web应用，已经在用某一个常见的PHP框架了，希望能够对这个框架有一个深入的学习了解，甚至希望横向地比较多个不同的PHP Web框架，这些都是非常清晰的目的。自然在学习的过程中，不太会迷失方向。

比较危险的一种，是听说某某项目很有名气，甚至是为了将来找工作比较容易，就贸然一头扎进某个项目中去了。怀有这种学习目的的人，往往会选择到那种很庞大，也很成熟的项目，打开文件夹一看，成百上千的源文件，根本无法看完，一下子就懵了，再就是颓了。心想自己大概不是学软件开发的料吧～～

### 优先选择能够独立运行的项目

开源的项目有很多种类，能够独立运行的项目，当然很多。但是也有不少项目，是其他开源项目的插件、类库、扩展包之类的东西，这些在一开始接触开源的时候，最好不要涉猎，因为理解他们，可能会需要理解他们背后的那个庞然大物，往往会遭遇很多难解的细节，一不小心，就进行不下去了。

当然，还有一类项目，他们虽然是独立运行，但是想要让他们独立运行成功，还得安装、配置很多其他的依赖项目，这个往往会让初学者特别绝望，搞了一个礼拜，居然这个项目都还没有运行起来...

所以，小的、能够独立运行的、不依赖于太多其他项目的开源项目，可以优先选择。

PS. 在Docker出现以后，运行一个项目，往往只需要一行简单的命令。在Github上，也能找到很多demo项目，或者是docker-compose.yml文件，这些是很好的入手点。

### 选择活跃的项目

项目的活跃程度，包括两个部分，一个是开发者提交新代码的频繁程度。另一个是在社区中对于这个项目的讨论热烈程度。提交代码越是活跃，提交的人越多，越能证明这个项目是很有价值的，也证明这个项目是值得你花精力去学习的。而项目在社区讨论的热烈程度，则能够确保当你遇到问题的时候，能够搜索到别人的答案，或者你自己提问以后，能够有人热心回答你。

当然，活跃程度都是相对的，如果你真的对一个项目感兴趣，可以直接试着给这个项目的作者发邮件，提问题。大多数开发者都会很高兴有人关注他的项目，也会通常会热心的回答你的问题的。

### 判断代码质量

并非所有的开源项目，都是高手写的，都值得你去学习。事实上，有很多垃圾开源项目，代码仔细一看，写得真是一塌糊涂。所以，试着阅读一下这个项目的代码。至于如何判断一个项目的代码质量，之前我在知乎回答过一个类似的问题“如何让自己写的代码易维护？”，推荐各位朋友参考一下。

当然，更加推荐的，是阅读《Clean Code》一书，非常好的一本介绍如何提高代码质量的书。附一篇书评，可以一读：[《写代码犹如写文章》](http://book.douban.com/review/5199308/)

### 选择合适的版本

最后，面对已经发展了多年的开源项目，最好不要选择最新的版本。如果你是在工作中想要使用这个项目，当然应该选择最新的稳定版，甚至测试版、 beta版。但是如果是出于学习的目的，为了减少复杂度，快速地理解这个项目的核心结构与开发思想，选择第一个稳定版，是一个比较妥当的办法。

然后，在初步理解了第一个版本的代码之后，再不断地通过阅读changelogs，追踪最新的版本中的代码变更，体会作者修改代码的目的、手法与技巧。这样应该会有很大的收获。

## 3.3. 值得推荐给大家的开源项目

| 项目名称                                     | 语言（平台）                        | 所属领域          | 推荐理由                                     |
| ---------------------------------------- | ----------------------------- | ------------- | ---------------------------------------- |
| [Petshop4.0](http://msdn.microsoft.com/en-us/library/Aa479070) | NET                           | 企业开发          | 1.微软官方用来展示.Net企业开发实力的项目,架构优雅;2.涉及中小型企业开发常用技术;3.网络资源较多 |
| [Haozesfx](http://haozesfx.codeplex.com/) | NET                           | Winform,SIP协议 | 1.基于飞信实现的开源项目，实用性强,方便二次开发;2.结构清晰，设计成熟;3.实现了SIP协议 |
| [ThinkPHP](http://www.thinkphp.cn/)      | PHP                           | Web框架         | 1.应用较为广泛的Web开发框架，成熟稳定;2.集成多项先进的设计思想;3.活跃的社区支持和完善的中文文档(帮助手册,Demo,代码注释) |
| [Nginx](http://nginx.org)                | C/Linux/Unix/windows/MAC      | 基础设施          | 代码优秀简洁，插件系统牛逼，HTTP协议可谓当今码农的必备知识          |
| [bottle](http://bottlepy.org)            | Python/Linux/Unix/windows/MAC | web开发         | 代码优秀简洁，3000多行代码（包括注释）搞定web server        |
| [memcached](http://memcached.org/)       | C                             | 基础设施          | Free & open source, high-performance, distributed memory object caching system。by Jun Guo |
| [Docker](https://docker.com/)            | Go                            | 容器,基础设施       | 目前最热容器技术的基石，有孙宏亮《Docker源代码解读》可供参考        |

## 3.4 各语言的Awesome List

github中有人总结过各个语言在不同的应用方向上值得推荐的开源项目列表, 即Awesome List. Awesome List不仅可以方便大家找到优秀的项目进行学习, 还可以让大家方便地找到各种已有的轮子来进行开发.

| 语言/平台             | Awesome List 地址 |
| ---------------- | ----------------|
| Java | [awesome-java](https://github.com/akullpp/awesome-java) |
| c++ | [awesome-cpp](https://github.com/fffaraz/awesome-cpp) |
| python | [awesome-python](https://github.com/vinta/awesome-python) |
| go | [awesome-go](https://github.com/avelino/awesome-go) |
| javascript(浏览器) | [awesome-javascript](https://github.com/sorrycc/awesome-javascript) |
| nodejs | [awesome-nodejs](https://github.com/sindresorhus/awesome-nodejs) |
| .net | [awesome-dotnet](https://github.com/quozd/awesome-dotnet) |
| .net core | [awesome-dotnet-core](https://github.com/thangchung/awesome-dotnet-core) |
| ruby | [awesome-ruby](https://github.com/markets/awesome-ruby) |
| php | [awesome-php](https://github.com/ziadoz/awesome-php) |
| rust | [awesome-rust](https://github.com/rust-unofficial/awesome-rust) |
| dart | [awesome-dart](https://github.com/yissachar/awesome-dart) |
| ios(Objective-C和swift) | [awesome-ios](https://github.com/vsouza/awesome-ios) |
| android | [awesome-android](https://github.com/snowdream/awesome-android) |


[上一章](Start.md) | [下一章](Hello-world.md)

