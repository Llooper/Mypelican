Title:Acer Ubuntu亮度设置
Date:2015-06-26 17:50
Category:Ubuntu
Tags:Ubuntu,亮度
Author:Looper
Summary:关于Ubuntu亮度无法调节的问题解决。
##Ubuntu亮度调节
####亮度无法调节的原因
每次重装ubuntu时都因为显示比较亮，很刺眼的问题纠结。去查找了一下相关资料，发现：
NVIDIA GEFORCE 独立显卡没有为Linux系统开发显卡驱动，导致无法使用Fn或者直接在图形界面中调节亮度。
Linux大神还曾经因为这个吐槽过NVIDIA公司的，想要八卦的自行去看吧。

####调节方法
修改亮度存储文件brightness的亮度参数。网上说里边的参数是百分比，亲测实际不是，一打开时显示900多的。
brightness文件位置如下：/sys/class/backlight/intel_backlight 中，cd到该目录下ls一下就可以看到brightness文件了。
直接sudo vim brightness然后将参数修改为个人比较习惯的亮度就ok，本人比较习惯100-150的。
####修改配置文件
上面所说的修改只能保证当前使用时的状态，重启后又会变回很刺眼的情况，即birghtness中的数据又恢复为初始值。
要使得不用每次都很麻烦的去修改之中的数据，想到了修改系统启动配置文件rc.local。
rc.local为系统启动之后会执行的文件，初始化一些脚本，我们只需往其中添加我们需要开机启动的执行脚本就可以了。
操作如下： sudo vim /etc/rc.local
打开rc.local后，在exit 0之前添加一句脚本，将亮度数据写入birghtness文件即可，如下：
echo 150 > /sys/class/backlight/intel_backlight/brightness

配置自己想要的ubuntu亮度操作基本完成了。

