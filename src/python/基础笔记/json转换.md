### pyton对象转字符串
```python
import json

json.dumps(object,default=lambda obj:obj.__dict__,sort_keys = False,indent = 4,ensure_ascii = False)
json.dumps()     # 对象转json

# lambda  是python类对象的方法  dict 保存的是对象的字典转成的字符串
```

### json字符串转对象
```python  

# class必须试先init方法
classStus:
  list:list

  def__init__(self,d):
    self.__dict__=d
    jsons = {"list": [{"id": 1, "name": "cao", "age": 10, "profile": "曹的自我介绍"},{"id": 2, "name": "wang", "age": 20, "profile": "王的自我介绍"}]}
    jsons = json.dumps(jsons)    将python字典转成json串
    json.loads(jsons,object_hooks = class)

```
