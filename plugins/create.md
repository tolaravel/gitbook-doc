# 创建并发布一个插件

GitBook插件是在NPM上发布的一个节点包，它遵循一个已定义的约定.

## 结构

#### package.json
`package.json`是描述 **Node.js modules** 的一种显示格式.GitBook插件是建立在node模块之上的.它声明了在GitBook中运行插件所需的依赖、版本、所有权和其他信息。 该文档详细描述了模式


A plugin manifest `package.json` can also contain details about the required configuration. The configuration schema is defined in the `gitbook` field of the `package.json` (This field follow the [JSON-Schema](http://json-schema.org) guidelines):

一个插件清单定义的 `package.json` 还可以包含所需配置的详细信息。配置模式在`package.json`的`gitbook`字段中定义 (此字段遵循[JSON 模式](http://json-schema.org)指导原则):

```js
{
    "name": "gitbook-plugin-mytest",
    "version": "0.0.1",
    "description": "This is my first GitBook plugin",
    "engines": {
        "gitbook": ">1.x.x"
    },
    "gitbook": {
        "properties": {
            "myConfigKey": {
                "type": "string",
                "default": "it's the default value",
                "description": "It defines my awesome config!"
            }
        }
    }
}
```

你可以学到更多关于  `package.json` 从 [NPM documentation](https://docs.npmjs.com/files/package.json).

这个 **package name** 必须以 `gitbook-plugin-` 开始 , 这个 **package engines** 应该包含 `gitbook`.

#### index.js

这个 `index.js` 是你的插件运行时的主要入口点:

```js
module.exports = {
    // Map of hooks
    hooks: {},

    // Map of new blocks
    blocks: {},

    // Map of new filters
    filters: {}
};
```

## 发布您的插件

GitBook插件可以发布到 [NPM](https://www.npmjs.com).

发布一个新插件, 你需要创建一个帐户 [npmjs.com](https://www.npmjs.com) 然后从命令行发布它:

```
$ npm publish
```

## 私人的插件

可以在GitHub上托管私有插件，并使用git url:

```
{
    "plugins": [
        "myplugin@git+https://github.com/MyCompany/mygitbookplugin.git#1.0.0"
    ]
}
```
