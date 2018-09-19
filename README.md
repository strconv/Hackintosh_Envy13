# Hackintosh_Envy13_10.13.6

## 适用于Hp Envy13 ad1xxx 
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6/blob/master/Pictures/QQ20180919-233241%402x.png)

i5 8250u + uhd620 + 8G + 256G


### 声卡：
声卡ID用的3，可以驱动下面两个喇叭，声音大一些，四个喇叭同时驱动还在寻找方法
有了Hotpatch的话，改config里面的ID是没用的，要改 ```/Volumes/EFI/EFI/CLOVER/ACPI/patched``` 下的 ```SSDT-Config.aml``` 和```
SSDT-HDEF.aml```对应位置的ID，可用的还有13，28
![image](https://github.com/ArisHub/Hackintosh_Envy13_10.13.6/blob/master/Pictures/QQ20180919-235329@2x.png)

### 开启HIDPI：
#### 安装命令：
```
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
```
#### 修复睡眠/盒盖显示不正常：<br>

  先下载
  https://github.com/daliansky/XiaoMi-Pro/blob/master/HIDPI%20for%20Mi%20Pro/install.command
  然后运行
  
  <br>注：如果开启后开不了机，Clover 开启 -x
```
$ cd /Volumes/"Your System Disk Part"/System/Library/Displays/Contents/Resources/Overrides
$ VendorID=$(ioreg -l | grep "DisplayVendorID" | awk '{print $8}')
$ Vid=$(echo "obase=16;$VendorID" | bc | tr 'A-Z' 'a-z')
$ rm -rf ./DisplayVendorID-$Vid
$ cp -r ./backup/* ./
```

目前还存在的问题：
1.手动点击睡眠，在开机就变哑巴了，没声音了，蓝牙也跟着GG（无法解决）。
2.三不时冷启动会开五六分钟的机，进系统也是卡成狗。
错误日志是NVMe驱动崩溃，解决办法：盒盖一段时间再打开就不卡了。
另外一个方法就是改SMBIOS里面的机型，至于改什么自己试吧，欢迎交流
