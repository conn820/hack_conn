Git & GitHub 互推
---

`说明`：

- 本文档主要针对 git & github & bash shell三料小白，作者也是三料小白，欢迎大牛拍砖
- 本文档主要介绍基本的
	- 与自己github账户互推，而非团队管理
	- bash shell控制，而非客户端
- 的git & github互推方法
- 本文档主要针对windows用户


`配置环境`：

- win7，64位
- Git bash [http://git-scm.com/](http://git-scm.com/)
- GitHub 网页端

`主要参考资料`：

- ProGit [http://git-scm.com/book/en/v2](http://git-scm.com/book/en/v2)
- Git help [https://help.github.com/](https://help.github.com/)

### 0.1 基本概念介绍

- Git：是一种文件（版本）管理机制，相当于一种约定
- Git Bash：在本地操作Git这种管理机制的一个工具（这个工具不同于我们平时的桌面文件系统，需要学一些基本的命令）
- GitHub：一个和我们本地仓库保持对接的远程仓库，用来
	- 和别人合作
	- 保护自己文件的安全性（而非隐私性）
	- 去一窥其他人的项目


### 0.2 基本环境搭建

- 注册GitHub账户
- 下载Git Bash工具，网站已经附上，安装在本地（假设安装在了D:\git）

### 0.3 基本技能养成

- GitHub建立仓库：github界面右侧大绿块
- Git Bash文件基本操作：bash shell本质上是一个用命令代替了咱们的鼠标，来进入/进出/新建/删除文件等等，本文只介绍几个基本的命令，用来感受一下用bash shell控制文件的感觉。
	- 好的，首先点开git bash图标：
	- 1）输入`pwd`，这个命令用来看当前自己的工作环境路径
	- 2）你可以用 `cd d:/git`来将自己的工作环境设为其他某个文件夹，
	- 3）新建一个文件 `mkdir test` （看下当前文件环境中是否出现了一个test的文件夹）
	- 2）进入这个文件开始工作 `cd test`
	- 3）退出这个文件 `cd `，就是cd后面空格回车就好

互推工作正式开始！


### 1. 确定目标

我们的主要目标，是希望在github上建立一个仓库后，我可以在本地进行管理。为了达成这个目标，我们需要完成以下几步：

- 步骤a：在GitHub上建立仓库，假设为`test`
- 步骤b：将这个仓库克隆（clone）到我们本地
- 步骤c：在本地做一些修改
- 步骤d：将本地做的这些修改同步推送到github上

为了达成这四步，我首先要让我的github账户和我的本地取得一个基本的互信，即建立一个ssh钥匙。

所以，整个过程可以分为五步：

- 步骤a：在GitHub上建立仓库，假设为`test`
- 步骤a*：建立ssh钥匙，让本地与github账户间取得互信
- 步骤b：将这个仓库克隆（clone）到我们本地
- 步骤c：在本地做一些修改
- 步骤d：将本地做的这些修改同步推送到github上


### 2. 步骤a及步骤a*：

步骤a不介绍了，重点说说步骤a*。本章主要参考依据为：[https://help.github.com/articles/generating-ssh-keys/](https://help.github.com/articles/generating-ssh-keys/)

首先，在本地生成一个ssh钥匙：

`$ssh-keygen -t rsa -C "your_email@example.com"$`
