vue 和jinjia2模板冲突：
1. 修改vue模板：

```
delimiters: ['{[', ']}']
```
2. 修改jinjia2模板：

```
app.jinja_env.variable_start_string = '[['
app.jinja_env.variable_end_string = ']]'

```
