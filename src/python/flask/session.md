session 过期时间

```python
def login():   
    session.permanent = True
    app.permanent_session_lifetime = timedelta(minutes=1) # 设置session到期时间
```
