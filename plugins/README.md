# 插件

插件是扩展GitBook功能的最佳方式 (电子书 and 网站). T有很多插件可以做很多事情:提供数学公式显示支持, 使用谷歌分析的跟踪访问, etc.

### 如何找到插件吗?

可以很容易地对插件进行搜索 [plugins.gitbook.com](https://plugins.gitbook.com).


### 如何安装插件?

一旦你找到了你想要安装的插件，你需要将它添加到你的插件中 `book.json`:

```
{
    "plugins": ["myPlugin", "anotherPlugin"]
}
```

您还可以指定一个特定的版本: `"myPlugin@0.3.1"`. 在默认情况下，GitBook将使用当前的GitBook版本来解决插件的最新版本。.

### GitBook.com

插件被自动安装在 [GitBook.com](https://www.gitbook.com). 在本地, 运行 `gitbook install` 为你的书安装和准备所有的插件.

### Configuring plugins

插件特定的配置存储在 `pluginsConfig`. 您必须参考插件本身的文档，了解可用选项的详细信息.
