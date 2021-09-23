# GitBook 安装部署

安装 Gitbook 非常简单，只需 2 步即可完成，下面以 Mac 平台部署为例。

> PS：Linux、Centos、Ubuntu 平台安装可访问 **[泰泰博客](https://www.taitaiblog.com)**，获取自动安装脚本程序完成安装。

1、安装 Node.js

由于 Gitbook 依赖于 Node.js 环境，因此在部署 Gitbook 前需先安装 Node.js ，步骤如下：

```shell
# 从 Node.js 官网下载安装包并安装
https://nodejs.org/zh-cn/

# 检查 node 安装情况
node --version

# 检查 npm 安装情况（务必保证可用）
npm --version
```

2、安装 Gitbook

```shell
# 安装Gitbook命令
sudo npm install -g gitbook-cli

# 检查是否安装成功
gitbook --version

# 查看安装位置
which gitbook
```

## 自动化安装脚本


```shell
#!/bin/bash

echo ####################################################
echo ## 功    能：自动安装 GitBook 服务脚本程序
echo ## 运行平台：CentOS、Ubuntu 
echo ##
echo ## 作    者：qintaiwu
echo ## 编写时间：2020/6/3
echo ## 个人博客：www.taitaiblog.com
echo ####################################################

echo "正在安装 Node.js "
cd /usr/local/
wget https://nodejs.org/dist/v12.18.0/node-v12.18.0-linux-x64.tar.xz &&
xz -dk node-v12.18.0-linux-x64.tar.xz && tar xvf node-v12.18.0-linux-x64.tar &&
mv ./node-v12.18.0-linux-x64 ./node &&
ln -s /usr/local/node/bin/node /usr/local/bin/node &&
ln -s /usr/local/node/bin/npm /usr/local/bin/npm &&

echo "正在安装 GitBook "
npm install gitbook-cli -g &&
ln -s /usr/local/node/bin/gitbook /usr/local/bin/gitbook
gitbook --version &&


echo ------------------------------
echo "Node.js 版本信息：" && node --version
echo "npm 版本信息：" && npm --version
echo "GitBook 版本信息：" && gitbook --version
echo ------------------------------
```

