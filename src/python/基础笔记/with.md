`with`用法和原理：
```python
class Sample:
    def __enter__(self):
        print("In __enter__()")
        return "Foo"
    def __exit__(self, type, value, trace):
        print("In __exit__()")
def get_sample():
    return Sample()
with get_sample() as sample:
    print ("sample:%s" % sample)
```
运行代码，输出如下
```text
In __enter__()
sample: Foo
In __exit__()
```
先执行`__enter__`方法，最后执行`__exit__`方法退出
