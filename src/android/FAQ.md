## 经常遇到的问题：

### 读取本地存储文件权限受限
* open failed: EACCES (Permission denied)

```
//manifest.xml application标签
<application 
    android:requestLegacyExternalStorage="true"
/>

```