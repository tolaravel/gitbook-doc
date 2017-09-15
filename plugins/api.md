# 上下文和api

GitBooks为插件提供了不同的api和上下文. 这些api可以根据被使用的GitBook版本而变化, 你的插件应该指定`engines.gitbook`包。相应的`package.json`.

#### 书中实例

这个 `Book` 类是 GitBook的焦点, 它将所有访问读取方法集中起来. 这个类是在 [book.js](https://github.com/GitbookIO/gitbook/blob/master/lib/book.js)中定义的.

```js
// 从 book.json 读取配置
var value = book.config.get('title', 'Default Value');

// 将文件名解析为绝对路径
var filepath = book.resolve('README.md');

// 呈现一个内联标记字符串
book.renderInline('markdown', 'This is **Markdown**')
    .then(function(str) { ... })

// 呈现一个标记字符串(块模式)
book.renderBlock('markdown', '* This is **Markdown**')
    .then(function(str) { ... })
```

#### output实例

这个 `Output` 类 代表了 output/write 方法.

```js
// 返回根文件夹用于输出
var root = output.root();

// 在输出文件夹中解析一个文件
var filepath = output.resolve('myimage.png');

// 将文件名转换为URL (返回到html文件的路径)
var fileurl = output.toURL('mychapter/README.md');

// 在输出文件夹中写入一个文件
output.writeFile('hello.txt', 'Hello World')
    .then(function() { ... });

// 将一个文件复制到输出文件夹
output.copyFile('./myfile.jpg', 'cover.jpg')
    .then(function() { ... });

// 验证文件是否存在
output.hasFile('hello.txt')
    .then(function(exists) { ... });
```

#### Page 实例

A page . 实例 表示当前已解析的页面e.

```js
// 页面的标题 (from SUMMARY)
page.title

// 页面的内容 (Markdown/Asciidoc/HTML according to the stage)
page.content

// 书中的相对路径
page.path

// 文件的绝对路径
page.rawPath

// 用于此文件的解析器类型
page.type ('markdown' or 'asciidoc')
```

#### Blocks和filters的上下文

Blocks and filters 可以访问相同的 context, 该上下文与模板引擎执行绑定:

```js
{
    // 当前的模板语法
    "ctx": {
        // 例如, after a {% set message = "hello" %}
        "message": "hello"
    },

    // Book 实例
    "book" <Book>,

    // Output 实例
    "output": <Output>
}
```

For example a filter or block function can access the current book using: `this.book`.

例如，一个过滤器或块函数可以使用:this.book来访问当前的图书。

#### Context for Hooks

Hooks only have access to the `<Book>` instance using `this.book`.

钩子只能使用`this.book`来访问它的作用。
