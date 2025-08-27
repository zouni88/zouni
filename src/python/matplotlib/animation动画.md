### 动画

```python
from matplotlib import animation,pyplot as plt
import numpy as np
fig,axe = plt.subplots()
x = np.arange(0,2*np.pi,0.01)
line, = axe.plot(x,np.sin(x))

def animations(i):
    line.set_ydata(np.sin(x+i/10))
    return line
def init():
    line.set_ydata(np.sin(x))
    return line

# func 动画更新函数回调
# frames : 帧数，共多少帧 播放完
# init_func : 初始化回调函数
# interval : 刷新间隔 ms 毫秒
# blit ：是否整体刷新
ani = animation.FuncAnimation(fig=fig,func=animations,frames=100,init_func=init,interval=20,blit=False)
plt.show()
```
