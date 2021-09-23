
# 插件

GitBook 支持插件扩展。

插件安装的4个步骤：

```
1. 在 NPM 上搜索相关插件
2. 在 book.json 文件中配置插件信息
3. 执行 `gitbook install` 命令安装插件
4. 执行 `gitbook serve` 查看效果
```

**第一步：**

你可以从 [NPM](https://www.npmjs.com/) 上搜索到需要安装的相关插件。


**第二步：**

GitBook 的插件信息保存在书籍根目录下的 `book.json` 文件中，默认该文件不存在，需手动创建。

`book.json` 文件中定义了所有插件的信息，并以`json`的数据格式保存在文件中：

```json
{
    "plugins": [
      "插件1",    // 定义插件1 名称
      "插件2"    // 定义插件2 名称
    ],
    "pluginsConfig": {
        "插件1": {
          // 定义插件1的具体配置信息
        },
        "插件2":{
          //定义插件2的具体配置信息
        }
    }
}
```

可见 `book.json` 文件内容主要分为 `plugins` 和 `pluginsConifg` 两部分，`plugins` 定义着插件的名称，`pluginsConifg` 定义着插件的具体配置信息。


下面以安装 [Gitbook Donate Plugin 打赏插件](https://www.npmjs.com/package/gitbook-plugin-donate)为例，修改 `book.json` 内容为如下信息：

```json
{
    "plugins": ["donate"],
    "pluginsConfig": {
        "donate": {
          "wechat": "http://blog.willin.wang/static/images/qr.png",
          "alipay": "http://blog.willin.wang/static/images/qr.png",
          "title": "如果您觉得文章对你有帮助，可进行打赏.",
          "button": "打赏",
          "alipayText": "支付宝打赏",
          "wechatText": "微信打赏"
        }
    }
}
```

> 说明：当你创建完 `book.json` 的那一刻，源 `gitbook serve` 命令启动的服务会被中断。


**第三步：**

执行 `gitbook install` 命令安装插件，插件安装完成后，会在书籍的根目录下生成一个名为 `node_modules` 文件夹，里面存放的是所有已安装的插件程序。

![](https://my-picture-storage.oss-cn-hangzhou.aliyuncs.com/Markdown/20210923004457.png)


**第四步：**

执行 `gitbook serve` 命令，重新启动 GitBook 的web服务，接下来，你就可以在页面中看到插件实现的效果了。



## 推荐插件

- [Gitbook Donate Plugin （打赏按钮插件）](https://www.npmjs.com/package/gitbook-plugin-donate)
- [GitBook Plugin: Edit Link (Github 编辑按钮)](npmjs.com/package/gitbook-plugin-edit-link)
- [（Github 按钮）]()







