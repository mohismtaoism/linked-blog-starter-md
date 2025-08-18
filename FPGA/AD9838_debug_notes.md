# 简单介绍

us_logic用AD9838生成一定频率的脉冲，ad9838是一款DDS芯片。

# 初始化

上位机软件刚启动，会通过spi总线给FPGA发送一个AD9838_INIT_REG消息，然后给AD9838_Controller module的引脚ad9838_init产生一个脉冲。

# AD9838 control bits 详解

| Bit | Bit Name | Description                |
| --- | -------- | -------------------------- |
| D0  | Reserved | Must be zeros              |
| D1  | Mode     | 如果mode是1，输出三角波；是0的话，就输出正弦波 |
| D2  | Reserved | Must be zeros              |
| D3  |          |                            |

