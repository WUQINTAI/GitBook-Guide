# GitBook 介绍

GitBook 是一款书籍编排管理工具。 同时是一款开源软件，于 2014 年中开源在 Github 上，其仓库地址为 **[gitbook](https://github.com/GitbookIO/gitbook)** ，引用项目中的介绍，其定义为：

> 原文：GitBook is a command line tool (and Node.js library) for building beautiful books using GitHub/Git and Markdown (or AsciiDoc).
>
> 译文：GitBook 是一个命令行工具（和Node.js库），可用于配合 GitHub/Git 和 Markdown（或AsciiDoc）构建漂亮的书。



## GitBook 的商业化

目前，GitBook 已实现了项目的商业化，托管在 GitHub 仓库上的  **[gitbook](https://github.com/GitbookIO/gitbook)**  项目也已停更许久，但从用户角度上看，我们仍可以使用这款命令行工具来编撰书籍，只不过无法再使用到新功能而已。

GitBook 目前已提供 `在线网页编辑` 和 `本地图形化软件编辑` 服务，你可以访问 **[GitBook 官网](https://www.gitbook.com/)** ，然后创建一个私有账号，接着就可以使用它提供的在线编辑文档服务了。当然你也可以下载图形化编辑软件(提供 Windows、Mac和Linux 版)，在本地安装后再编辑，如果有需要还可以将编辑后的书籍提交到线上服务器进行存储和查看。

上面提到的这些服务都是集成的，你不需要额外安装 GitBook 命令行工具、Git/Github、Markdown 这些工具，但由于 GitBook 是国外团队开发的，因此其服务器也在外国，国内的用户如果想使用该平台提供的服务就必须得懂翻墙技能，越过山丘，到达大洋彼岸的服务器。



## GitBook 的优点

前面定义中说到，GitBook 命令行工具可用于配合 Git/GitHub 、Markdown 进行书籍的编辑，用过 Git 和 Markdown 的朋友，很快就能说出其特点来：

- *Markdown* ：是一种轻量级标记语言，编辑文件高效、容易上手。
- Git/GitHub：是版本控制系统，用于对文件实施版本控制，让你在编辑文件时有“后悔药可吃”。
- GitBook：书籍编排工具，负责多文件的管理、融合展现和电子书导出，是团队协作的重要基石。

就是这样的一套组合组件，让你或你的团队可以随心所欲的开展书籍的编辑工作。当然有些组件也不是必须安装的，例如：Git/Github 组件，没有该组件不会影响到你的书籍编辑，只不过是没有版本控制服务而已。

此外 gitbook 还支持已插件的形式去扩展更多的功能，只要你愿意，尽管去折腾，探索你喜欢的编辑世界。

gitbook 支持输出文件：静态站点（默认）、eBook、单页网页、JSON 等格式文件。


## 本地部署搭配建议

本文不展开讲 gitbook 在线服务的使用 和 图形化软件的使用，原因是这些软件都集成了必要的组件，直接根据提示使用即可。

本文将在本地部署 gitbook 服务，建议搭配以下软件使用：

- Typora ：一款好用的 Markdown 编辑器，主要用于文档的编辑。
- Git：版本控制软件，用于实现文件的版本控制，如果不需要该功能可不安装。