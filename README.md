# AndroidO-Extdisk-Mount
在高通平台验证，修改分区表预留一个extdisk分区，然后当做外置disk挂载。


## 关于exdisk image的制作

```
  mkfs.vfat -n "Internal SD" -F 32 -C usbdisk.tmp 1048576
	dd if=usbdisk.tmp of=udisk.img bs=1024 count=20480
  
	其中：
	- -n "ExtDisk" 是指定了卷标
	- 1048576 是磁盘空间大小，单位是KB
	- dd这个命令的目的就是将前面20MB的内容抠出来
```
