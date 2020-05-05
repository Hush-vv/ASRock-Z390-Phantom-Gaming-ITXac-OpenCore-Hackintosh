# ASRock-Z390-Phantom-Gaming-ITXac-OpenCore-Hackintosh



## 电脑配置
|规格 | 详细信息|
|:-: | :-:|
|主板型号| ASRock Z390 Phantom Gaming-ITX/ac |
|操作系统|macOS Catalina 10.15.x |
|处理器|英特尔 酷睿 i9-9900k|
|内存|芝奇 16GBx2 3200Mhz C16|
|硬盘| 西数 SN750 1T |
|显卡|蓝宝石 5700XT 超白金|
|显示器|优派 VX2780-4K-ZERO|
|声卡| Realtek ALC1220|
|网卡| 94360CS2|

## 使用说明

### BIOS设置

- BIOS版本：V4.2

  - Advanced \ Chipset Configuration → Vt-d : Disabled

  - Advanced \ Super IO Configuration → Serial Port: Disabled

  - Advanced \ USB Configuration → XHCI Hand-off : Enabled

  - Advanced \ Chipset Configuration → Share Memory : 128MB

  - Advanced \ Chipset Configuration → IGPU Multi-Monitor : Enabled

### `OC-5700XT`文件说明

- 更新或安装系统时请确认以下内容的设置，否则会黑屏

  - `ACPI`-`Patch`-`ltem 2`-`Enabled`=`NO`
  - `Kernel`-`Add`-`ltem 4`-`Enabled`=`YES`
  - `Kernel`-`Patch`-`ltem 0`-`Enabled`=`NO`
  - `NVRAM` \ `Add` \ `7C436110-AB2A-4BBB-A880-FE41995C9F82` \ `boot-args` \ `agdpmod=pikera`  
  
 - 正常使用时可以将上面的内容反过来设置，以达到不使用`WhateverGreen.kext`的目的
  - `WhateverGreen.kext`请勿更新，这是一个定制版本

 ## 其他大佬的EFI
 
  - [fangf2018](https://github.com/fangf2018/ASRock-Z390-Phantom-ITX-OpenCore-Hackintosh)
  


