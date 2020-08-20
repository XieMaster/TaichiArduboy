# TaichiArduboy
基于Arduboy框架的游戏机项目。完全兼容Arduboy，紧凑硬件设计，实测续航约28h。

<div align="center"><img width="100%" src="imgs/gamebottitle.jpg"> </div>

### 总览

 TaichiArduboy是一个Arduboy框架的开源硬件设计。设计需要焊接，为方便DIY，全部元件采用直插，并选择最常见的方便采购的元件。口袋游戏机兼容所有arduboy游戏，您也可以编写自己的游戏上传。设置了开关控制蜂鸣器通断，板上也设置了锂电池充放一体模块，可插接JST头转接软包锂电池



### 运行说明

联机对战需要两台机子，两块8266开发板之间需要通过wifi进行连接。其中开启AP模式的是master机，开启STA模式的是slave机。游戏过程中，两台机子之间通过UDP协议传输己方球拍的位置数据，同时接受对方球拍的位置数据，以此达到数据同步的联机游戏效果。若对8266的AP模式和STA模式有疑问，请参阅[此处](http://www.taichi-maker.com/homepage/iot-development/iot-dev-reference/esp8266-c-plus-plus-reference/)。若不了解UDP协议在本游戏中的具体应用，可以参看[此例程](http://www.taichi-maker.com/homepage/iot-development/iot-dev-reference/esp8266-c-plus-plus-reference/wifiudp/esp8266-udp-led/)进一步了解

<div align="center"><img width="100%" src="imgs/udp.jpg"> </div>


### 材料清单
|         材料          | 数量 |
| :-------------------: | :--: |
| ArduinoPromicro开发板 |  2   |
|     0.96寸OLED屏      |  2   |
|       按键开关        |  4   |
|         跳线          | 若干 |
|        面包板         |  2   |

注：主控请一定使用ArduinoPromicro，

### 接线图

如果没有PCB电路板，或者不方便焊接，您可以用面包板搭建一个小掌机，遵照以下电路图即可

<div align="center"><img width="100%" src="imgs/pong_hardware.png"> </div>




### 获取电路板
电路板制作文件位于 /电路板加工文件 文件夹下。gerber文件请直接在PCB板厂计价入口提交压缩包。
使用的第三方库有：

- Adafruit_GFX库
- Adafruit_SSD1306库

请前往[太极创客第三方库下载页面](http://www.taichi-maker.com/homepage/download/#library-download)进行下载。

如果对ESP8266-NodeMCU开发板的使用有疑问，请参看[此处](http://www.taichi-maker.com/homepage/esp8266-nodemcu-iot/iot-c/esp8266-iot-basics/)的说明

如果对添加第三方库库有疑问，请参看[此处](http://www.taichi-maker.com/homepage/reference-index/arduino-library-index/install-arduino-library/)的说明

如果对烧录代码到8266有疑问，请参看[此处](http://www.taichi-maker.com/homepage/esp8266-nodemcu-iot/iot-c/esp8266-iot-basics/)的说明



### 搭建说明

#### step1

确认元件是否买齐，插上电路板确定封装是否正确

<div align="center"><img width="100%" src="imgs/step1.jpg"> </div>



#### step2

进行焊接。焊接顺序为电源模块→屏幕→按键→ArduinoPromicro→蜂鸣器→蜂鸣器开关和电源开关

<div align="center"><img width="100%" src="imgs/step2.jpg"> </div>



#### step3

wifi连接完成后，oled会提示，当玩家准备好开始游戏后按下按键↓

<div align="center"><img width="100%" src="imgs/step3.jpg"> </div>



#### step4

当双方均按下按键时，游戏正式开始。两个按键代表上下移动球拍，一旦一方没有接住球，另一方就会增加一分。游戏将持续进行↓

<div align="center"><img width="100%" src="imgs/step4.jpg"> </div>



### 待优化的问题

您如果进行了游戏，可以看到，双方传输数据其实是有一定延迟的。而且除了球拍的位置数据互相传输以外，其实没有其他数据交互。相当于一旦因为延迟出现误差，主机和从机会出现不同步的游戏局面。这一点可通过增加球位置校验等方法解决，也可以通过进一步优化代码来解决。您可以尝试修改或升级这个简单的游戏，解决这些小瑕疵。我们也会继续优化代码，以追求更优的效果。



### 更多信息

这个小制作只是展示了8266网络对战的效果，用到的物联网相关应用知识并不困难。如果您想学习更多物联网开发相关知识，请访问[太极创客官网](http://www.taichi-maker.com/)获取更多教程。


