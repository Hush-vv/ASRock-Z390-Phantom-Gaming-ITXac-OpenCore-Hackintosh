# ASRock Z390 Phantom Gaming- ITX/ac-OpenCore-Hackintosh


## 电脑配置
|规格 | 详细信息|
|:-: | :-:|
|主板型号| ASRock Z390 Phantom Gaming-ITX/ac |
|操作系统| macOS Big Sur 11.1（20C5061b） |
|处理器| 英特尔 酷睿i9 9900k |
|内存| 芝奇 16GBx2 3200Mhz C16 |
|硬盘| 西数 SN750 1T |
|显卡| XFX Radeon VII |
|显示器| 优派 VX2780-4K-ZERO |
|声卡| Realtek ALC1220 |
|网卡| 94360CS2 |

## 使用说明

### BIOS设置

- BIOS版本：V4.40C

  - Advanced \ Chipset Configuration → Vt-d : Disabled

  - Advanced \ USB Configuration → XHCI Hand-off : Enabled

  - Advanced \ Chipset Configuration → Share Memory : 128MB

  - Advanced \ Chipset Configuration → IGPU Multi-Monitor : Enabled
    
### 驱动 `Thunderbolt3`接口

- 刷入BIOS`V4.40C`按照下图设置 `Thunderbolt3` 的`BIOS`

   ![BIOS](Docs/IMG_2487.jpeg)

- 添加SSDT，`SSDT-DTPG.aml` （必须）`SSDT-TbtOnPch_PINI_D8.aml` or `SSDT-TbtOnPch_PINI.aml`

- 打开IOJones搜索rp21 查看reg。如果是dc选用`SSDT-DTPG.aml `+ `SSDT-TbtOnPch_PINI.aml`，如果是D8就选用`SSDT-DTPG.aml` + `SSDT-TbtOnPch_PINI_D8.aml`

 ![IOJones](Docs/IMG_2488.png)

- 添加布丁`_E2C` to`XE2C`
 
  ![添加布丁](Docs/IMG_2489.png)
 
- 重启成功驱动！
  
  ![TB3](Docs/IMG_2490.png)
  
- `SSDT-TbtOnPch_PINI_D8_Win.aml` or `SSDT-TbtOnPch_PINI_Win.aml`可解决`OpenCore`引导`Windows`时出现蓝屏(`ACPI_BISO_Error`)问题。请按需求替换

-  [固定`域UUID`](https://github.com/Hush-vv/ASRock-Z390-Phantom-Gaming-ITXac-OpenCore-Hackintosh/blob/master/Docs/%E5%9B%BA%E5%AE%9A%60%E5%9F%9FUUID%60.md)

- `SSDT-XHC-TbtTypeC.aml`是TypeC端口，需开机前插入（如果使用了`SSDT-TbtOnPch_PINI_D8.aml` or `SSDT-TbtOnPch_PINI.aml`无需使用`SSDT-XHC-TbtTypeC.aml`！）。
  - 使用`SSDT-XHC-TbtTypeC.aml`时需要`ACPI`-`Delete`-`ltem1`-`Enabled`=`YES`

- 已通过ACPI定制全部USB端口，无需重复定制。

- `RadeonBoost.kext`支持下列显卡“优化”，请按需打开。`AMD RX5000系列`请自行在`boot-args`处添加`agdpmod=pikera`

  - RX 5500
  - RX 5500 XT
  - RX 5600
  - RX 5600 XT
  - RX 5700
  - RX 5700 XT
  - Radeon VII
  - RX480
  - RX580
  - RX590
  
### 其它设置
  
 ![其它设置1](Docs/IMG_2493.png)
   
 ![其它设置2](Docs/IMG_2494.png)
  
### 感谢
 
 -  @宪武 大佬
 - [fangf2018](https://github.com/fangf2018/ASRock-Z390-Phantom-ITX-OpenCore-Hackintosh)
  


