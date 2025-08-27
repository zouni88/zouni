## final和const区别
`final`：修饰变量，初始化之后不可改变值
> final name = 'zhangsan';

`const`：修饰常量
> const name = 'zhangsan';  

const常量值必须在编译期确定
```dart
  var zhangsan = 12;
  var lisi = 13;
  const sum = zhangsan + lisi; //error
  final sum = zhangsan + lisi; //ok

```

