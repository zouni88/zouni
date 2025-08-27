### trait 函数集合，类似java中的interface接口

```rust
struct User{
    name:String,
    age:i8
}

trait Hello{
    fn hello(&self) -> String;
    fn print(&self){
        print!("hello trait");
    }
}

impl Hello for User{
    fn hello(&self) -> String {
        format!("hello {}",self.name)
    }
}

#[test]
fn trait_test(){
    let u = User{name:String::from("zhangsan"),age:18};
    u.print();
}
```