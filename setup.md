# 安装 GitBook

安装好GitBook只需要几分钟.

### GitBook.com

[GitBook.com](https://www.gitbook.com) 是一种易于使用的解决方案来编写、发布和托管书籍. 它是发布内容和协作的最简单的解决方案。

它与[GitBook Editor](https://www.gitbook.com/editor)很好地整合在一起.

### 本地安装

##### 要求

安装GitBook是简单直接的,你的系统只需要满足两个要求:

* NodeJS (v4.0.0 以上版本)
* Windows, Linux, Unix, or Mac OS X

##### 通过NPM安装

安装GitBook最好的方式是通过 **NPM**.

```
$ npm install gitbook-cli -g
```

`gitbook-cli` 是在同一个系统上安装和使用GitBook的多个版本的实用程序. 它将自动安装所需版本的GitBook来构建一本书.

##### 构建一本书

GitBook 设置样板书:

```
$ gitbook init
```
如果你希望在一个新的目录制作书,你可以运行`gitbook init ./directory`

预览你的书可以执行:

```
$ gitbook serve
```

或者 建立静态网站可以执行:

```
$ gitbook build
```

##### 安装预览版本

`gitbook-cli` 很容易让你下载和安装其他版本的Gitbook去测试你的书:

```
$ gitbook fetch beta
```

用 `gitbook ls-remote` 列出可供安装的远程版本.

##### 调试

你可以用选项 `--log=debug` 和 `--debug` 去得到好的错误消息(跟踪). 例如:

```
$ gitbook build ./ --log=debug --debug
```
