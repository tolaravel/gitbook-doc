# 页面和总结

### 总结

GitBook 用`SUMMARY.md`文件去定义书的章节和目录. 这个`SUMMARY.md` 文件用来生成书的目录表.

`SUMMARY.md`的格式仅仅是个链接的列表. 链接的标题用做章节的标题,链接是对应的章节的文件的路径.

在父类中添加一个嵌套的列表将会创建子章节

##### 简单的例子

```markdown
# Summary

* [Part I](part1/README.md)
    * [Writing is nice](part1/writing.md)
    * [GitBook is nice](part1/gitbook.md)
* [Part II](part2/README.md)
    * [We love feedback](part2/feedback_please.md)
    * [Better tools for authors](part2/better_tools.md)
```

每个章节有专用页面并被划分为子章节.


##### 锚点

目录中的章节可以使用锚点指向文件的特定部分。

```markdown
# Summary

### Part I

* [Part I](part1/README.md)
    * [Writing is nice](part1/README.md#writing)
    * [GitBook is nice](part1/README.md#gitbook)
* [Part II](part2/README.md)
    * [We love feedback](part2/README.md#feedback)
    * [Better tools for authors](part2/README.md#tools)
```


##### 部件

目录可以分为若干部分，由标题或横线分隔

```markdown
# Summary

### Part I

* [Writing is nice](part1/writing.md)
* [GitBook is nice](part1/gitbook.md)

### Part II

* [We love feedback](part2/feedback_please.md)
* [Better tools for authors](part2/better_tools.md)

----

* [Last part without title](part3/title.md)
```

部分只是章节的一组，没有专门的页面，但是根据主题，它将在导航中显示。

### Pages

#### Markdown syntax

Most of the files for GitBook use the Markdown syntax by default. GitBook infers your pages's structure from it. The syntax used is similar to the [GitHub Flavored Markdown syntax](https://guides.github.com/features/mastering-markdown/). One can also opt for the [AsciiDoc syntax](asciidoc.md).

##### Example of a chapter file

``` markdown
# Title of the chapter

This is a great introduction.

## Section 1

Markdown will dictates _most_ of your **book's structure**

## Section 2

...

```

#### 扉页

Pages can contain an optional front matter. It can be used to define the page's description. The front matter must be the first thing in the file and must take the form of valid YAML set between triple-dashed lines. Here is a basic example:

```yaml
---
description: This is a short description of my page
---

# The content of my page
...
```
前面的内容可以定义您自己的变量，它们将被添加到页面[变量](templating/variables.md)中，以便您可以在模板中使用它们。
