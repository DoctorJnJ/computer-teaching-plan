# 1.Python的基本语法及用途？
## 1.1 基本语法
变量、数据结构、运算符、条件语句、循环语句、列表、元组、字典、集合、面向对象
## 1.2 用途
### 1.2.1 解决基础数学问题
加减乘除、圆周率计算、面积计算等
### 1.2.2 输出简单图像
爱心等
### 1.2.3 简单的小程序
# 2.Conda是什么？为什么使用虚拟环境？conda如何应用？其他虚拟环境？
## 2.1 conda
Conda 是一个开源的包管理系统和环境管理系统，可在 Windows、macOS 和 Linux 上运行。Conda 可快速安装、运行和更新包及其依赖项，因此可以轻松地在计算机上创建、保存、加载和切换环境。它本是为 Python 程序而创造的，因为Python的版本比较多，并且它的库也非常广泛，同时库和库之间存在很多依赖关系，所以在库的安装和版本的管理上很麻烦，因此设计Conda作为一个管理版本和Python环境的工具，但它业可以打包和管理任何语言的软件。
## 2.2 虚拟环境
所谓的python虚拟环境，我们可以类比虚拟机的概念，每一个python虚拟环境都包含基本的python库，是能够独立运行的执行空间。在虚拟环境里可以下载第三方包、创建项目、写代码等等。
## 2.3 Conda应用
### 2.3.1 基本命令
确认版本：conda -V
查看命令参数：conda
查看子命令帮助信息:conda [子命令] -h
查看既存环境：conda env list
创建虚拟环境：conda create -n [环境名称] [安装库包列表]
查看环境列表：conda env list
启动新环境：conda activate [环境名称]
新建环境中安装所需的包：conda install [安装库包名称]
退出新环境:exit
删除环境：conda remove -n [环境名称] --all
创建个低版本的环境-Python3.8(科学计算包numpy 数学包scipy 符号包sympy 可视化包matplotlib seaborn)：conda create -n [环境名] python=3.8 numpy scipy matplotlib seaborn 
克隆一个base环境：conda create -n coder-base --clone [环境名称]
参考：[一文全面掌握conda_小码匠与老码农的博客-CSDN博客](https://blog.csdn.net/coder_oldgeek/article/details/122239755)
## 2.4 其他虚拟环境
### 2.4.1 virtualenv、conda
两者区别
（1）包管理软件：virtualenv使用pip作为包管理器，而anaconda使用conda作为包管理器
（2）环境隔离:virtualenv只能隔离python包，而anaconda可以隔离整个python环境及其依赖项
（3）系统依赖：anaconda可以安装一些系统依赖库，例如科学计算库
### 2.4.2 venv、poetry
# 3.github使用方法？SSH是什么？SSH key如何生成？Github如何免密clone？Github中https和ssh区别？Github中创造repo，代码push？
## 3.1 github使用方法
[(81条消息) Github如何使用详细介绍（保姆级教学）_如何使用github_久绊A的博客-CSDN博客](https://blog.csdn.net/m0_67906358/article/details/128833736)
## 3.2 SSH
SSH（Secure Shell，安全外壳）是一种网络安全协议，通过加密和认证机制实现安全的访问和文件传输等业务。传统远程登录或文件传输方式，例如Telnet、FTP，使用明文传输数据，存在很多的安全隐患。
## 3.3 SSH key生成
[(80条消息) github使用ssh方式_github ssh_幽忧偶心的博客-CSDN博客](https://blog.csdn.net/weixin_48349367/article/details/120056192)
## 3.4 https和ssh区别
### 3.4.1 简介
### 3.4.2 优缺点
ssh:一般使用22端口、通过先在本地生成SSH密钥对再把公匙上传到服务器、速度相对慢点
https:一般使用443端口、通过用户名/密码授权，可用性比较高、速度相较快点、一般企业防火墙会打开80和443这两个http/https协议的端口，因此在架设了企业防火墙的时候使用http就可以很好的绕开安全限制使用git了，很方便；而对于ssh来说，企业防火墙很可能没打开22端口
### 3.4.3 使用区别
clone 项目：使用ssh方式时，需要配置ssh key，即要将生成的SSH密钥对的公钥上传至服务器；使用http方式时，没有要求，可以直接克隆下来。
push 项目：使用ssh方式时，不需要验证用户名和密码，之前配置过ssh key，(如果你没设置密码)直接push即可、使用http方式时，需要验证用户名和密码。
### 3.4.4 总结
HTTPS利于匿名访问，适合开源项目，可以方便被别人克隆和读取(但没有push权限)；
SSH不利于匿名访问，比较适合内部项目，只要配置了SSH公钥极可自由实现clone和push操作。
## 3.5创造repo，代码push
### 3.5.1 下载git
[Git - Downloading Package (git-scm.com)](https://git-scm.com/download/win)
下载网速不好就利用using winget tool进行下载
### 3.5.2 登录github 详情见github使用方法
### 3.5.3创建new repository
![[Pasted image 20230414113439.png]]
Repository name: 仓库名称

Description(可选): 仓库描述介绍

Public, Private : 仓库权限（公开共享，私有或指定合作者）

Initialize this repository with a README: 添加一个README.md

gitignore: 不需要进行版本管理的仓库类型，对应生成文件.gitignore

license: 证书类型，对应生成文件LICENSE

这里配置主要是名称，描述，私有还是公开等
最后点击create repository完成项目创建
### 3.5.4 右键打开要上传文件
Git Bash here
### 3.5.5 在创建项目上找到项目链接code
git bush默认关闭复制粘贴
### 3.5.6 输入git clone [你的项目链接]
### 3.5.7 进入该文件中
ls 
cd [文件名]/
### 3.5.8 git add 你要上传的文件名称
### 3.5.9 git commit -m"提交信息"
### 3.5.10 git push(把本地仓库push到GitHub上面)
### 3.5.11 在github中查看完成上传，后续传项目时，应先git pull更新仓库再进去上传
如果想要删除可打开对应文件右上角进行删除