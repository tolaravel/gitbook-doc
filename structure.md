# 目录结构

GitBook采用一个简单的目录结构. 所有的 Markdown/Asciidoc 文件列表在 [SUMMARY](pages.md) 将被转换为 HTML. 多语言书籍略有 [不同的结构](languages.md).

基本的GitBook通常是这样的:

```
.
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```

以下是对这些内容的概述:

| 文件 | 描述 |
| -------- | ----------- |
| `book.json` | 储存 [配置](config.md) 数据 (__optional__) |
| `README.md` | 你书的前言 / 介绍  (**required**) |
| `SUMMARY.md` | 内容结构 (See [Pages](pages.md)) (__optional__) |
| `GLOSSARY.md` | 用于注释的词汇/列表 (See [Glossary](lexicon.md)) (__optional__) |

### 静态文件和图片

静态文件是未在 `SUMMARY.md`中列出的文件. 所有的静态文件, 除了 [ignored](#ignore), 被复制到输出中.

### Ignoring 文件 & 目录 {#ignore}

GitBook 将跳过从读取 `.gitignore`, `.bookignore` and `.ignore` 文件得到文件和目录.
这些文件中的格式, 遵循同样的惯例 `.gitignore`:

```
# This is a comment

# Ignore the file test.md
test.md

# Ignore everything in the directory "bin"
bin/*
```

### 项目集成子目录 {#subdirectory}

对软件项目, 可以使用子目录 (like `docs/`) 为项目的文档存储书籍. 您可以配置 [主选项](config.md) 为了显示吉本可以找到书文件的文件夹:

```
.
├── book.json
└── docs/
    ├── README.md
    └── SUMMARY.md
```

 `book.json` 包含:

```
{
    "root": "./docs"
}
```
