显示字符实验例程说明

1. 例程说明

   本例程基于 ST7789V LCD显示屏，型号240x240。

2. 文件说明

| 文件名                  | 描述                                                         |
| ----------------------- | ------------------------------------------------------------ |
| st7789v.py              | 包含 ST7789V lcd 驱动初始化、写ASCII字符、写汉字以及显示图片的方法接口。 |
| fonts.py                | 字库，提供常见ASCII字符的两种大小的字库，分别是8x16和16x24，同时包含了实验中用到汉字的几种不同大小的字库。用户可根据自己的需要制作字库，使用PCtoLCD2002软件，参照fonts.py中说明来制作。 |
| example_display_char.py | 主程序，调用st7789v.py和fonts.py中接口及信息来实现ASCII字符的显示与汉字的显示。 |

3. 显示效果

<img src="H:\工作\项目\Quecpython\任务\小实验文档编写-20200105\ST7789V\例程\显示字符\显示结果.jpg" alt="显示结果" style="zoom:80%;" />