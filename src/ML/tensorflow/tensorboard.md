
```python

import tensorflow as tf
# 这一步在网络初始化后
mode.summary()

tf.summary.create_file_writer('logs')

```
### 指定要监听的工作日志目录
```shell
tensorboard --logdir logs
```
