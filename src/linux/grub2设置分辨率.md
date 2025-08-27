### 设置grub2 分辨率
1. 进入`grub` 命令行  
在`grub` 启动界面，按下`c` 键进入命令行界面
2. 查询支持的分辨率  
输入 `videoinfo` 得到支持的分辨率列表
3. 命令行设置选择的分辨率  
输入`terminal_output console`  进入终端模式，输入 `set gfxmode=1024x768` (x 不是*)
4. 退出  
`terminal_output gfxterm` 退出到图形模式

### 进入系统设置
/boot/grub/grub.cfg

