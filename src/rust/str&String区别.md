### str和String区别：
通俗讲 String就像是`笔记本`,可以往里面写字符串；而str就像是一个`标签`,引用了`笔记本`里的一段内容；  
* String 是 Rust 标准库提供的可变、拥有所有权的字符串类型，底层是堆分配，可以动态增长和修改。
* str 是不可变的字符串切片类型，通常以 &str 形式出现，指向某个字符串的一部分，不能直接修改内容。
* String 可以通过 .as_str() 方法转换为 &str，而 &str 可以通过 .to_string() 或 String::from() 转换为 String。

```rust
let x = String::from("hi zouni");
let y:&str = &x[1..2];

//&str -> String
let x = "world";
let y:String = x.to_string();
```
