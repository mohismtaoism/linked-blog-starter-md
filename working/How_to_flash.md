# 1. 安装JLink软件

一步一步往下点就行。

# 2. 部署烧录器

具体烧录器型号请咨询我司，需要一端插电脑usb接口，另一端接到主板上。
![[jflash_step6.png]]

# 3. 烧录步骤

1.  首先找到Segger J-Flash V8.xx，后面的xx是小版本号，具体可能不太一样，然后打开工程：
		![[jflash_step11.png]]
2.  选择工程文件
		![[jflash_step12.png]]
3. 以上两个步骤是第一次烧录必须经历的步骤，之后就直接打开现成的工程文件就行，如下图：
		![[jflash_step13.png]]
		Open recent project那里显示的上面步骤打开的LPC1114.jflash，然后点击Start J-Flash按钮，如下图：
		![[jflash_step14.png]]

4. 打开需要烧录的hex文件
		![[jflash_step15.png]]
		![[jflash_step16.png]]
		![[jflash_step17.png]]

5. 然后点击Target菜单，出现下拉菜单，先点击connect，再点击Production Programming
		![[jflash_step18.png]]
	