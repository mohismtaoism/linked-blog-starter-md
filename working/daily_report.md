# 2025.09.01

1.  Research CVSS tools for ultrasurgery
2.  Preparing LPC1114 pure-binary flashing solution and documents.

$$
\text{波特率} = \frac{\text{系统时钟频率}}{\text{分频系数}} 
$$
# 2025.09.08

1. 早上赖床不想起，耗到了卡点来的公司；
2. 来了公司写了篇文章《机器猫与Rick & Morty的异曲同工之妙》，结果网页异常，没保存下来，我草泥马！
3. AC了一道简单Two points的167的题目，2-sum，主要是为了解决3-Sum。
4. 耀辉的主机资料到了，大体看了下代码，主控代码有两个，还有vol_pwm的代码，感觉功率板也有mcu，具体明天再说。
5. 尝试3-sum，失败了，思路是想固定一个数，然后套用2-sum；
6. 在群里跟个傻逼吵了一架；
7. 去十三陵水库游了600米，然后买了一只扒鸡；

# 2025.09.09

## 产品小需求
	如何用TTS技术做到不方便语音的时候还是以语音发信息

1. 早上来得还算早，四点多就醒了，刷手机刷到六点起来看早之前买的《Skunk Works》，看到七点多去上班；
2. 用AI分析了下耀辉的Main_ic11代码，形成了文件；
	1. 目前有两个串口，注释显示一个是与HMI通信，一个是与电压控制小板通信，多余的串口需要我们自己添加？
	2. Main_ic10，Main_ic10两个mcu，这两个mcu在整个系统是如何分工的？
	3. ModBus是基于串口实现的？是不是实现了三个mcu的一个组网通信？

# 2025.09.10

1. Building main_ic10 and Burning it to the main board.
2. Analyze main_ic10 source code.

# 2025.09.11

1. Build main_ic11 and burn it;
2. Verify the pedal's function.
Questions:
	1. 请提供屏幕供应商细节，并且诉我界面的美术资源怎么获取，比如那些警告界面？