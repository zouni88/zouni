```python
import numpy as np

x = [1,2]
y = [2,3]
xx,yy = np.meshgrid(x,y)
# 生成对应的网格坐标点

```
Out:
```python
# 对应输出坐标点：(1，2),(1,3),(2,2,),(2,3)
[[1 2]
 [1 2]]
[[2 2]
 [3 3]]
 ```
