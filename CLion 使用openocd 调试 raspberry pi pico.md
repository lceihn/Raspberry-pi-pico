## CLion使用openocd 调试 raspberry pi pico

- CLion中Openocd位置: **openocd.exe** 改为 **openocd_rp2040.exe**

- 面板配置文件内容为
```
source [find interface/picoprobe.cfg] #不同仿真器使用不同配置, 这里使用的是官方的picoprobe

source [find target/rp2040.cfg]

# 为了能正常烧录
proc init_board {} {
    gdb_port 3333;
}
```

