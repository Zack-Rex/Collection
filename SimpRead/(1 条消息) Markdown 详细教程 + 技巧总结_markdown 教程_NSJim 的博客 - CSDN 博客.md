> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/NSJim/article/details/89697630?app_version=5.14.3&code=app_1562916241&csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%2289697630%22%2C%22source%22%3A%22weixin_46341649%22%7D&uLinkId=usr1mkqgl919blen&utm_source=app)

### Markdown 详细教程 + 技巧总结

*   [前言](#_1)
*   [Markdown 工具](#Markdown_8)
*   *   [工具介绍](#_9)
    *   [Typora](#Typora_20)
    *   *   [介绍](#_21)
        *   [安装](#_28)
        *   [设置](#_33)
        *   [技巧](#_66)
    *   [VS Code (Visual Studio Code)](#VS_Code_Visual_Studio_Code_74)
    *   *   [安装](#_75)
        *   [设置中文](#_81)
        *   [安装扩展](#_94)
        *   [编辑 Markdown 文档](#Markdown_98)
        *   [配合 Markdown 使用的扩展](#Markdown_101)
    *   [Markdown Pad 2](#Markdown_Pad_2_131)
    *   *   [介绍](#_132)
        *   [安装](#_134)
        *   [设置中文](#_138)
        *   [Key](#Key_140)
        *   [个性化设置](#_152)
*   [Markdown 与 HTML 的联系](#MarkdownHTML_159)
*   [编辑技巧](#_168)
*   *   [快捷键](#_169)
    *   [列表](#_185)
    *   [标记失效](#_192)
    *   [页面内跳转](#_204)
*   [CSDN 博客技巧](#CSDN_227)
*   *   [CSDN 目录](#CSDN_228)
    *   [CSDN 快捷键](#CSDN_233)
    *   [自定义列表](#_236)
    *   [注脚](#_252)
    *   [注释](#_267)
    *   [LaTeX 公式](#LaTeX_280)
    *   [Mermaid 制图](#Mermaid_283)
    *   *   [甘特图](#_291)
        *   [UML 图](#UML_316)
        *   [FLowchart 流程图](#FLowchart_342)
    *   [导出与导入](#_368)
*   [字符实体](#_375)
*   *   [前言](#_376)
    *   [空格](#_378)
    *   [其他](#_385)
*   [转义字符](#_407)
*   [首行缩进](#_423)
*   [空行](#_429)
*   [字体](#_433)
*   [目录](#_505)
*   [导出分页](#_517)
*   [链接](#_525)
*   [列表](#_535)
*   *   [有序列表](#_536)
    *   [无序列表](#_549)
    *   [待办列表](#_562)
    *   [多级列表](#_573)
    *   [自定义列表](#_608)
*   [图片](#_624)
*   *   [Markdown 图片](#Markdown_625)
    *   [CSDN 图片](#CSDN_636)
    *   [HTML 图片](#HTML_659)
    *   [图片居中标题](#_694)
*   [表格](#_705)
*   [分割线](#_748)
*   [代码块](#_768)
*   *   [单行代码块](#_769)
    *   [多行代码块](#_778)
    *   [技巧](#_799)
*   [LaTeX 数学公式](#LaTeX_808)
*   *   [介绍](#_809)
    *   [注意事项](#_829)

前言
==

若想直接学习 [LaTeX](https://so.csdn.net/so/search?q=LaTeX&spm=1001.2101.3001.7020) 数学公式，请参见我的另一篇博客：[_LaTeX 数学公式 - 详细教程_](https://blog.csdn.net/NSJim/article/details/109045914) 。

本篇文章从基础开始介绍 Markdown 语言，并有自己的经验和总结。适合新手和有基础的用户。其他途径的基础学习可以参照 [_Markdown 中文文档_](https://markdown-zh.readthedocs.io/en/latest/) 。

本篇文章内容包含 Markdown 工具，Markdown 与 HTML 的联系，页面内跳转，编辑技巧，CSDN 博客技巧，字符实体，空格，[转义字符](https://so.csdn.net/so/search?q=%E8%BD%AC%E4%B9%89%E5%AD%97%E7%AC%A6&spm=1001.2101.3001.7020)，首行缩进，空行，字体，目录，导出分页，链接，列表，图片，表格，代码块，LaTeX 数学公式，等等。

Markdown 工具
===========

工具介绍
----

很多小伙伴想要学习 Markdown 但却不知道使用什么编辑器来编写，这里我来列举一些可以编辑 Markdown 文件（即`.md`文件）的软件：Typora（推荐，目前已收费），Vsual Studio Code（推荐），Markdown Pad 2，有道云笔记，印象笔记等等。

个人优先推荐 Typora（目前已收费），优点是跨平台，轻量；真缩减即所得，没有预览窗口，写出即可预览；可以自动根据标题显示大纲，即目录。而且集成了 LaTeX 数学公式的包（需要在设置中开启，后文会详细说明），不需要安装插件。

个人第二推荐 Vsual Studio Code，即 VS Code，VS Code 原生支持 Markdown 语言，可以安装其他插件使其功能更加强大，下文有 VS Code 中编辑 Markdown 的说明，并介绍一些配合 Markdown 使用的插件。

至于 Markdown Pad 2，优点是便捷，速度快，无广告，而且还可以进行个性化设置。但可能需要安装插件，并授权激活，下方有该软件的安装与配置说明。

如果不想安装软件，在 CSDN 等博客网站上也可以编辑 Markdown 文件，然后可以选择导出。

Typora
------

### 介绍

（目前已收费）

1.  跨平台，轻量；
2.  真缩减即所得，没有预览窗口，写出即可预览；
3.  可以自动根据标题显示大纲（即目录），也可以手动输入 Markdown 语法生成目录；
4.  集成了 LaTeX 数学公式的包（需要在设置中开启，后文会详细说明），不需要安装插件。

### 安装

Typora 官网：[链接](https://www.typora.io/)

下载对应系统的软件安装包正常安装即可。

### 设置

点击`文件-偏好设置`即可进行设置：  
`通用-启动选项`：可根据自己偏好选择，推荐`打开新文件`  
`通用-保存`：勾选`自动保存`  
`通用-更新`：取消自动更新  
`通用-高级设置`：取消勾选`发生匿名数据`  
`外观-字体大小`：根据自己的偏好设置，如无特殊要求推荐选择`自动`  
`外观-状态栏`：显示状态栏  
`外观-侧边栏`：大纲视图允许折叠和打开  
`外观-主题`：GitHub  
`编辑器-使用成对符号`：匹配括号和引号，匹配 Markdown 字符  
`编辑器-即时渲染`：显示 Markdown 源码  
`编辑器-复制`：复制 Markdown 源码  
`图像-插入图片`：复制到指定路径，对本地图片使用规则，对网络图片使用规则，优先使用相对路径，推荐填写`./image/${filename}`  
`Markdown-Markdown扩展语法`：全部勾选  
`Markdown-代码块`：全部勾选，代码缩进为 4  
`导出-通用-默认导出文件夹`：和原文件同目录  
`导出-PDF-主题`：自动使用当前主题  
`导出-PDF-分页`：可根据自己偏好选择，也可使用 **导出分页** 章节的方法  
`导出-PDF-页尾`：可根据自己偏好填写，推荐`${pageNo}`

以下为几个设置截图：  
![](https://img-blog.csdnimg.cn/20210616203846486.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L05TSmlt,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20210616203701854.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L05TSmlt,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20201011110515724.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L05TSmlt,size_16,color_FFFFFF,t_70#pic_center)  
![](https://img-blog.csdnimg.cn/20210622144135638.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L05TSmlt,size_16,color_FFFFFF,t_70)

![](https://img-blog.csdnimg.cn/20201011110910914.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L05TSmlt,size_16,color_FFFFFF,t_70#pic_center)

![](https://img-blog.csdnimg.cn/20201011110924460.png#pic_center)

### 技巧

1.  软件使用教程详见官网：[链接](https://support.typora.io/) 。
2.  在软件内调用的图片，可以右键进行缩放，即可更改图片的尺寸（会自动将 Markdown 语法改为 HTML 语法）。
3.  在软件内输入`$$`后按回车，可以输入居中的跨行公式。
4.  在`设置-外观`处可以更改`字体大小`，同时会影响导出 PDF 文档的字体大小。
5.  按照 **导出分页** 章节中的方法，可以自由在导出的 PDF 文档中控制分页。
6.  通过`设置-导出`进行设置，可以更改导出 PDF 文档的纸张大小，可以增加页眉和页码，还可以按一级标题进行分页。

VS Code (Visual Studio Code)
----------------------------

### 安装

Visual Studio 官网：[链接](https://visualstudio.microsoft.com/zh-hans/)  
VS Code 下载网址：[链接](https://code.visualstudio.com/download)

注意：Windows 环境下载时，分为 User 版和 System 版（推荐），User 版只能安装在 C 盘的用户文件夹下，System 版可以自定义安装位置，用户可以安装需求选择下载哪个版本。

### 设置中文

安装好 VS Code 后，软件默认为英文，以下步骤可以将其设置为中文。

1.  选择`View - Command Palette`，或使用快捷键`Ctrl+Shift+P`，搜索`configure language`，然后选择`Configure Display Language`，然后选择`zh-cn`，如下图。  
    ![](https://img-blog.csdnimg.cn/20200722023340125.png)  
    **注意：** 若选择`Configure Display Language`后，未出现上图所示选项，而是出现如下图的 json 文件编辑页面，则可能为旧版的 VS Code，将 json 文件中的`locale`后面的`en`改为`zh-cn`，然后按照步骤 3 中安装`Chinese （Simplified）Language Pack`扩展。  
    ![](https://img-blog.csdnimg.cn/20200723145814955.png)
    
2.  若没有`zh-cn`，可以选择`Install additional languages`，然后安装扩展包`Chinese (Simplified) Language Pack`，然后重复步骤 1。
    
3.  也可以先在`View - Extensions`中安装`Chinese （Simplified）Language Pack`中文简体语言包扩展，如下图第 1 个扩展，然后进行步骤 1。  
    ![](https://img-blog.csdnimg.cn/20200723150515232.png)
    

### 安装扩展

在`查看 - 扩展`中可以查看、设置、启用、禁用、卸载已安装扩展，即对已安装扩展进行管理，同时可以搜索并安装各种扩展，如下图。  
![](https://img-blog.csdnimg.cn/20200722024945957.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L05TSmlt,size_16,color_FFFFFF,t_70)

### 编辑 Markdown 文档

在 VS Code 中打开或新建`.md`格式的文件即可进行编辑（在 VS Code 中新建文件时可能需要先保存为`.md`格式文件），点击右上角的预览按钮可以进行实时预览。下图第一个按钮即为预览按钮。  
![](https://img-blog.csdnimg.cn/20200722023841181.png)

### 配合 Markdown 使用的扩展

推荐的扩展套装：

1.  基于`Markdown Preview Enhanced`扩展预览窗口（推荐）：`Markdown Preview Enhanced 和 Prince软件` + `markdownlint` + `Mermaid Markdown Syntax Highlighting` + `Maridown PDF（可选）` + `vscode-pdf（可选）`
    
    优点：支持各种 CSDN 博客特殊语法，如：mermaid 绘图，注脚，注释，等等。而且预览窗口不受 VS Code 软件深色主题的影响，更加形象的展示所编写文件的 pdf 文档样式。
    
2.  基于原生预览窗口：`markdownlint` + `Markdown+Math` + `Mermaid Markdown Syntax Highlighting` + `Markdown Preview Mermaid Support` + `Maridown PDF` + `vscode-pdf（可选）`
    
    优点：预览窗口反应快速，无需安装额外的预览扩展，主题可以跟随 VS Code 软件的深色主题。
    
    缺点：部分特殊语法无法得到支持。
    

以下为各个扩展的详情介绍：

1.  markdownlint：一个好用的 Markdown 格式检查扩展，它规定了许多规则并实时对文档进行检查，防止一些语法错误，同时维持文档风格的统一，使用此工具有助于形成一个良好的写作习惯和规范。
    
2.  Markdown Preview Enhanced：一个很好用的完善预览功能的插件，可以更加形象的展示所编写文件的 pdf 文档样式。优点是支持 LaTeX 数学公式和 Mermaid 图表等内容的显示。
    
    安装后，你会发现工作区的右上角多了一个预览按钮，这个按钮就是 Markdown Preview Enhanced 插件产生的，如下图。直接右键`.md`文件的页面也可以开启 Markdown Preview Enhanced。  
    ![](https://img-blog.csdnimg.cn/20200722025234460.png)  
    注意：右键 Markdown Preview Enhanced 预览页面也有一些选项，如下图。`Open in Browser`是在浏览器中打开预览，`HTML`是打印成 HTML 文件，`PDF`是打印成 PDF 文件（此选项需额外安装 Prince 软件，VS Code 扩展库中没有，安装方法见后文）。  
    ![](https://img-blog.csdnimg.cn/20200723235032123.png)  
    安装 Prince 软件：进入 [Prince 官网](https://www.princexml.com/)，点击下载，选择对应的版本进行下载并安装。然后添加环境变量，`右键我的电脑->属性->高级系统设置->环境变量->系统变量->Path->编辑`，新建一条`Prince安装路径\engine\bin`即可。然后重启 VS Code。
    
3.  Markdown All in One：集成了各种功能，同时也支持 LaTeX 数学公式（在扩展设置中`启用基本的数学支持`选项可以开启与关闭该功能），但貌似没有显示 Mermaid 图表和打印 PDF 的功能。个人建议，若启用 Markdown+Math 扩展，则不必启用此扩展。
    
4.  Markdown+Math：使 VS Code 原生的 Markdown 预览窗口支持显示 LaTeX 数学公式。可以与 Markdown All in One 扩展同时使用，同时使用时，LaTeX 公式显示风格以 Markdown+Math 为标准。
    
5.  Mermaid Markdown Syntax Highlighting：支持 Mermaid 图表代码高亮，但无法在原生预览窗口显示。
    
6.  Markdown Preview Mermaid Support：支持原生预览窗口显示 Mermaid 图表。
    
7.  Maridown PDF：可以简单的将编写的`.md`文件转换成其他格式的文件，右键`.md`文件的页面可以进行转换，如下图。生成的文件将会直接保存在`.md`文件的文件夹下。但不支持 LaTeX 数学公式和 Mermaid 图表等内容的显示。  
    ![](https://img-blog.csdnimg.cn/20200722025429106.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L05TSmlt,size_16,color_FFFFFF,t_70)
    
8.  vscode-pdf：若希望在 VS Code 中直接打开并浏览 pdf 格式文件，可以通过安装该插件来达到该目的。
    

Markdown Pad 2
--------------

### 介绍

Markdown 是一种可以使用普通文本编辑器编写的标记语言，通过简单的标记语法，它可以使普通文本内容具有一定的格式。而 Markdown Pad 2 便是编辑 Markdown 语言的一款编辑器，其功能强大，便捷，速度快，无广告，而且还可以进行个性化设置。下面介绍一下 Windows 系统下，该工具的安装与配置方法。

### 安装

1.  进入官网：[_官网链接_](http://markdownpad.com/)，然后点击`Download MarkdownPad`；或者直接点击该链接，[_下载链接_](http://markdownpad.com/download.html)，会立刻开始下载。
2.  运行上一步骤下载到的 exe 文件，开始安装，并完成安装。
3.  注意：Win10 若提示 HTML 渲染组件出错，错误的表现形式为，不能实时预览 Markdown 生成的 HTML 页面。则需要安装`awesomium_sdk`，下载地址：[_Download awesomium_v1.6.6_sdk_win.exe_](http://markdownpad.com/download/awesomium_v1.6.6_sdk_win.exe)。

### 设置中文

Tool —> Options —> Editor —> Language，选择中文。

### Key

在初次打开软件时单击 Enter Key 按钮，或点击帮助—> 升级到 MarkdownPad 专业版。输入如下`Email`和`Key`。

**Email**

```
Soar360@live.com
```

**Key**

```
GBPduHjWfJU1mZqcPM3BikjYKF6xKhlKIys3i1MU2eJHqWGImDHzWdD6xhMNLGVpbP2M5SN6bnxn2kSE8qHqNY5QaaRxmO3YSMHxlv2EYpjdwLcPwfeTG7kUdnhKE0vVy4RidP6Y2wZ0q74f47fzsZo45JE2hfQBFi2O9Jldjp1mW8HUpTtLA2a5/sQytXJUQl/QKO0jUQY4pa5CCx20sV1ClOTZtAGngSOJtIOFXK599sBr5aIEFyH0K7H4BoNMiiDMnxt1rD8Vb/ikJdhGMMQr0R4B+L3nWU97eaVPTRKfWGDE8/eAgKzpGwrQQoDh+nzX1xoVQ8NAuH+s4UcSeQ==
```

### 个性化设置

菜单栏 —> 工具 —> 选项

1.  Markdown —> GitHub 风格 Markdown （离线）
2.  样式表 —> Markdownpad-github.css
3.  文件 —> 在导出的 PDF 文件中包含 CSS 背景

Markdown 与 HTML 的联系
===================

1.  Markdown 支持 HTML 的大部分标签，但反之 HTML 不支持 Markdown 语法；即 Markdown 兼容 HTML。例如换行标签`<br>`，键盘文本`<kbd>`，预格式文本`<pre>`，上标`<sup>`，下标`<sub>`，等等。更多标签和用法请参照 [_HTML 标签_](http://www.w3school.com.cn/tags/html_ref_byfunc.asp) 。
    
    例子：  
    键盘文本 - 复制的快捷键：`<kbd>Ctrl/Command</kbd> + <kbd>C</kbd>`
    
    显示：  
    Ctrl/Command + C
    
2.  Markdown 中支持 HTML 的大部分字符实体，如大于号：> ，显示为 >。更多 HTML 字符实体请参照 [_HTML 字符实体_](http://www.w3school.com.cn/html/html_entities.asp) 。
    

编辑技巧
====

快捷键
---

在编辑页面可以适当的使用快捷键提升效率。以下为 CSDN 的快捷键，其中有些是可以通用于各个编辑器的。

CSDN 快捷键：

1.  撤销：`Ctrl/Command + Z`
2.  重做：`Ctrl/Command + Y`
3.  加粗：`Ctrl/Command + B`
4.  斜体：`Ctrl/Command + I`
5.  标题：`Ctrl/Command + Shift + H`
6.  无序列表：`Ctrl/Command + Shift + U`
7.  有序列表：`Ctrl/Command + Shift + O`
8.  待办列表：`Ctrl/Command + Shift + C`
9.  插入代码：`Ctrl/Command + Shift + K`
10.  插入链接：`Ctrl/Command + Shift + L`
11.  插入图片：`Ctrl/Command + Shift + G`

列表
--

当使用顺序列表时，按回车会自动生成序号，想中断排序，再按一次回车即可。

在顺序列表的编号后面按回车，不会打乱编号的顺序。

当使用列表后，缩进中断时，可以使用 Tab 进行缩进。

标记失效
----

1.  在使用 Markdown 标记语言时，一些标记后需要加空格才会生效，如标题标记：`#` 。
    
2.  一些标记的前面需要有回车才会生效，如分隔符：`---` 。
    
3.  一些字体标记，当`结束标记`前的字符为`标点符号`时可能会失效。  
    例如：`**标点符号。**是句号。`  
    显示：** 标点符号。** 是句号。
    
    解决方案：在`结束标记**`后加空格即可，其他字体标记同理。
    
    例如：`**标点符号。** 是句号。`  
    显示：**标点符号。** 是句号。
    

页面内跳转
-----

由于 Markdown 目前没有实现页面内跳转的方法，故可以使用 HTML 的方法进行页面内跳转，因为 Markdown 支持 HTML。值得一提的是，跳转到锚点时，可以使用 Markdown 的链接语法进行跳转。

**注意：** 示例中锚点的`<h1>`标签可以换成任何其他标签，如`<text>`标签等。

纯 HTML 示例：

```
<!-- 跳转到锚点 -->
<a href="#1">锚点目标</a>
<!-- 创建锚点 -->
<h1 id="1">锚点</h1>
```

HTML 创建锚点 + Markdown 跳转示例：  
跳转到锚点：`[锚点目标](锚点id '标题')`  
创建锚点（同上）：`<h1>锚点</h1>`

展示：  
HTML 语法跳转：[锚点目标](#1)  
Markdown 语法跳转：[锚点目标](#1)

锚点

CSDN 博客技巧
=========

CSDN 目录
-------

输入`#`，并按下`Space`后，将生成 1 级标题。  
输入`##`，并按下`space`后，将生成 2 级标题。  
以此类推，我们支持 6 级标题。有助于使用`@[TOC](自定义目录标题)`或`@[toc](自定义目录标题)`语法后生成一个有缩进的目录，可实现页内跳转。

CSDN 快捷键
--------

同编辑技巧章节的快捷键。此处省略。

自定义列表
-----

CSDN 编辑器支持，某些本地编辑器不支持。

例子（最前面要有空行）：

```
Authors
: John
: Luke
```

显示：

Authors

John

Luke

注脚
--

CSDN 编辑器支持，某些本地编辑器不支持。

注脚会按照文章的顺序自动排序。

例子：

```
一个具有注脚的文本。[^1]
[^1]: 注脚的解释
```

显示：  
一个具有注脚的文本。[1](#fn1)

注释
--

CSDN 编辑器支持，某些本地编辑器不支持。

例子（注释词前后要有空格）：

```
Markdown兼容 HTML 语言。
*[HTML]: 超文本标记语言
```

显示：  
Markdown 兼容 HTML 语言。

LaTeX 公式
--------

CSDN 编辑器中支持 LaTeX 数学公式，详情请见后文的 **LaTeX 公式**章节。**Typroa 软件**支持，设置方法详见上文的 **Markdown 工具 - Typroa - 设置** 章节。

Mermaid 制图
----------

CSDN 编辑器中支持 mermaid 绘图，如甘特图，UML 图等。详情及具体用法请见[参考文档](https://mermaid-js.github.io/mermaid/#/)。  
参考文档：[链接](https://mermaid-js.github.io/mermaid/#/) 。

需要注意的是：有些本地编辑器不支持 mermaid 绘图，但如果使用 VS Code，则可以通过安装`Markdown Preview Enhanced`或`Markdown Preview Mermaid Support`扩展的方式支持，详情请见上文的 **Markdown 工具 - VS Code - 配合 Markdown 使用的扩展** 章节。

下方是一些图的简单绘制方法。

### 甘特图

```mermaid  
gantt  
dateFormat YYYY-MM-DD  
title Adding GANTT diagram functionality to mermaid  
section 现有任务  
已完成 :done, des1, 2014-01-06,2014-01-08  
进行中 :active, des2, 2014-01-09, 3d  
计划一 : des3, after des2, 5d  
计划二 : des4, after des3, 5d  
```

显示：

Mon 06 Mon 13 Mon 20 已完成 进行中 计划一 计划二 现有任务 Adding GANTT diagram functionality to mermaid

### UML 图

```mermaid  
sequenceDiagram  
张三 ->> 李四: 你好！李四, 最近怎么样?  
李四–>> 王五: 你最近怎么样，王五？  
李四–x 张三: 我很好，谢谢!  
李四 - x 王五: 我很好，谢谢!  
Note right of 王五: 李四想了很长时间, 文字太长了  
不适合放在一行.

李四–>> 张三: 打量着王五…  
张三 ->> 王五: 很好… 王五, 你怎么样?  
```

显示：

张三 李四 王五 你好！李四, 最近怎么样? 你最近怎么样，王五？ 我很好，谢谢! 我很好，谢谢! 李四想了很长时间, 文字太长了 不适合放在一行. 打量着王五... 很好... 王五, 你怎么样? 张三 李四 王五

### FLowchart 流程图

```mermaid  
flowchat  
st=>start: 开始  
e=>end: 结束  
op=>operation: 我的操作  
cond=>condition: 确认？

st->op->cond  
cond(yes)->e  
cond(no)->op  
```

显示：

Created with Raphaël 2.3.0 开始 我的操作 确认？ 结束 yes no

导出与导入
-----

**导出**  
用户可以在 CSDN 文章中任意编辑。完成了一篇文章的写作后, 可以在上方工具栏找到 `导出`按钮 ，生成一个`.md`文件或者`.html文件`进行本地保存。

**导入**  
如果用户想加载一篇自己写过的`.md`文件或者`.html`文件，在上方工具栏可以选择`导入`按钮进行对应扩展名的文件导入，并继续创作。

字符实体
====

前言
--

与 HTML 字符实体相同，详情可参照 [_HTML 字符实体_](http://www.w3school.com.cn/html/html_entities.asp) 。

空格
--

1.  `&nbsp;`  
    不换行空格，全称是 No-Break Space，它是最常见和我们使用最多的空格，大多数的人可能只接触了 ，它是按下 space 键产生的空格。在 HTML 中，如果你用空格键产生此空格，空格是不会累加的（只算 1 个）。要使用 html 实体表示才可累加，该空格占据宽度受字体影响明显而强烈。
2.  `&ensp;`  
    半角空格，全称是 En Space，en 是字体排印学的计量单位，为 em 宽度的一半。根据定义，它等同于字体度的一半（如 16px 字体中就是 8px）。名义上是小写字母 n 的宽度。此空格传承空格家族一贯的特性：透明的，此空格有个相当稳健的特性，就是其占据的宽度正好是 1/2 个中文宽度，而且基本上不受字体影响。
3.  `&emsp;`  
    全角空格，全称是 Em Space，em 是字体排印学的计量单位，相当于当前指定的点数。例如，1 em 在 16px 的字体中就是 16px。此空格也传承空格家族一贯的特性：透明的，此空格也有个相当稳健的特性，就是其占据的宽度正好是 1 个中文宽度，而且基本上不受字体影响。

其他
--

<table><thead><tr><th>显示结果</th><th>描述</th><th>实体名称</th><th>实体编号</th></tr></thead><tbody><tr><td>&nbsp;</td><td>空格</td><td>&amp;nbsp;</td><td>&amp;#160;</td></tr><tr><td>&lt;</td><td>小于号</td><td>&amp;lt;</td><td>&amp;#60;</td></tr></tbody></table>

> | 大于号 |> |>  
> ≦ | 小于等于 |≤  
> ≧ | 大于等于 |≥  
> & | 和号 |& |&  
> "| 引号 |" |"  
> ’ | 撇号 |'(IE 不支持) |'  
> ￠ | 分 |¢ |¢  
> £ | 镑 |£ |£  
> ￥ | 日圆 |¥ |¥  
> € | 欧元 |&euro |€  
> § | 小节 |§ |§  
> © | 版权 |© |©  
> ® | 注册商标 |® |®  
> ™ | 商标 |™ |™  
> × | 乘号 |× |×  
> ÷ | 除号 |÷ |÷

转义字符
====

1.  写法：`\+字符`
    
2.  用途：当某些特殊字符与 Markdown 语法冲突时，使用转义字符可以使字符强制显示，字符实体也可用转义字符显示。
    
3.  示例：  
    `\>`  
    显示：>
    
    `\=\=`  
    显示：==
    
    `\&gt;`  
    显示：>
    
    等等
    
4.  注意：使用字符实体也可以达到一样的效果，但不常用的或记不住的字符实体建议使用转义字符。
    

首行缩进
====

缩进 2 个汉字大小：

1.  使用 2 个`&emsp;`（推荐）
2.  使用 4 个`&ensp;`
3.  使用 8 个`&nbsp;`

空行
==

1.  连续输入 2 个回车，即可打出一个空行。
2.  输入 HTML 表签`<br>`，即可打出一个换行。

字体
==

1.  普通文本：
    
    ```
    *强调文本* _强调文本_
    **加粗文本** __加粗文本__
    ==标记文本==
    ~~删除文本~~
    > 引用文本
    ```
    
    显示：  
    _强调文本_ _强调文本_  
    **加粗文本** **加粗文本**  
    标记文本  
    ~删除文本~
    
    > 引用文本
    
    注意：强调文本即斜体文本。
    
2.  组合文本：  
    加粗加斜：使用`***`或`___`  
    例子：`***加粗加斜***`  
    显示：_**加粗加斜**_
    
3.  上下标  
    **CSDN 编辑器**  
    此方法可能不适用某些本地编辑器，本地编辑器可以使用 HTML 方法或 LaTeX 公式方法。
    
    上标：`^文本^`  
    下标：`~文本~`
    
    例子：  
    `H~2~O`  
    `2^10^`
    
    显示：  
    H2O  
    210
    
    **HTML 方法**  
    此方法比较同用，适用于各种 Markdown 编辑器，因为 Markdown 支持 HTML。显示效果与 CSDN 编辑器相同。  
    上标：`<sup>文本</sup>`  
    下标：`<sub>文本</sub>`
    
    例子：  
    `H<sub>2</sub>O`  
    `2<sup>10</sup>`
    
    显示：  
    H2O  
    210
    
    **LaTeX 公式方法**  
    详情请见下文的 **附录 LaTeX 公式细节 - 上下标** 章节。以下为简单的例子。
    
    例子：  
    `$x^z_{y+1}$`
    
    显示：  
    x y + 1 z x^z_{y+1} xy+1z​
    
4.  引用可嵌套  
    例子：
    
    ```
    >这是引用的内容
    >>这是引用的内容
    >>>>>>>>>>这是引用的内容
    ```
    
    显示：
    
    > 这是引用的内容
    > 
    > > 这是引用的内容
    > > 
    > > > > > > > > > > 这是引用的内容
    

目录
==

Markdown 基本语法并没有生成目录的功能，但很多平台或软件都支持生成目录，比如：CSDN 博客平台、Typroa 软件、等等。使用方法如下，输入下方命令即可在相应位置插入目录，该目录为 Markdown 文档内的标题组成的目录：

**CSDN 博客**  
`@[TOC](目录名称)` 或 `@[toc](目录名称)` 。

**Typroa**  
`[TOC]` 或 `[toc]` 。

**其他**  
同 Typroa。

导出分页
====

在 Markdown 导出为 PDF 时，若想要设置分页，在 Markdown 文件想分页的位置输入如下 HTML 代码即可，再次导出即可显示分页效果。该语句已在 Typroa 软件中实验成功。

```
<div style="page-break-after: always;"></div>
或
<div STYLE="page-break-after: always;"></div>
```

链接
==

格式：`[链接文本](链接地址 '链接标题')`  
说明：链接文本为显示的文字，链接地址为链接的网址，链接标题可以不写，是鼠标悬停在链接处显示的标题。

例子：  
`[Link](https://mp.csdn.net)`

显示：  
[Link](https://mp.csdn.net)

列表
==

有序列表
----

示例：

```
1. 项目1
2. 项目2
3. 项目3
```

显示：

1.  项目 1
2.  项目 2
3.  项目 3

无序列表
----

示例：

```
- 项目
- 项目
- 项目
```

显示：

*   项目
*   项目
*   项目

待办列表
----

示例：

```
- [ ] 计划任务
- [x] 完成任务
```

显示：

*   [ ]  计划任务
*   [x]  完成任务

多级列表
----

每写下一级有序列表或无须列表时，多缩进 1 个 Tab（推荐）或 4 个空格。

有序多级列表示例：

```
1. 标题1
	1. 标题1.1
		1. 标题1.1.1
		2. 标题1.1.2
	2. 标题1.2
	3. 标题1.3
2. 标题2
```

显示：

1.  标题 1
    1.  标题 1.1
        1.  标题 1.1.1
        2.  标题 1.1.2
    2.  标题 1.2
    3.  标题 1.3
2.  标题 2

无序多级列表示例：

```
- 项目
	- 项目
		- 项目
```

显示：

*   项目
    *   项目
        *   项目

自定义列表
-----

注意：CSDN 编辑器支持，某些本地编辑器不支持。

例子（最前面要有空行）：

```
Authors
: John
: Luke
```

显示：

Authors

John

Luke

图片
==

Markdown 图片
-----------

插入图片格式：  
![](https://img-blog.csdnimg.cn/20200722184858402.png#)  
**注意：** 图片替换文本是图片未显示时替换的文本，图片标题是鼠标悬停在图片上显示的文本，图片标题可不写，图片标题的引号用单引号和双引号都可以。图片地址可以是网络网址（`https://xxx`），也可以是本地相对路径（推荐，如`./images/pic1.jpg`）或绝对路径。

例子：  
`![Alt](https://img-blog.csdnimg.cn/20210531154235861.png 'title')`

显示：  
![](https://img-blog.csdnimg.cn/20210531154235861.png)

CSDN 图片
-------

CSDN 平台针对 Markdown 的图片语法做了特殊处理，支持调整图片的大小和对齐方式，使用方法如下：

1.  带尺寸的图片：  
    `![Alt](https://img-blog.csdnimg.cn/20210531154235861.png# =30x30)`
    
    显示：  
    ![](https://img-blog.csdnimg.cn/20210531154235861.png#)
    
2.  居中的图片：  
    `![Alt](https://img-blog.csdnimg.cn/20210531154235861.png#pic_center)`
    
    补充：图片居左为`#pic_left`，图片居右为`#pic_right` 。
    
    显示：  
    ![](https://img-blog.csdnimg.cn/20210531154235861.png#pic_center)
    
3.  居中并且带尺寸的图片：  
    `![Alt](https://img-blog.csdnimg.cn/20210531154235861.png#pic_center =30x30)`
    
    显示：  
    ![](https://img-blog.csdnimg.cn/20210531154235861.png#pic_center)
    
4.  为了让用户更加便捷，CSDN 博客增加了图片拖拽功能。
    

HTML 图片
-------

即使不在 CSDN 平台，Markdown 编辑器也可以实现调整图片大小和对齐方式的功能，因为 Markdown 支持 HTML，使用 HTML 语言即可，使用方法如下：

**居中图片**  
代码：

```
<div align=[对齐方式]> <!--对齐方式可以为center，left，right-->
<img src="图片地址" alt="替换文字" width="宽度" height="高度">
</div>
```

示例 1：居中的图片

```
<div align=center>
<img src="https://img-blog.csdnimg.cn/2021053115541388.png">
</div>
```

显示：

![](https://img-blog.csdnimg.cn/2021053115541388.png)

示例 2：居中且带尺寸的图片

```
<div align=center>
<img src="https://img-blog.csdnimg.cn/2021053115541388.png" width="50%">
</div>
```

显示：

![](https://img-blog.csdnimg.cn/2021053115541388.png)

图片居中标题
------

无论以何种方式插入图片，都有在图片下方输入图片标题的需求，使用 HTML 语法即可为图片添加居中标题，使用方法如下：

在图片下方添加如下 HTML 代码即可：

```
<center>图片标题</center>
```

显示：

图片标题

表格
==

1.  如果表格贴近行首，则可以使用简便方式制作表格  
    例子：
    
    ```
    列1 | 列2
    --- | ---
    值1 |值2
    值3 |值4
    ```
    
    显示：
    
    <table><thead><tr><th>列 1</th><th>列 2</th></tr></thead><tbody><tr><td>值 1</td><td>值 2</td></tr><tr><td>值 3</td><td>值 4</td></tr></tbody></table>
2.  若表格前有 Tab 缩进，则左侧的 | 需补全，否则会出现第一列不显示的状况。  
    例子：
    
    ```
    | 列1 | 列2
    | --- | ---
    | 值1 |值2
    | 值3 |值4
    ```
    
    显示：
    
    <table><thead><tr><th>列 1</th><th>列 2</th></tr></thead><tbody><tr><td>值 1</td><td>值 2</td></tr><tr><td>值 3</td><td>值 4</td></tr></tbody></table>
3.  完整的表格格式。  
    例子：
    
    ```
    | 列1 | 列2 | 列3 |
    | :--- | :---: | ---: |
    | 文本居左 | 文本居中 | 文本居右 |
    ```
    
    显示：
    
    <table><thead><tr><th align="left">列 1</th><th align="center">列 2</th><th align="right">列 3</th></tr></thead><tbody><tr><td align="left">文本居左</td><td align="center">文本居中</td><td align="right">文本居右</td></tr></tbody></table>
4.  注意：最左侧（第一个） `|` 右端最好有 1 或 2 个空格，否则可能会出现未知错误（如缺失字符，对齐失效等）。
    

分割线
===

三个或者三个以上的 - 或者 * 都可以，效果是一样的。  
注意分割线前要有空行。

例子：

```
（空行）
---
----
***
*****
```

显示：

代码块
===

单行代码块
-----

代码只有一行或在文本中插入时可以使用，也可以叫行中代码块，格式为：` 代码 ` 。

例子：  
`print('Hello World!)`

显示：  
`print('Hello World!)`

多行代码块
-----

多行代码块可以插入多行代码，且可以标记编程语言的类型，如 python，可以简写成 py，JavaScript 可以简写成 js。

格式：  
``` 编程语言类型  
代码片段  
代码片段  
```

例子：  
```py  
for i in(1,11,1):  
 print(‘Hello World!’,end=‘\n’)  
```

显示：

```
for i in(1,11,1):
	print('Hello World!',end='\n')
```

技巧
--

1.  代码块前面可以使用 Tab 缩进，显示的代码块前端也会有缩进。
    
    例子：
    
    ```
    print('前面有缩进。')
    ```
    
2.  在 CSDN 博客设置页面，可以选择一款自己喜欢的代码片高亮样式。
    

LaTeX 数学公式
==========

介绍
--

CSDN 支持 LaTeX 公式，但有些本地编辑器可能不支持 LaTeX 公式，Typroa 可以更改设置支持，VS Code 可以通过安装扩展的方式支持，详情请见上文的 **Markdown 工具** 章节。

LaTeX 数学公式的各种细节请参见我的另一篇博客：[_LaTeX 数学公式 - 详细教程_](https://blog.csdn.net/NSJim/article/details/109045914) 。

1.  官方文档：  
    传送门：[_官方文档_](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)  
    网址：`https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference`
2.  中文教程：  
    传送门：[_中文教程_](https://www.jianshu.com/p/25f0139637b7)  
    网址：`https://www.jianshu.com/p/25f0139637b7`
3.  技巧：使用[_在线 LaTeX 公式编辑器_](https://private.codecogs.com/latex/eqneditor.php)，来生成 LaTeX 公式代码，然后复制到 Markdown 编辑器中，并在两边加上`$`或`$$`即可。  
    在线 LaTeX 公式编辑器网址：`https://private.codecogs.com/latex/eqneditor.php`
4.  插入公式  
    左对齐公式（行中公式）：`$数学公式$`  
    居中公式（独立公式）：`$$数学公式$$`  
    注意：使用`$`行中公式时，`数学公式`与`$`连接处不要有空格，否则公式不会显示；使用`$$`居中公式时，`数学公式`与`$$`连接处可以有空格。即`$ 数学公式 $` 不显示公式。
5.  注释：`%`为单行注释。
6.  细节：细节请参见我的另一篇博客：[_LaTeX 数学公式 - 详细教程_](https://blog.csdn.net/NSJim/article/details/109045914) 。

注意事项
----

1.  使用`$`，即行中公式时，`数学公式`与`$`连接处不要有空格，否则公式不会显示。
2.  使用`$$`，即居中公式时，`数学公式`与`$$`连接处可以有空格。即`$ 数学公式 $` 不显示公式。
3.  使用`$$`时，上方要空一行。
4.  `=`不要单独打一行，否则可能会出错。
5.  `+ - * / = ( ) | , . '`等符号直接在`$`或`$$`之间输入即可识别。

1.  注脚的解释 [↩︎](#fnref1)