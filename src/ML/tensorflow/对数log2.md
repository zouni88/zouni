**tensorlfow math.log() 是以自然常数`e`为底 转化为以`2`为底：**  
 根据对数换底公式：  
 ∵

 ![log2](/res/tensorflow/log.png)  


    ∴ loge(4)/loge(2) = log2(4) = 2

 代码实例：
```python
import tensorflow as tf
x = tf.math.log(4.)/tf.math.log(2.)

```
Out:

    <tf.Tensor: shape=(), dtype=float32, numpy=2.0>

效果等同于 numpy log2(4)
```python
import numpy as np

np.log2(4)
```
Out:
```
2.0
```
