# 输出
用 `{{}}` 进行输出，如：
```
{{ age }}
{{ page.hehe }}
{{ '么么哒' }}
```

# 过滤器
对输出内容进行过滤。
## 格式
```
{{page.zhaiyao | truncate:5}}
```

## 常见的过滤器
过滤器名 | 描述
--- | ---
truncate |  截取指定长度的字符串，第2个参数追加到字符串的尾部  {{ 'foobarfoobar' | truncate: 5, '.' }} # => 'foob.'
strip_html |  删除 HTML 标签  {{ '<a href="">123</a>' | strip_html }} => 123
请参考： | http://ju.outofmemory.cn/entry/149459
百度查： | jekyll语法 -> 第一条

# 全局变量
- page 代表当前页面，可以获取当前页面中定义的数据
- site 用于获取 `_config.yml` 配置文件中的数据
- content 用在模板文件中，代表子模板的内容
- paginator 获取分页的内容


# 目录结构
- _config.yml 文件，配置文件，在这个文件中配置的内容可以通过`site`全局变量获取
- _includes 文件夹，用于放置include包含的文件



# 提取公共部分
1. include 包含的方式
> 1. 用 `{% include 文件路径 %}` 包含文件
> 2. 会去到网站根目录下的`_includes`文件夹下找相应的文件

2. layout 布局的方式(店长推荐)
> 1. 在网站根目录新建一个 `_layouts` 文件夹
> 2. 搞一个基本模板，将每个页面不同内容替换成 `{{content}}`
> 3. 在子模板中继承基本模板 
```
---
layout: 模板名
---
```
> 4. 子模板中的内容会自动被放到基本模板中 `{{content}}` 的位置