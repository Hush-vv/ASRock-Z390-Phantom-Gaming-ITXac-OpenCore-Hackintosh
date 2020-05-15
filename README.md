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
  
  - 没有的选项跳过即可
  
  
### 使用说明

- 如果你的显卡是`AMD 5700XT`请按照以下设置即可达到相关的“优化”（更新或安装系统时请按照以下设置，否则会黑屏）

  - `ACPI`-`Add`-`ltem1`-`Enabled`=`YES`
  - `ACPI`-`Patch`-`ltem0`-`Enabled`=`YES`
  - `Kernel`-`Patch`-`ltem0`-`Enabled`=`NO`
  - `NVRAM` \ `Add` \ `7C436110-AB2A-4BBB-A880-FE41995C9F82` \ `boot-args` \ `agdpmod=pikera`  
  - 并将`EFI`文件夹下的`WhateverGreen.kext`替换掉OC-Kexts文件夹下的`WhateverGreen.kext`
  - `WhateverGreen.kext`（59kb）请勿更新，这是一个定制版本 
 
- `AMD 5700XT`正常使用时可以按照以下设置来达到不使用`WhateverGreen.kext`的目的

  - `ACPI`-`Add`-`ltem1`-`Enabled`=`YES`
  - `ACPI`-`Patch`-`ltem0`-`Enabled`=`YES`
  - `Kernel`-`Add`-`ltem4`-`Enabled`=`NO`
  - `Kernel`-`Patch`-`ltem0`-`Enabled`=`YES`
  - 删除 `agdpmod=pikera`  
  - 并将`EFI`文件夹下的`WhateverGreen.kext`替换掉OC-Kexts文件夹下的`WhateverGreen.kext`
  - `WhateverGreen.kext`（59kb）请勿更新，这是一个定制版本 
  
- `TB3`接口将`ACPI`-`Add`-`ltem3`-`Enabled`=`YES`即可支持热拔插
  
  - 使用`SSDT-TbtOnPch.aml`会导致`ACPI Error`请酌情按需开启
  
- 其它显卡按默认使用即可，如果想做优化请自行爬帖


 ## `fangf`大佬的EFI
 
  - [fangf2018](https://github.com/fangf2018/ASRock-Z390-Phantom-ITX-OpenCore-Hackintosh)
  


