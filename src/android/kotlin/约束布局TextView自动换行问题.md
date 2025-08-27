1.修改textview的约束条件
```
app:layout_constraintStart_toEndOf="@+id/textView3"
改为
app:layout_constraintLeft_toRightOf="@+id/textView3"
```
注意 其他的start end也都改为left right 

2.其他属性搭配：
```
android:layout_height="wrap_content"
搭配：app:layout_constrainedWidth="true"

android:layout_height="wrap_content"
搭配：app:layout_constrainedHeight="false"（不写默认即false）

```
