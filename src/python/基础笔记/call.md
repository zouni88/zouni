### call函数使用方法
  `__call__` 函数一般用于实例对象的回调,至少看起来实例对象的调用方式和函数一样
  `call` 函数一个普通的函数，一般实现父类的方法之后，会在父类的`__call__`函数中回调

    class Base():
    def call(self):
        print('我是base')

    def __call__(self, *args, **kwargs):
        self.call()


    class A(Base):

        def __init__(self, name):
            self.name = name

        def call(self):
            print(self.name)

实例化：

    a = A('small')
    a()

输出：

    small  

子类不实现call，则会输出：

    我是base
