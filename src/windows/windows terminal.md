1. windows新终端
    ![windows terminal](/res/windows/w_ter.png)

2. 可以自定义主题  
    1. 打开设置  
    ![打开设置](/res/windows/setting.png)

    2. 在这里选择一个喜欢的 [主题](https://atomcorp.github.io/themes/)

    ![选择主题](/res/windows/theme_site.png)

    将选择好的主题配置信息，放在下图`schemes`集合里

    ![修改配置文件](/res/windows/config_modify.png)

    修改上图`list`增加`colorScheme` 名字对应添加的schemes中的`name`

## 不够炫酷？修改背景图片，
```
"backgroundImage": "E:\\bg.png",
"backgroundImageOpacity": 0.3,
"backgroundImageStretchMode":"none", # 有四个选项 uniformToFill | none | fill | uniform 

```

![背景图设置](/res/windows/set_bg_image.png)  
`注意图片路径的反斜杠-转义或者用正斜杠`：'/' 否则会设置失败

## 最终效果：
![效果图](/res/windows/design.png)
重新打开终端，ok
