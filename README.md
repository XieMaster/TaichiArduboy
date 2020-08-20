# TaichiArduboy
基于Arduboy框架的游戏机项目。完全兼容Arduboy，紧凑硬件设计，实测续航约28h。

<div align="center"><img width="100%" src="imgs/gamebottitle.jpg"> </div>

### 总览

 TaichiArduboy是一个Arduboy框架的开源硬件设计。设计需要焊接，为方便DIY，全部元件采用直插，并选择最常见的方便采购的元件。口袋游戏机兼容所有arduboy游戏，您也可以编写自己的游戏上传。设置了开关控制蜂鸣器通断，板上也设置了锂电池充放一体模块，可插接JST头转接软包锂电池。

### 材料清单
|         材料          | 数量 |
| :-------------------: | :--: |
| ArduinoPromicro开发板 |  1   |
|  0.96寸SPI 7针OLED屏  |  1   |
|       按键开关        |  7   |
| TP4056锂电池充放模块  |  1   |
|      无源蜂鸣器       |  1   |
|       PCB电路板       |  1   |
|       JST头一对       |  1   |
|      3.7v锂电池       |  2   |
|      M3六角铜柱       |  4   |
|        面包板         |  4   |
|        M3螺母         |  4   |

注：主控请一定使用ArduinoPromicro或兼容同型号开发板,本例程内请勿使用其他型号代替。如果有多的电路板，可以用六角铜柱和螺丝把两块电路板连在一起，做成半封闭外壳，更易携带。

<div align="center"><img width="100%" src="imgs/bom.jpg"> </div>



### 接线图

如果没有PCB电路板，或者不方便焊接，您可以用面包板搭建一个最简单的小掌机，遵照以下电路图即可。这个电路没有复位和电池模块，需要持续供电才能运行。

<div align="center"><img width="100%" src="imgs/TaichiArduboy.jpg"> </div>




### 获取电路板
电路板制作文件位于 /电路板加工文件 文件夹下。gerber文件请直接在PCB板厂计价入口提交压缩包送厂制版（该文件在某厂商估价5元包邮），或采购散件进行焊接。

如果您想修改电路板文件，或制作自己的电路板印花，请访问此处


### 搭建说明

#### step1

确认元件是否买齐，插上电路板确定封装是否正确

<div align="center"><img width="100%" src="imgs/step1.jpg"> </div>



#### step2

进行焊接。焊接顺序为电源模块→屏幕→按键→ArduinoPromicro→蜂鸣器→蜂鸣器开关和电源开关

<div align="center"><img width="100%" src="imgs/step2.jpg"> </div>



#### step3

焊接完成后用数据线将TaichiArduboy连接上电脑

<div align="center"><img width="100%" src="imgs/step3.jpg"> </div>



#### step4

游戏上传一般有两种方式。

- 方式一：如果您有arduboy游戏的十六进制文件，您可以直接安装 /上传游戏 文件夹中的ArduboyUploader_setup.exe ，并打开游戏十六进制文件，选择游戏文件后烧录。烧录时如果没有反应，请按下游戏机上的RST键进行复位。本仓库 /上传游戏/不带源码的游戏 中有五个arduboy游戏的十六进制文件可供下载。

<div align="center"><img width="100%" src="imgs/step4.jpg"> </div>

- 方式二：如果您有arduboy游戏的源文件，请用arduinoIDE打开游戏的主程序（文件夹内的.ino文件），链接游戏机后选择Arduino/Genuino Micro开发板和相应的串口上传游戏。本仓库 /上传游戏/带源码的游戏 中有五个arduboy游戏的源码工程文件可供下载。

<div align="center"><img width="100%" src="imgs/step4B.jpg"> </div>



### 待优化的问题

您如果进行了游戏，可以看到，双方传输数据其实是有一定延迟的。而且除了球拍的位置数据互相传输以外，其实没有其他数据交互。相当于一旦因为延迟出现误差，主机和从机会出现不同步的游戏局面。这一点可通过增加球位置校验等方法解决，也可以通过进一步优化代码来解决。您可以尝试修改或升级这个简单的游戏，解决这些小瑕疵。我们也会继续优化代码，以追求更优的效果。



### 更多信息

这个小制作只是展示了8266网络对战的效果，用到的物联网相关应用知识并不困难。如果您想学习更多物联网开发相关知识，请访问[太极创客官网](http://www.taichi-maker.com/)获取更多教程。


