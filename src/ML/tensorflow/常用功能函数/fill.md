```python
# %%
import tensorflow as tf
from matplotlib import pyplot as plt

x = tf.zeros([2, 2], dtype=tf.int32)
# 如果要画一个灰度图，那么如下
# 填充一个[2,2]的矩阵为128 也就是灰色值
# [[255,255],
# [255,255]]
z = tf.fill([2, 2], 128)
# 在最后一个维度展开一次，变成[2,2,1]
z = tf.expand_dims(z, axis=-1)
# 在最后一个维度平铺3次
# [2,2,3]
z = tf.tile(z, [1, 1, 3])
plt.imshow(z)
plt.show()

```

![fil](/res/tensorflow/fill1.png)
```python
# %%
# 画一个红色的图，也很简单
# 三个通道不同颜色 比如洋红色的rgb色值[255,0,255]
r = tf.fill([3, 3], 255)
g = tf.zeros([3, 3],dtype=tf.int32)
b = r
img = tf.stack([r, g, b], axis=-1)
img.shape
# 一个3x3的图片就诞生了
plt.imshow(img)
plt.show()
```
![fill2](/res/tensorflow/fill2.png)
