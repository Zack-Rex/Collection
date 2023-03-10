> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [hexo.io](https://hexo.io/zh-cn/docs/index.html)

> 欢迎使用 Hexo，本文档将帮助您快速上手。

欢迎使用 Hexo，本文档将帮助您快速上手。如果您在使用过程中遇到问题，请查看 [问题解答](https://hexo.io/zh-cn/docs/troubleshooting) 中的解答，或者在 [GitHub](https://github.com/hexojs/hexo/issues)、[Google Group](https://groups.google.com/group/hexo) 上提问。

[](#什么是-Hexo？ "什么是 Hexo？")什么是 Hexo？[](#什么是-Hexo？)
-------------------------------------------------

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 [Markdown](http://daringfireball.net/projects/markdown/)（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

[](#安装 "安装")安装[](#安装)
---------------------

安装 Hexo 只需几分钟时间，若您在安装过程中遇到问题或无法找到解决方式，请 [提交问题](https://github.com/hexojs/hexo/issues)，我们会尽力解决您的问题。

### [](#安装前提 "安装前提")安装前提[](#安装前提)

安装 Hexo 相当简单，只需要先安装下列应用程序即可：

*   [Node.js](http://nodejs.org/) (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
*   [Git](http://git-scm.com/)

如果您的电脑中已经安装上述必备程序，那么恭喜您！你可以直接前往 [安装 Hexo](#%E5%AE%89%E8%A3%85-Hexo) 步骤。

如果您的电脑中尚未安装所需要的程序，请根据以下安装指示完成安装。

### [](#安装-Git "安装 Git")安装 Git[](#安装-Git)

*   Windows：下载并安装 [git](https://git-scm.com/download/win).
*   Mac：使用 [Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) 或者下载 [安装程序](http://sourceforge.net/projects/git-osx-installer/)。
*   Linux (Ubuntu, Debian)：`sudo apt-get install git-core`
*   Linux (Fedora, Red Hat, CentOS)：`sudo yum install git-core`

> **Mac 用户**
> 
> 如果在编译时可能会遇到问题，请先到 App Store 安装 Xcode，Xcode 完成后，启动并进入 **Preferences -> Download -> Command Line Tools -> Install** 安装命令行工具。

> **Windows 用户**
> 
> 对于中国大陆地区用户，可以前往 [淘宝 Git for Windows 镜像](https://npm.taobao.org/mirrors/git-for-windows/) 下载 git 安装包。

### [](#安装-Node-js "安装 Node.js")安装 Node.js[](#安装-Node-js)

Node.js 为大多数平台提供了官方的 [安装程序](https://nodejs.org/zh-cn/download/)。对于中国大陆地区用户，可以前往 [淘宝 Node.js 镜像](https://npm.taobao.org/mirrors/node) 下载。

其它的安装方法：

*   Windows：通过 [nvs](https://github.com/jasongin/nvs/)（推荐）或者 [nvm](https://github.com/nvm-sh/nvm) 安装。
*   Mac：使用 [Homebrew](https://brew.sh/) 或 [MacPorts](http://www.macports.org/) 安装。
*   Linux（DEB/RPM-based）：从 [NodeSource](https://github.com/nodesource/distributions) 安装。
*   其它：使用相应的软件包管理器进行安装，可以参考由 Node.js 提供的 [指导](https://nodejs.org/zh-cn/download/package-manager/)。

对于 Mac 和 Linux 同样建议使用 nvs 或者 nvm，以避免可能会出现的权限问题。

> **Windows 用户**
> 
> 使用 Node.js 官方安装程序时，请确保勾选 **Add to PATH** 选项（默认已勾选）

> **For Mac / Linux 用户**
> 
> 如果在尝试安装 Hexo 的过程中出现 `EACCES` 权限错误，请遵循 [由 npmjs 发布的指导](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally) 修复该问题。强烈建议 **不要** 使用 root、sudo 等方法覆盖权限

> **Linux**
> 
> 如果您使用 Snap 来安装 Node.js，在 [初始化](https://hexo.io/zh-cn/docs/commands#init) 博客时您可能需要手动在目标文件夹中执行 `npm install`。

### [](#安装-Hexo "安装 Hexo")安装 Hexo[](#安装-Hexo)

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

```
$ npm install -g hexo-cli
```

### [](#进阶安装和使用 "进阶安装和使用")进阶安装和使用[](#进阶安装和使用)

对于熟悉 npm 的进阶用户，可以仅局部安装 `hexo` 包。

```
$ npm install hexo
```

安装以后，可以使用以下两种方式执行 Hexo：

1.  `npx hexo <command>`
2.  将 Hexo 所在的目录下的 `node_modules` 添加到环境变量之中即可直接使用 `hexo <command>`：

```
echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.profile
```

### [](#Node-js-版本限制 "Node.js 版本限制")Node.js 版本限制[](#Node-js-版本限制)

我们强烈建议永远安装最新版本的 Hexo，以及 [推荐的 Node.js 版本](#%E5%AE%89%E8%A3%85%E5%89%8D%E6%8F%90)。

<table><thead><tr><th>Hexo 版本</th><th>最低版本 (Node.js 版本)</th><th>最高版本 (Node.js 版本)</th></tr></thead><tbody><tr><td>6.2+</td><td>12.13.0</td><td>latest</td></tr><tr><td>6.0+</td><td>12.13.0</td><td>18.5.0</td></tr><tr><td>5.0+</td><td>10.13.0</td><td>12.0.0</td></tr><tr><td>4.1 - 4.2</td><td>8.10</td><td>10.0.0</td></tr><tr><td>4.0</td><td>8.6</td><td>8.10.0</td></tr><tr><td>3.3 - 3.9</td><td>6.9</td><td>8.0.0</td></tr><tr><td>3.2 - 3.3</td><td>0.12</td><td>未知</td></tr><tr><td>3.0 - 3.1</td><td>0.10 或 iojs</td><td>未知</td></tr><tr><td>0.0.1 - 2.8</td><td>0.10</td><td>未知</td></tr></tbody></table>