# GitBook 常见问题

这个页面收集了关于GitBook格式和工具链的常见问题和答案

关于GitBook.com和编辑器的问题被收集到 [help.gitbook.com's FAQ](http://help.gitbook.com/faq.html).

#### 怎样才能把我的书 host/publish?

书籍可以很容易地出版在 [GitBook.com](https://www.gitbook.com). 但是GitBook输出可以托管在任何静态文件托管解决方案中.

#### 我能用什么来编辑我的内容?

Any text editor should work! But we advise using the [GitBook Editor](https://www.gitbook.com/editor). [GitBook.com](https://www.gitbook.com) also provides a web version of this editor.

---

#### Does GitBook supports RTL/bi-directional text ?

The GitBook format supports right to left, and bi-directional writing. To enable it, you either need to specify a language (ex: `ar`), or force GitBook to use RTL in your `book.json`:

``` json
{
    "language": "ar",
    "direction": "rtl"
}
```

With version 3.0 of GitBook, 它会根据内容自动检测到.
_Note that, while the output book will indeed respect RTL, the Editor doesn't support RTL writing yet_.

#### Should I use an `.html` or `.md` extensions in my links?

You should always use paths and the `.md` extensions when linking to your files, GitBook will automatically replace these paths by the appropriate link when the pointing file is referenced in the Table of Contents.

#### Can I create a GitBook in a sub-directory of my repository?

Yes, GitBooks can be created in [sub-directories](structure.md#subdirectory). GitBook.com and the CLI also looks by default in a serie of [folders](structure.md).

#### Does GitBook supports RTL languages?

Yes, GitBook automatically detect the direction in your pages (`rtl` or `ltr`) and adjust the layout accordingly. The direction can also be specified globally in the [book.json](config.md).

---

#### Does GitBook support Math equations?

GitBook supports math equations and TeX thanks to plugins. There are currently 2 official plugins to display math: [mathjax](https://plugins.gitbook.com/plugin/mathjax) and [katex](https://plugins.gitbook.com/plugin/katex).

#### Can I customize/theme the output?

Yes, both the website and ebook outputs can be customized using [themes](themes/README.md).

#### Can I add interactive content (videos, etc)?

GitBook is very [extensible](plugins/README.md). You can use [existing plugins](https://plugins.gitbook.com) or create your own!
