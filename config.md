# 配置

GitBook允许你使用灵活的配置来定制你的书. 这些选项在 `book.json` 文件中. 对于不熟悉JSON语法的作者, 您可以使用[JSONlint](http://jsonlint.com)工具来验证语法 .

### 一般配置

| 变量 | 描述 |
| -------- | ----------- |
| `root` | 路径到包含所有图书文件的根文件夹, 排除 `book.json`|
| `structure` | 指定路径 Readme, Summary, Glossary etc. 可以看看 [Structure paragraph](#structure). |
| `title` | 你的书的标题, 从README中提取默认值. On GitBook.com 这个字段是预先填写. |
| `description` | 你的书的描述, 从README中提取默认值. On GitBook.com 这个字段是预先填写. |
| `author` | 作者的名字. On GitBook.com 这个字段是预先填写. |
| `isbn` | 书的编号 |
| `language` | [ISO code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) 这本书的语言, 默认为 `en` |
| `direction` | 文字的方向. 可以是 `rtl` or `ltr`, 默认值取决于语言的值 |
| `gitbook` | 应该使用的GitBook的版本. 使用 [SemVer](http://semver.org) 规范并接受类似的条件 `">= 3.0.0"` |

### 插件 plugins

插件和它的配置在`book.json`中指定. 可以看看 [the plugins section](plugins/README.md) .

自版本 3.0.0以来, GitBook 可以使用主题. 更多细节可以看看 [the theming section](themes/README.md) .

| 变量 | 描述 |
| -------- | ----------- |
| `plugins` | 加载插件列表 |
| `pluginsConfig` |插件的配置信息 |

### 结构 structure

除了 `root` 变量之外, 你可以定义 Readme, Summary, Glossary, Languages 文件的名字 (而不是像 `README.md`一样默认的名字).
这些文件必须是你的书的root (or the root of every language book). 路径如 `dir/MY_README.md` 是不容许的.

| 变量 | 描述 |
| -------- | ----------- |
| `structure.readme` | Readme file name (defaults to `README.md`) |
| `structure.summary` | Summary file name (defaults to `SUMMARY.md`) |
| `structure.glossary` | Glossary file name (defaults to `GLOSSARY.md`) |
| `structure.languages` | Languages file name (defaults to `LANGS.md`) |

### PDF Options

 `book.json` 可以使用一组选项来定制PDF输出:

| 变量 | 描述 |
| -------- | ----------- |
| `pdf.pageNumbers` | 在每个页面的底部添加页码 (默认为 `true`) |
| `pdf.fontSize` | 基本字体大小 (默认为 `12`) |
| `pdf.fontFamily` | 基本字体 (默认为 `Arial`) |
| `pdf.paperSize` | 纸张大小, 选项有 `'a0', 'a1', 'a2', 'a3', 'a4', 'a5', 'a6', 'b0', 'b1', 'b2', 'b3', 'b4', 'b5', 'b6', 'legal', 'letter'` (默认为 `a4`) |
| `pdf.margin.top` | Top margin (默认为 `56`) |
| `pdf.margin.bottom` | Bottom margin (默认为 `56`) |
| `pdf.margin.right` | Right margin (默认为 `62`) |
| `pdf.margin.left` | Left margin (默认为 `62`) |
