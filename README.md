# Hackintosh_Envy13_10.13.6/10.14

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
#### 修复睡眠/盒盖显示不正常：
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

### 目前还存在的问题：
1. Windows非正常关机，再引导到MacOS后会长时间读条，强制关机再开机即可
2. 不同BIOS版本出的问题不一样，有的睡眠后不出声音，有的蓝牙和Wifi失效

