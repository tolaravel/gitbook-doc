# Theming 主题

从版本 3.0.0, GitBook 可以很容易地为主题. Books use the [theme-default](https://github.com/GitbookIO/theme-default) 为默认主题.

> **Caution**: 自定义主题可以阻止一些插件的正常工作.

### 一个主题的结构

主题是一个包含模板和资产的插件. 覆盖任何单独的模板是可选的, 因为主题总是扩展默认主题.

| 文件夹 | 描述 |
| -------- | ----------- |
| `_layouts` | 包含所有模板的主文件夹 |
| `_layouts/website/page.html` | 普通页面模板 |
| `_layouts/ebook/page.html` | 在电子书生成过程中，普通页面的模板 (PDF< ePub, Mobi) |


### 继承或定做书的主题

作者可以直接从他们的书源中扩展主题的模板 (不需要创建外部主题). 模板将在本书的`_layouts`文件夹中被解析,然后在安装的插件/主题中.

### Extend instead of Forking

当你想要让你的主题改变到多本书的时候, 替代默认的主题, 你可以用它来扩展它 [templating syntax](../templating/README.md):

```html
{% extends template.self %}

{% block body %}
    {{ super() }}
    ... This will be added to the "body" block
{% endblock %}
```

看一看 [API](https://github.com/GitbookIO/theme-api) theme 为了更完整的例子.

### 发布一个主题

主题以插件形式发布 ([see related docs](../plugins/README.md)) with a `theme-` prefix. 例如主题 `awesome` will be loaded from the `theme-awesome` 插件, 然后从 `gitbook-plugin-theme-awesome` NPM package.
