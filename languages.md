# 多语言

GitBook支持用多种语言编写的书籍。每一种语言都应该是遵循常规的GitBook格式的子目录，以及一个名为`LANGS.md`的文件。应该以以下格式出现在存储库的根目录中

```markdown
# Languages

* [English](en/)
* [French](fr/)
* [Español](es/)
```

### 配置每种语言

When a language book (ex: `en`) has a `book.json`, 它的配置将扩展主配置.

The only exception is plugins, plugins are specified globally, and language specific plugins cannot be specified.
唯一的例外是插件，插件是全局指定的，并且不能指定特定于语言的插件。
