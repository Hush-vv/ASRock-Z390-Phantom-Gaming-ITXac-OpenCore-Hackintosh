## 固定`域UUID`


- 打开`系统报告`查看雷雳总线的`域UUID`将其复制替换到下面的`ToUUID ("989597F1-04F7-4D5C-95F4-30530FC5F2A6")` 中的`989597F1-04F7-4D5C-95F4-30530FC5F2A6`

```sw
Method (_DSM, 4, NotSerialized)  // _DSM: Device-Specific Method
{
    If (_OSI ("Darwin"))
    {
        Local0 = Package ()
            {
            "ThunderboltUUID", 
            ToUUID ("989597f1-04f7-4d5c-95f4-30530fc5f2a6"), 
            "sscOffset", 
            Buffer (0x02)
            {
                 0x00, 0x00                                       // ..
            }, 

            "power-save", 
            One, 
            Buffer (One)
            {
                 0x00                                             // .
            }
        }

```
  - 使用`MaciASL`打开你使用的`SSDT-TbtOnPch_PINI_D8.aml` or `SSDT-TbtOnPch_PINI.aml`另存为`SSDT-TbtOnPch_PINI_D8.dsl` or `SSDT-TbtOnPch_PINI.dsl`找到`HNI0`下的这个位置
  
![HNI0](Docs/IMG_2491.png)

- 将上面替换了`域UUID`的复制进`SSDT-TbtOnPch_PINI_D8.dsl` or `SSDT-TbtOnPch_PINI.dsl`中

![固定域UUID后](Docs/IMG_2492.png)

- 编译确认没有警告后另存为`SSDT-TbtOnPch_PINI_D8.aml` or `SSDT-TbtOnPch_PINI.aml`然后放入`EFI`中加载。这样每次启动后`域UUID`值就不会改变了
