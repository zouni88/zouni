获取`map`第一个元素的方法
```python
map = {'a': 1, 'b': 2}
keys = map.keys()
# keys 是 dict_list类型 转成list
keys = list(keys)
# 利用第一个key来获取value
item1 = map[keys[0]]
print(item1)
```
打印结果：
```shell
1
```
