# 生成 eBooks and PDFs

GitBook 能生成一个网站, 同时也能生成电子书 (ePub, Mobi, PDF).

```
# 生成 a PDF file
$ gitbook pdf ./ ./mybook.pdf

# 生成 an ePub file
$ gitbook epub ./ ./mybook.epub

# Generate a Mobi file
$ gitbook mobi ./ ./mybook.mobi
```

### 安装 ebook-convert

`ebook-convert` 是生成电子书必备的 (epub, mobi, pdf).

##### OS X

Download the [Calibre application](https://calibre-ebook.com/download). After moving the `calibre.app` to your Applications folder create a symbolic link to the ebook-convert tool:

```
$ sudo ln -s ~/Applications/calibre.app/Contents/MacOS/ebook-convert /usr/bin
```

You can replace `/usr/bin` with any directory that is in your $PATH.

### Cover 封面图片

Covers 被用于所有电子书格式. 你可以自己制作, 或 用 [autocover plugin](https://plugins.gitbook.com/plugin/autocover)来生成一个.

提供的封面,命名为 **`cover.jpg`** 的文件在书的根目录.  **`cover_small.jpg`** 是小尺寸的封面. 这个封面必须是 **JPEG** 文件

一个好的封面应该尊重以下的指导方针:

* 尺寸: 1800x2360 pixels for `cover.jpg`, 200x262 for `cover_small.jpg`
* 无边框
* 清晰可见书名
* 任何重要的文本都应该在小尺寸版本中可见
