# Hackintosh_Envy13_10.13.6/10.14
前言：**_社区共同开发成果，希望用于个人DIY和技术交流，不得用于商业用途，淘宝贩子还请绕道！_** 
仓库为缺省版本，删除了部分核心文件，并不能直接食用，防止TB店家直接盗用。需要完整版请加页面最下方的交流群免费获取、一起交流、参与贡献！

> 进群切勿当伸手党，请先自己逛 [黑果小兵](https://blog.daliansky.net/) 和 [远景论坛](http://bbs.pcbeta.com/) ，学习基本安装流程之后自己动手，在群里讨论关键性问题。

## 完美适用于Hp Envy13 2017 ad1xxx 
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6-10.14/blob/master/Pictures/QQ20190213-145037%402x.png)
LZ的Envy13 2017配置为i5 8250u + uhd620 + 8G + 256G + Bcm94352z，惠普其它型号，可以进群寻找EFI、讨论及共同开发完美版本（群号在最下面）。

### 开启HIDPI（系统原生缩放和显示更细腻）
* 项目原地址: [Enable macOS HiDPI](https://github.com/xzhih/one-key-hidpi)
* 一键安装命令：
```
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
```

### 优秀Mac资源网站：
* [马可菠萝-分享您喜欢的Mac应用](https://www.macbl.com/)
* [爱情守望者](https://www.waitsun.com/)
* [Mac玩法](https://www.waerfa.com/)
* [威锋-MacOS软件分享区](https://bbs.feng.com/thread-htm-fid-19.html)
* [MacEnjoy-Crack](https://www.macenjoy.co/)

### 软件推荐
1. 功能增强工具，自己看图看名称
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6-10.14/blob/master/Pictures/QQ20190213-145744%402x.png)
2. 神器：鼠标悬浮预览 + 拖拽全屏/窗口 
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6-10.14/blob/master/Pictures/QQ20190213-150642.png)
3. others：
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6-10.14/blob/master/Pictures/QQ20190213-150401%402x.png)
以上软件在资源网站里面都能找到。

### 声卡
声卡ID用的3，可以驱动下面两个喇叭，声音大一些，四个喇叭同时驱动还在寻找方法
有了Hotpatch的话，改config里面的ID是没用的，要改 ```/Volumes/EFI/EFI/CLOVER/ACPI/patched``` 下的 ```SSDT-Config.aml``` 和```
SSDT-HDEF.aml```对应位置的ID，可用的还有13，28
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6/blob/master/Pictures/QQ20180919-235329@2x.png)

### 目前还存在的问题
1. Windows非正常关机，再引导到MacOS后会长时间读条，强制关机再开机即可
2. 不同BIOS版本出的问题不一样，有的睡眠后不出声音，有的蓝牙和Wi-Fi失效

### 交流群
* Envy13(2017)交流群：[247548827](https://jq.qq.com/?_wv=1027&k=5DaEwE0)
* 惠普电脑Mac交流群：[543758684](https://jq.qq.com/?_wv=1027&k=5lZnwck)
