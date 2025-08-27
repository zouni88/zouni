### flask-migrate 坑

1. 字段长度更新会提示 `No changes in schema detected.`

 解决办法：初始化Migrate的时候增加属性`compare_type`为True

```python
Migrate(app=app, db=db,render_as_batch = True,compare_type = True)

```
