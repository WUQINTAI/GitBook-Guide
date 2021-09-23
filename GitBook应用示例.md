# GitBook 应用示例

使用 Gitbook 来编辑书籍，主要分为：`创建一本书`  >> `编辑书籍` >> `预览书籍` >> `生成电子书` 四个流程。


## 创建一本书

首次编写书籍时，需要先初始化一本新书：

```
# 创建并切换到书籍目录
mkdir book && cd book

# 初始化书籍
gitbook init
```

初始化后，程序会自动在书籍 book 目录下创建两个必要的文件，其结构如下：

```shell
$ tree book/
book/
├── README.md
└── SUMMARY.md

0 directories, 2 files
```

README.md 是书籍的简单介绍，初始内容如下：

```
# Introduction

```

SUMMARY.md 是书籍的摘要（可以理解为大纲或目录结构），初始内容如下：

```
# Summary

* [Introduction](README.md)
```

关于如何使用这两个文件，请接着往下看。



## 编辑书籍

编写一本书，首先要做的就是规划这本书要讲的内容、要分哪些章节进行讲述。因此通常是先搭建一套内容体系，然后再着手书籍内详细内容的编辑。

在构建了清晰的知识体系后，后续的编写工作才能更好、更快、更有条理和更清晰的去编辑该书籍的详细内容，从而完成此书的编辑。

在 GitBook 中使用的就是此思维，建议用户在编辑书籍前先搭建内容体系，后着手书籍内容编辑。

> PS：该步骤也为团队协作编辑书籍打下了伏笔。

`GitBook` 通过 `SUMMARY.md` 文件来定义书籍的目录，因此可通过改写该文件来实现书籍的内容规划，设置参考如下：

```markdown
# Summary

* [Introduction](README.md)
* [Chapter-1](Chapter-1/README.md)
    * [Section 1.1](Chapter-1/Section 1.1.md)
    * [Section 1.2](Chapter-1/Section 1.2.md)
* [Chapter-2](Chapter-2/README.md)
    * [Section 2.1](Chapter-2/Section 2.1.md)
    * [Section 2.2](Chapter-2/Section 2.2.md)
```

`SUMMARY.md` 文件：`[]` 内填写标题文本，该内容将显示在书的摘要(大纲)上；`()` 内填写标题对应的文档的存放路径，后面将通过初始化指令，自动完成所有文件的初始化；`*`用于分割章节和子章节，其通过 4 个空格符进行目录的分级。

目录结构编写完毕后，再次执行 `gitbook init` 指令完成相关文件的自动初始化，初始化后 book 的目录结构如下：

> 注意：Gitbook 目前仅支持两级目录划分，更深层次的目录无法完成自动创建。 

```shell
book/
├── Chapter-1
│   ├── README.md
│   ├── Section 1.1.md
│   └── Section 1.2.md
├── Chapter-2
│   ├── README.md
│   ├── Section 2.1.md
│   └── Section 2.2.md
├── README.md
└── SUMMARY.md
```

文件初始化完毕后，即可在相应的文件上进行书籍内容的编辑。



## 预览书籍

编写书籍的过程中，为了便于观察书籍的整体情况，可使用预览功能：

```
# 启动预览服务
gitbook serve

# 打开本地浏览器，访问以下地址查看书籍详情
http://127.0.0.1:4000
```



## 生成电子书

在本地编撰的书籍，需要依赖于当前的路径，因此如果将书籍移植到其它平台或目录，极有可能会导致文件的访问异常，影响书籍的阅读性。

为了打破这种文件路径依赖的壁垒，你可以在书籍编写完成后，通过编译操作，将书籍输出为 HTML 的电子书：

```shell
# 编译书籍jian
gitbook build
```

编译完成后，在书籍目录下会生成一个名为 `_book` 的文件夹，该文件夹内存放的文件就是编译后的书籍文件，你可将文件移植到任何平台、任何目录进行访问，而无需考虑路径的依赖关系。当然也可上传到网站上作为静态网站文件访问。

`_book` 目录内的 `index.html` 文件是电子书的访问文件，双击打开，即可在浏览器上访问和查看。
