# Hackintosh_Envy13_10.13.6/10.14

## 适用于Hp Envy13 ad1xxx 
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6-10.14/blob/master/Pictures/QQ20190213-145037%402x.png)
i5 8250u + uhd620 + 8G + 256G + Bcm94352z

### 开启HIDPI
#### 安装命令
```
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
```
### 优秀Mac资源网站：
* [马可菠萝-分享您喜欢的Mac应用](https://www.macbl.com/)
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

### 声卡
声卡ID用的3，可以驱动下面两个喇叭，声音大一些，四个喇叭同时驱动还在寻找方法
有了Hotpatch的话，改config里面的ID是没用的，要改 ```/Volumes/EFI/EFI/CLOVER/ACPI/patched``` 下的 ```SSDT-Config.aml``` 和```
SSDT-HDEF.aml```对应位置的ID，可用的还有13，28
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6/blob/master/Pictures/QQ20180919-235329@2x.png)

#### 修复睡眠/盒盖显示不正常：
下载
https://github.com/daliansky/XiaoMi-Pro/blob/master/HIDPI%20for%20Mi%20Pro/install.command
后运行
  
  <br>注：如果开启后开不了机，Clover 开启 -x
```
$ cd /Volumes/"Your System Disk Part"/System/Library/Displays/Contents/Resources/Overrides
$ VendorID=$(ioreg -l | grep "DisplayVendorID" | awk '{print $8}')
$ Vid=$(echo "obase=16;$VendorID" | bc | tr 'A-Z' 'a-z')
$ rm -rf ./DisplayVendorID-$Vid
$ cp -r ./backup/* ./
```

### 目前还存在的问题
1. Windows非正常关机，再引导到MacOS后会长时间读条，强制关机再开机即可
2. 不同BIOS版本出的问题不一样，有的睡眠后不出声音，有的蓝牙和Wifi失效

### 交流群
* Envy13(2017)交流群：247548827
* 惠普电脑Mac交流群：543758684
