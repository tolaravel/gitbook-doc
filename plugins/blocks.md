# 扩展模块

扩展模板块是向作者提供额外功能的最佳方式.

最常见的用法是在运行时处理某些标记中的内容. It's like [filters](./filters.md), 但是在形式上你并不局限于一个单一的表达.

### 定义一个新的模块

模块是由插件定义的, 模块是与模块描述符相关联的名称的映射. 模块描述符需要至少包含一个 `process`方法.

```js
module.exports = {
    blocks: {
        tag1: {
            process: function(block) {
                return "Hello "+block.body+", How are you?";
            }
        }
    }
};
```

这个 `process` 应该返回替换标签的html内容. 参考 [Context and APIs](./api.md) 去学习 `this` and GitBook API.

### 处理 block 模块的参数

可以将参数传递给模块:

```
{% tag1 "argument 1", "argument 2", name="Test" %}
This is the body of the block.
{% endtag1 %}
```

在过程方法中，参数很容易被访问:

```js
module.exports = {
    blocks: {
        tag1: {
            process: function(block) {
                // block.args equals ["argument 1", "argument 2"]
                // block.kwargs equals { "name": "Test" }
            }
        }
    }
};
```

### 处理 子模块

A defined block can be parsed into different sub-blocks, for example let's consider the source:

可以将已定义的块解析为不同的子块，例如，让我们考虑源代码:

```
{% myTag %}
    Main body
    {% subblock1 %}
    Body of sub-block 1
    {% subblock 2 %}
    Body of sub-block 1
{% endmyTag %}
```
