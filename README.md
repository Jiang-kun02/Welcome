# FOC硬件设计

## 单元测试
- STM32F103C8T6标准版
- STM32F103C8T6最小系统板(带IIC的OLED)
- DCDC模块12V转5V和3.3V

## STM32F103C8T6标准版
    这块板子的USB模块那里我并没有画差分线，而且走线还有点曲折。

![STM32F103c8t6抄板](.\Picture\STM32F103c8t6抄板.jpg)

## STM32F103C8T6最小系统板(带IIC的OLED)
    这块板子里面其实带来模拟输入端口，其中的两个0欧电阻式用来连接模拟地、GND 和 3V3和模拟3V3的，但其实没用他可以去掉，同时用排针引出了SW下载端口，同时引出了OLED显示屏的连接线。

![单片机最小系统板](.\Picture\单片机最小系统板.jpg)

## DCDC模块12V转5V和3.3V
    这块板子在FB端口连接了两个反馈电阻，他们会影响输出电压。
    Vout = 0.8 * (R1 + R2) / R2 
    在电路图中R1 = 10KΩ ， 按照道理来说R2 = 1.9KΩ左右，但是没有这种电阻。
    实测12V输入，输出5.22V 和 3.24V 左右.

![FOC的开关电源模块](.\Picture\FOC的开关电源模块.jpg)
