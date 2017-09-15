# 模板

GitBook uses the [Nunjucks templating language](https://mozilla.github.io/nunjucks/) 处理页面和主题的模板.

The Nunjucks syntax is very similar to **Jinja2** or **Liquid**. Its syntax uses surrounding braces `{ }` to mark content that needs to be processed.

### 变量

一个变量从模板内容中查找值. 如果你想简单地显示一个变量, 您将使用 `{{ variable }}` 语法. For example :

```twig
My name is {{ name }}, nice to meet you
```

它从内容中查找用户名并显示它. 变量名可以在其中包含点，查找属性, 就像 JavaScript. 还可以使用方括号语法.

```twig
{{ foo.bar }}
{{ foo["bar"] }}
```

如果一个值没有定义, 什么也不显示. 如果foo没有定义，下面所有输出都不会输出: `{{ foo }}`, `{{ foo.bar }}`, `{{ foo.bar.baz }}`.

GitBook 提供了一组 [预先变量](variables.md) 从内容里.

### 过滤

过滤器本质上是可以应用于变量的函数. 它们被称为管道操作符 (`|`) 和可以带参数.

```twig
{{ foo | title }}
{{ foo | join(",") }}
{{ foo | replace("foo", "bar") | capitalize }}
```

The third example shows how you can chain filters. It would display "Bar", by first replacing "foo" with "bar" and then capitalizing it.

### Tags

##### if

`if` tests a condition and lets you selectively display content. It behaves exactly as JavaScript's `if` behaves.

```twig
{% if variable %}
  It is true
{% endif %}
```

If variable is defined and evaluates to true, "It is true" will be displayed. Otherwise, nothing will be.

You can specify alternate conditions with `elif` and `else`:

```twig
{% if hungry %}
  I am hungry
{% elif tired %}
  I am tired
{% else %}
  I am good!
{% endif %}
```

##### for

`for` iterates over arrays and dictionaries.

```twig
# Chapters about GitBook

{% for article in glossary.terms['gitbook'].articles %}
* [{{ article.title }}]({{ article.path }})
{% endfor %}
```

##### set

`set` lets you create/modify a variable.

```twig
{% set softwareVersion = "1.0.0" %}

Current version is {{ softwareVersion }}.
[Download it](website.com/download/{{ softwareVersion }})
```

##### include and block

Inclusion and inheritance is detailled in the [Content References](conrefs.md) section.

### Escaping

If you want GitBook to ignore any of the special templating tags, you can use raw and anything inside of it will be output as plain text.

``` twig
{% raw %}
  this will {{ not be processed }}
{% endraw %}
```
