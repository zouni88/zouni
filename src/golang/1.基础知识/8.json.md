### json编码
```go
type Person struct {
	Name string `json:"name"`
	Age int `json:"age,omitempty"`
}

type Toys struct {
	Person
	Toys []string `json:"toys"`
}

func main(){
    p := Person{Name:"cao",Age:12}
    toys := []string{"a","b"}
    toy := Toys{Person:p,Toys: toys}
    resbyte,err := json.Marshal(toy)
    if err != nil{
      log.Fatal(err)
    }
    // 返回byte切片，转成string类型
    resstring := string(resbyte)
    fmt.Println(resstring)
}

```
Out:
```
{"name":"cao","toys":["a","b"]}
```

`json:"age"` : 可以理解成别名，

`oemiempty` ： 值为空，就忽略此字段
### 解码json  Unmarshal()
将json字符串转成结构体变量，json.Unmarshal()必须传入byte切片
