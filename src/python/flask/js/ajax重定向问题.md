ajax 收到服务器端返回请求`302`,服务端给定重定向地址

 服务端返回
```python
{'code': 302, 'data': '/cms/'}
```
前端处理
```javascript
$(function () {
  var url = window.location.pathname
  $.ajax({
      url: url+'logout',
      type: 'get',
      dataType:'json'
      success: function (data,status) {
          // var datas = JSON.parse(data)
          if(data.code === 302){
              location.href = data.data;
          }
          alert('重定向')
      },
      error: function (data) {
          console.log(data.toString())
      }
  })  
}
```
