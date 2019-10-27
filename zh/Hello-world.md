# Hello World

<!-- toc -->

## 下载源代码的N种办法

### 关于源代码管理与版本控制

首先需要介绍一些基础的概念，这里只是简要的介绍，比较详细的介绍，可以参见[Understanding Version-Control Systems](http://www.catb.org/%7Eesr/writings/version-control/version-control.html)，期待有人能够将其翻译为中文（或者已经有中译本了，欢迎告知我）。

**源代码([Source Code](http://en.wikipedia.org/wiki/Source_code))**：也就是通常一个软件，由程序员编写，并且可以被其他程序员阅读的，可以被直接执行/编译后执行的文本代码。

**源代码管理与版本控制([Version control/Revision control](http://en.wikipedia.org/wiki/Revision_control))** ：由于源代码数量急剧膨胀、变更越来越频繁，可能修改同一个源文件的人也越来越多，需要将这些代码管理起来，于是每次变更被称之为一次修正 (Revision)。版本控制更准确的说法应该是“Revision control”，每当我们修改一个源代码文件并再次保存时，就出现了两个不同的版本，一个是修改前的，一个是修改以后的。而版本控制，就是确保源文件的每一次修改，都被记录下来，并且可以知道是被谁修改的，是因为什么原因而修改的。必要时，可以找回任何一个版本的源代码。

**软件版本号([Software Version](http://en.wikipedia.org/wiki/Software_versioning))** ：这里的版本，是另外一个概念，源代码中的任何一个文件，都存在一个修订版本号，而作为整个软件，无论对内称呼还是对外发布，都需要一个更加正式的、完整的版本号。前者的英文是Revision，而后者的英文是Version。因此，当我们谈到版本管理的时候，很可能是同时谈到两者：一个是源代码的Revision，一个是整个项目的Version。

**版本控制工具([Revision control software](http://en.wikipedia.org/wiki/List_of_revision_control_software))** ：为了更好地管理源代码，程序员们开发出了林林种种的版本控制工具，有闭源的，也有开源的。而现在市面上流行的，已经几乎全是开源的了。简单的列出几种在下面：

* 仅管理本地源文件
  * 免费/开源：SCCS (1972) RCS (1982)
  * 闭源：PVCS (1985)
* C/S方式管理源代码
  * 免费/开源：CVS (1990) CVSNT (1998) Subversion (2000)
  * 闭源：Software Change Manager (1970s) ClearCase (1992) CMVC (1994) Visual SourceSafe (1994) Perforce (1995) StarTeam (1995) MKS Integrity (2001) AccuRev SCM (2002) SourceAnywhere (2003) SourceGear Vault (2003) Team Foundation Server (2005) Rational Team Concert (2008)
* 分布式管理源代码
  * 免费/开源：GNU arch (2001) Darcs (2002) DCVS (2002) SVK (2003) Monotone (2003) Codeville (2005) Git (2005) Mercurial (2005) Bazaar (2005) Fossil (2007) Veracity (2011)
  * 闭源：TeamWare (1990s?) Code Co-op (1997) BitKeeper (1998) Plastic SCM (2006)

**更多参考资料：**
* 上述概念所附带的四个link，都是来自于英文版的wikipedia，有些也有附带的中文版本，顺着这四个主条目的介绍，可以点击阅读更多的词条，加深了解。
* [版本控制工具历史的10个里程碑](http://blog.jobbole.com/14489/) 本文中的一些link，也非常值得点击过去细细阅读。
* [为什么软件项目从集中式迁移到分布式版本控制系统的热情持续不减?](http://codinn.com/projects/why-projects-moving-to-dvcs/view/) 最新趋势，值得了解。

### 寻找早期开源项目的源代码

取得源代码的方式千千万万，现在有越来越多的开源项目，已经开始逐步采用规范的，统一的方式，提供自己的源代码以供下载。但是在开源项目发展的早期，还有很多是以并非规范的方式提供的。而在寻找一些开源项目的源代码时，google与wikipedia，将会是我们的好帮手。当然，还有更早期的一些开源项目，就是在邮件列表里发一个带附件的邮件，要找到那种项目的源代码，就得有考古的功力了。

这里举一个例子，来描述一下我寻找某一个开源项目源代码的过程。

有一个项目叫做GForge，在早期还是一个较为著名的开源托管平台的项目，这个托管平台的代码本身也是以GNU许可开源的。假设，我首先是在wikipedia上发现了这个项目： http://en.wikipedia.org/wiki/GForge
看到这个项目的介绍，我觉得大概不错，于是我就看到下面的External links，列出了四个外部链接：

* GForge official website
* GForge project open source page
* GForge Advanced Server page
* FusionForge project open source page

一个比较合理的猜测，自然是首先访问[GForge project open source page](http://gforge.org/projects/gforge/)因为这个项目托管在自己的开源平台上，应该是顺理成章的。进入这个页面之后，我迷惑了一下，他竟然是一个中文界面，里面有文件、档案发行和SVN三个疑似可以下载的地方。经过试错，我发现：文件里没啥东西。SVN的存取信息里告诉我，可以svn checkout [http://gforge.org/svn/gforge](http://gforge.org/svn/gforge)获得最新的源代码。而在档案发行里，我发现了[各个历史版本的列表](http://gforge.org/gf/project/gforge/frs/?action=FrsReleaseBrowse&frs_package_id=2)而最新的那个5.0版本并非一个压缩包，而是一个txt文件，里面告诉我：GForge项目已经被全部重新设计和重写，目前可以在[as-help](http://gforge.org./gf/project/as-help/)这个项目里看到。另外，如果要下载最新的版本，可以到[http://gforgegroup.com/es/download.php](http://gforgegroup.com/es/download.php)

而如果要下载早期的版本，那么历史版本列表的那些gforge-x.x.tag.bz2，就可供我挑选了。

更加糟糕的情况也许会需要我们在google里搜索：“XXX source code download”这样的关键字，才能找到，这里不再赘述。

### SVN、Git、Mercurial快速介绍

三本值得一看的书

* [Subversion 与版本控制](http://svnbook.red-bean.com/)
* [progit 中文版](https://progit.bootcss.com/)
* [hginit.com 中文版](https://zh-hginit.readthedocs.io/en/latest/)

另外

* [Mercurial 权威指南](https://i18n-zh.googlecode.com/svn/www/hgbook/zh/index.html)(这本书的翻译尚未完成，因此推荐直接阅读英文版)

基本上，如果想要开始使用并深入掌握这三种版本管理工具的其中一种，都可以由此入门，并最终融会贯通。

**SVN如何获取代码**

如果你在windows平台下，推荐安装[TortoiseSVN](http://tortoisesvn.net/downloads.html)，然后，就在图形界面下简单操作。

填入SVN来源URL，直接CheckOut出最新的版本(HEAD revision)，或者选择某个具体的版本(Revision)，选择CheckOut的目录即可。

如果你在linux/mac平台下，那么命令行会非常方便：

    svn checkout http://SiteDomain/path/ProjectName 获取最新的版本
    svn checkout http://SiteDomain/path/ProjectName --revision {....} 获取某个版本
    svn checkout http://SiteDomain/path/ProjectName/tags/Release_x.xx 获取上某某tag的具体发行版本

**Git如何获取代码**

如果一个git管理的项目放在github这样的成熟项目托管平台，获取代码是非常简单的，而且网站还会有详细的操作指南，教你一步一步的如何操作。

至少，你可以先参照[GitHub的指南](http://help.github.com/win-set-up-git/)，搭建自己的git开发环境。

然后，获取代码也极其简单：

这里要注意的是，gitHub给出的项目地址GitRepoURL不止一个，这是因为git是支持多种协议的，例如默认的ssh，https等。

    git clone GitRepoURL

**Mercurial如何获取代码**

正如GitHub是主打Git的开源托管平台，[BitBucket](https://bitbucket.org/)则是一个主打Mercurial的开源托管平台。因此，我们可以在这里找到关于Mercurial的操作指南。而因为Git的飞速发展，现在BitBucket也开始同时支持Git，所以在[bitbucket 101](http://confluence.atlassian.com/display/BITBUCKET/Set+up+Git+and+Mercurial)，可以同时看到两种工具的安装指南。

    hg clone HgRepoURL

即可获得Mercurial仓库的完整副本。（Mercurial又简称为hg）

### 基于包管理的方式获取源代码

这是新增的一个小节，因为在很多动态脚本语言中，都有类似的包管理工具，在wikipedia中有一个词条[List of software package management systems](http://en.wikipedia.org/wiki/List_of_software_package_management_systems)，其中的Application-level package managers小节，就介绍了十多种不同语言的包管理工具。

想要更进一步的了解软件包管理系统，可以阅读[英文版](http://en.wikipedia.org/wiki/Package_management_system) [中文版](http://zh.wikipedia.org/wiki/%E8%BD%AF%E4%BB%B6%E5%8C%85%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F)

与过去的很多开源项目不同，这种脚本语言的包管理工具实在是方便，一行命令，连下载，带安装，就都有了。本章4.2节的让代码运行起来里，会举几个这样的例子。这里就不再赘述了。

**Application-level package managers**

| 语言     | 包管理工具                                    | 相关文档与资源                                  |
| ------ | ---------------------------------------- | ---------------------------------------- |
| Perl   | [CPAN](http://www.cpan.org/)             | [[1]](http://en.wikipedia.org/wiki/CPAN) [[2]](http://www.cpan.org/misc/cpan-faq.html) |
| PHP    | [PEAR](http://pear.php.net/) [PECL](http://pecl.php.net/) | [[1]](http://en.wikipedia.org/wiki/PHP_Extension_and_Application_Repository) [[2]](http://pear.php.net/manual/en/) |
| Ruby   | [RubyGems](http://www.rubygems.org/) [Bundler](http://bundler.io/) | [[1]](http://docs.rubygems.org/) [[2]](http://rubydoc.info/github/carlhuda/bundler/master/Bundler) |
| Java   | [Maven](http://maven.apache.org/)        | [[1]](http://en.wikipedia.org/wiki/Apache_Maven) [[2]](http://maven.apache.org/guides/getting-started/maven-in-five-minutes.html) |
| Python | [EasyInstall](http://en.wikipedia.org/wiki/EasyInstall) [PyPI](https://pypi.python.org/pypi) | [[1]](http://peak.telecommunity.com/DevCenter/PythonEggs) [[2]](http://en.wikipedia.org/wiki/Python_Package_Index) |
| NET    | [NuGet](http://nuget.codeplex.com/)      | [[1]](http://nuget.codeplex.com/documentation) |
| NodeJS | [npm](http://npmjs.org/)                 | [[1]](http://npmjs.org/doc/)             |

## Windows下的开发环境准备

Windows，MacOS，Linux是当下主流的三大操作系统。很大一部分计算机用户出于经济适用和方便的原因，都选择 Windows操作系统，但对于计算机学习者来说，却不可避免的会使用Linux，因为你的大多数程序最终是跑在线上的 Linux服务器上，而且 Linux相对与其他系统，具有安全、稳定、高效、资源消耗少、易操作等一系列特点。所以，这里单独介绍除了虚拟机外 Windows环境下使用 Linux系统的一个简单方法（WSL），方便 Windows用户学习使用 Linux。

### 关于WSL

[WSL](https://baike.baidu.com/item/wsl/20359185?fr=aladdin)（Windows Subsystem for Linux）是一个在 Windows 10 上能够运行原生 Linux二进制可执行文件的兼容层。
Linux 的 Windows 子系统让开发人员可以直接在 Windows 上运行 Linux 环境（包括大多数命令行工具，实用程序和应用程序），而无需建立在虚拟机的开销之上，整个系统只有200多兆，但基本包含了你能用到的所有功能，并且和 Windows完美互操作(省去 Linux挂载本地 Windows分区或目录的操作)，目前 Linux的 Windows子系统已经相当完善，可当作完整 Linux 系统使用（极少部分Windows 应用不能正常运行）。

在WSL下，你可以实现如下功能，但不仅限于这些操作：

	1. 在 Microsoft Store 中选择你偏好的 GNU/Linux 分发版（推荐Ubuntu）；
	
	2. 运行 Bash shell 脚本和 GNU/Linux 命令行应用程序;
	
	3. 使用分发包管理器安装其他软件;
	
	4. 使用类似于 Unix 的命令行 shell 调用 Windows 应用程序;
	
	5. 在 Windows 上调用 GNU/Linux 应用程序。

WSL 体系结构的新版本 WSL2 也已经可以使用，WSL与 WSL2 的区别可自行查询。当然，你也可以选择虚拟机或者安装双系统，但传统的 [VM](https://baike.baidu.com/item/%E8%99%9A%E6%8B%9F%E6%9C%BA/104440?fromtitle=VM&fromid=16532539) (虚拟机推荐VMware)启动速度慢，隔离会消耗大量资源，需要时间进行管理，双系统更加消耗内存以及带来管理上的不便，不过这两种情况下的系统更能显示出 Linux的完整结构和操作，大家可以根据自己需求以及电脑配置进行选择。 


### WSL的安装 

**下载安装流程**

	1. 打开 Windows “启用或关闭Windows功能”；
	2. 勾选 “适用于Linux的Windows子系统”；
	3. 在 Windows应用商店搜索“Linux”，选择您喜欢的Linux版本，推荐Ubuntu；
	4. 正常下载安装（建议不要修改安装路径）；
	5. 安装以后即可打开Ubuntu使用Linux命令对windows文件进行操作；

**升级到WSL2方法**

	1. 按以上流程成功安装Ubuntu，且版本必须是18917之后的版本；
	2. 在搜索框中输入Powershell点击Run as Administrator；
	3. 在打开的命令行中输入 Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform 启用虚拟机平台可选组件；
	4. 完成后重启系统，之后依旧以管理员身份打开powershell，输入wsl -l查看已经安装的子系统；
	5. 输入命令wsl --set-version Ubuntu-18.04 2，这里的Ubuntu-18.04换成你的子系统名称（这里再强调一遍，必须是18917之后的版本）；
	6. 输入wsl -l -v查看目前WSL版本，查看是否已经成功安装。

**其他说明**

推荐一款好看的 Windows端的终端模拟器——Fluent Terminal，如需要的话可自行搜索相关教程（[GitHub](https://github.com/felixse/FluentTerminal)），在设置中选择WSL，之后子系统的所有操作都可以在Fluent terminal中操作，美观的不是一点。
WSL使用与Linux使用一致，尽情享用吧。

## 让代码运行起来

经过思考，决定将这一小节以实例的方式写出。也欢迎大家补充各种不同语言的how to install。

### Ruby版

**在Windows环境下** 推荐安装[RubyInstaller](http://rubyinstaller.org/)，进入下载页面，选择一个ruby版本，比如[Ruby 1.9.3-p125](http://rubyforge.org/frs/download.php/75848/rubyinstaller-1.9.3-p125.exe)，下载、运行安装即可。

**在Linux/Mac环境下** 推荐安装[RVM](http://beginrescueend.com/)或者[rbenv](http://rbenv.org/)

    $ bash -s stable < <(curl -s https://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer)
    ubuntu下，将下两行中的.bash_profile改为.profile
    $ echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # > Load RVM function' >> ~/.bash_profile
    $ source ~/.bash_profile
    $ rvm requirements
    根据提示，安装其他必要的软件包
    $ rvm install 1.9.3
    $ rvm use 1.9.3

安装一个开源项目

    $ gem install sinatra

搞定收工。。。

如果之前没有安装过rubygems这个包，则会困难一些。首先要在[RubyGems](> )这个页面挑一个文件格式下载，并解压缩。然后执行以下命令：

    $ cd directory
    $ ruby setup.rb

搞定收工。。。

参考：[使用RVM在ubuntu下安装ruby&rails](http://www.cnblogs.com/klobohyz/archive/2011/11/21/2256518.html)

### PHP版

**在Windows环境下** 推荐安装WAMP（Windws+Apache+MySQL+PHP）套件，[XAMPP](http://www.apachefriends.org/en/xampp-windows.html)

**在Linux环境下** 以下将简单介绍在Ubuntu下安装LAMP的过程，其他的linux平台以及Mac平台，请自行搜索。

    $ sudo apt-get install mysql-client mysql-server
    根据提示，输入两次MySQL的root密码。
    $ sudo apt-get install apache2
    在浏览器中访问 http://localhost，应该可以看到It Works等文字。表明Apache2安装成功。
    $ sudo apt-get install php5 libapache2-mod-php5 libapache2-mod-auth-mysql php5-mysql
    $ sudo /etc/init.d/apache2 restart #重启Apache服务器，完成配置PHP的工作
    $ sudo vim /var/www/info.php
    将以下内容写入文件
    <?php
    phpinfo();
    ?>
    在浏览器中访问 http://localhost/info.php 应该能够看到PHP的版本及模块说明等内容。这样就表明，Linux+Apache+MySQL+PHP已经配置完成了。

**安装一个开源项目** 以在Ubuntu上安装一个wordpress为例

    $ wget http://cn.wordpress.org/wordpress-3.3.1-zh_CN.tar.gz #需要寻找最新的版本
    $ tar -zxvf wordpress-3.3.1-zh_CN.tar.gz
    $ mysql -uroot -p
    mysql> CREATE DATABASE IF NOT EXISTS wordpress default charset utf8 COLLATE utf8_general_ci;
    mysql> GRANT ALL PRIVILEGES 
                   ON wordpress.* 
                   TO 'wp_user'@'localhost'
                   IDENTIFIED BY 'wp_password' 
                   WITH GRANT OPTION;
    mysql> exit
    $ cp wp-config-sample.php wp-config.php
    $ vim wp-config.php
    （最主要是修改以下四个值的定义）
    define('DB_NAME', 'wordpress');
    define('DB_USER', 'wp_user');
    define('DB_PASSWORD', 'wp_password');
    define('DB_HOST', 'localhost');

在浏览器中访问 [http://localhost/wordpress/wp-admin/install.php](http://localhost/wordpress/wp-admin/install.php) 按提示完成各个步骤，就搞定了，整个时间不超过5分钟。

最后一句的提示，很有趣味：“WordPress 安装完成。您是否还沉浸在愉悦的安装过程中？很遗憾，一切皆已完成！”

[参考文档 1](http://codex.wordpress.org/zh-cn:%E5%AE%89%E8%A3%85WordPress)  [参考文档 2](http://supriyadisw.net/2006/12/wordpress-installation-on-ubuntu-with-lamp)

### Java版

**在Ubuntu下以源代码方式安装Tomcat**

    $ wget http://apache.etoak.com/tomcat/tomcat-7/v7.0.27/src/apache-tomcat-7.0.27-src.tar.gz #寻找最新版本
    $ tar -zxvf apache-tomcat-7.0.27-src.tar.gz
    $ cd apache-tomcat-7.0.27-src
    $ vim BUILDING.txt # 阅读编译指南，按照指示操作
    $ 下载 jdk-6u31-linux-x64.bin #tomcat7.0.x的源代码编译，要求jdk6的版本，jdk7在编译时，会报错
    $ cd
    $ ./jdk-6u31-linux-x64.bin
    $ export JAVA_HOME=~/jdk1.6.0_31/
    $ wget http://apache.etoak.com//ant/binaries/apache-ant-1.8.3-bin.tar.gz
    $ tar -zxvf apache-ant-1.8.3-bin.tar.gz
    $ export PATH=%PATH:~/apache-ant-1.8.3/bin:~/jdk1.6.0_31/bin
    $ export ANT_HOME=~/apache-ant-1.8.3/
    $ cd apache-tomcat-7.0.27-src
    $ ant
    $ cd output/build/bin/
    $ ./catalina.sh run

至此，在浏览器中，访问[http://localhost:8080/](http://localhost:8080/) 可以看到Tomcat的欢迎页。

### Python版

**在Ubuntu上安装Python Webpy**

    $ sudo easy_install web.py
    $ python
      Python 2.7.5 (default, Mar  9 2014, 22:15:05)
      [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
      Type "help", "copyright", "credits" or "license" for more information.
   	  >>> import web

**在Ubuntu上安装Python Webpy -- 另一种方法**

    $ sudo pip install web.py
    $ python
      Python 2.7.5 (default, Mar  9 2014, 22:15:05)
      [GCC 4.2.1 Compatible Apple LLVM 5.0 (clang-500.0.68)] on darwin
      Type "help", "copyright", "credits" or "license" for more information.
   	  >>> import web

备注：安装easy_install或者pip的方法

    $ sudo apt-get install python easy_install
    $ sudo apt-get install python pip
    上述方法，二选一

到这一步，Webpy就算是安装完成了。太简单了，我们还得再用这个框架干点什么。

    $ cat hello.py
    #!/bin/env python
    #-*- coding:utf-8 -*-
    import web
    urls = (
        	'/', 'index'
    	    )
    
    class index:
    		def GET(self):
        		return "Hello, world!"
    
    if __name__ == "__main__":
    		app = web.application(urls, globals())
    		app.run()
    $ python hello.py
      http://0.0.0.0:8080/

这时，用浏览器访问 [http://localhost:8080/](http://localhost:8080/) 你将看到 "Hello, world!"

### JavaScript(nodejs)版

现在的JavaScript发展的确飞快，已经不仅在浏览器里可以使用了，这里先简单介绍一下服务器端的node.js的安装与使用。

**在Ubuntu下安装node.js、npm与express.js**

    首先确认GCC编译环境的正确安装，否则请：“apt-get install build-essential”
    $ wget http://nodejs.org/dist/v0.6.15/node-v0.6.15.tar.gz
    $ tar -zxvf node-v0.6.15.tar.gz
    $ cd node-v0.6.15
    $ sudo apt-get install libssl-dev
    $ ./configure
    $ make
    $ sudo make install
    $ node -v
    v0.6.15
    $ curl http://npmjs.org/install.sh | sudo sh
    $ npm -v
    1.1.18
    $ npm install express
    $ vim test.js
    #File Begin
    var app = require('express').createServer();
    
    app.get('/', function(req, res){
      res.send('Hello World!');
    });
    
    app.listen(3000);
    #File End
    $ node test.js

打开浏览器，访问[http://localhost:3000/](http://localhost:3000/) 将看到 Hello World!

### C/C++版

因为在王越的系列文章《Mac OS X背后的故事》里，其中第八章《[三好学生Chris Lattner的LLVM编译工具链](https://www.cnblogs.com/ender-cd/articles/4048486.html)》有对LLVM的介绍，这使我决定尝试把LLVM，作为c语言的hello world项目。

说实话，在开源项目中，C语言的各种开源项目的编译安装，都是非常类似的。绝大多数命令都是以下三行：

    $ ./configure
    $ make
    $ make install

当然，在windows下，会麻烦得多。LLVM的安装也非常简单，命令如下：

    $ cd where-you-want-llvm-to-live
    $ svn co http://llvm.org/svn/llvm-project/llvm/trunk llvm
    $ cd llvm/tools
    $ svn co http://llvm.org/svn/llvm-project/cfe/trunk clang
    $ cd ../projects
    $ svn co http://llvm.org/svn/llvm-project/compiler-rt/trunk compiler-rt
    $ svn co http://llvm.org/svn/llvm-project/test-suite/trunk test-suite
    $ cd ..
    $ mkdir build
    $ cd build
    $ ../configure
    $ make
    $ make check-all
    $ make update
    $ make install

然后，我们可以尝试用LLVM的编译工具链，来编译c语言的代码。
创建一个文件hello.c

    #include <stdio.h>
    
    int main() {
      printf("hello world\n");
      return 0;
    }

编译hello.c，得到hello

    $ clang hello.c -o hello

编译c代码，得到LLVM的bitcode文件。

    $ clang -O3 -emit-llvm hello.c -c -o hello.bc

第一行以普通方式，执行编译好的可执行文件，第二行调用LLVM JIT，命令为lli，来执行LLVM的bitcode。

    $ ./hello
    $ lli hello.bc

更多内容可以参考：

* [Getting Started with the LLVM System](http://llvm.org/docs/GettingStarted.html)
* [参考文档 漫谈C语言及如何学习C语言](http://sunxiunan.com/?p=1661)

## 如何克服可能遇到的困难

**1. 仔细看文档**

LLVM的文档很有意思，在他开篇头三条是：1. Read the documentation. 2. Read the documentation. 3. Remember that you were warned twice about reading the documentation.

是的，认真地，非常认真地阅读相关文档，是最重要的方法。其他的一切方法，都是排在这个后面的。

当然，文档的正确性和完整性，也是可以怀疑的。有很多开源项目，往往存在文档bug、文档版本与代码版本不同步等问题。比如LLVM的安装文档，也并非完全正确，我到现在都还不明白，在1.2.3.条那么正经的提示之后，他的第8条，只有configure、make、make check-all、make update，居然没有make install！

但是，先看文档，尤其是项目本身的文档，而非二手、三手文档，是必须的第一步。

**2. 注意依赖，注意版本号**

优秀的安装手册，会提示你各种版本依赖问题。在开始正式安装之前，核对各种相关系统、工具、类库的版本，是非常重要的。之前我在安装apache tomcat的时候，就发现用java sdk的最新版JDK7，是不能正确编译的。必须将JDK，退回到JDK6.x，才能正确。

说实话，在开源软件安装的时候，估计有60%的问题，都是出在版本错误上。而剩下的40%，多半是看文档不认真的原因。

**3. 仔细看出错提示信息，并且在网上搜索答案**

在编译LLVM的时候，我遇到了一个古怪的bug：“collect2: ld terminated with signal 9 [Killed]”，当时完全不理解是怎么回事，只能在Google上找答案，幸好，类似的悲剧也在别人身上发生过。我找到了一个简明扼要的回答：“You probably ran out of memory.”。于是，我重新调整了Ubuntu虚拟机的内存大小，就编译通过了。

事实上，将出错信息的关键一行原文，加上开源项目的名称作为关键词，在google上搜索。通常能够找到相关的答案。

**4. 不要太早钻研细节**

因为是完全从源代码开始安装，所以其实可以有比二进制方式安装多得多的选择。比如configure能够配置的各种参数，一开始最好全部选择缺省，这是因为过早陷入安装的细节，会分散我们学习的注意力。

**5. 在网上找一找攻略**

有很多前人，愿意将自己的安装步骤仔仔细细地记录下来，从而节约我们大量的时间。找到优质的攻略，是事半功倍之道。但是，要特别注意攻略提及的软件版本及相关环境。在网上搜索攻略时，也需要考虑类似情况，比如：不要只是简单的搜索“ubuntu apache source install”，而是搜索包括软件版本的“ubuntu 10.04 64 apache source install”。这样能够避免照着不同版本的攻略，一个劲的死拼，从而浪费了大量的时间。另外，再一次提醒，**不要在百度搜索**。在国内的技术圈，有无数的“开发者”，喜欢反复的转载别人的blog和文章。不但不注明原文来源，甚至连格式、排版都丢失了，内容也难免出现错漏。简直就是一堆垃圾。而在百度搜索，这种垃圾又特别多，躲都躲不开。

所以，最好是在Google搜索,如果没办法访问外网，bing也是一个不错的选择！

**6. 如果很难搞定，不要一条道走到黑，换个方向**

RP问题，是存在的。喘口气，歇一歇，换个方向。试试别的开源项目吧。

[上一章](Select-an-open-source-project.md) | [下一章](Understanding-the-source-code.md)
