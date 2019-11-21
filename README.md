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
- truncate - 截取指定长度的字符串，第2个参数追加到字符串的尾部  {{ 'foobarfoobar' | truncate: 5, '.' }} # => 'foob.'
- strip_html - 删除 HTML 标签  {{ '<a href="">123</a>' | strip_html }} => 123
- 请参考： http://ju.outofmemory.cn/entry/149459
- 百度： jekyll语法 -> 第一条

# 全局变量
- page 代表当前页面，可以获取当前页面中定义的数据
- site 用于获取 `_config.yml` 配置文件中的数据
- content 用在模板文件中，代表子节点的内容
- paginator 获取分页的内容


# 目录结构
- _config.yml 文件，配置文件，在这个文件中配置的内容可以通过`site`全局变量获取