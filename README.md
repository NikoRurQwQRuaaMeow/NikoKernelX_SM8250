# NikoKernelX_SM8250
该repo (`android14-lineage21-mod` 分支)主要基于[Lineage OS 21 xiaomi sm8250 kernel source](https://github.com/LineageOS/android_kernel_xiaomi_sm8250)。

原来这个repo(即`android12-stable-mod`/`android14-stable-mod`分支)是fork自[UtsavBalar1231的仓库](https://github.com/UtsavBalar1231/kernel_xiaomi_sm8250)，但切到`android14-stable`分支的时候，发现那套代码有睡死问题（202408的几个release），所以现在切到了基于lineage21的代码来搞。MIUI特性的代码以及部分的设备驱动抠自UtsavBalar1231的仓库。

维护和编译这个内核的主要目的是让HyperOS2 on Xiaomi10 Series的体验更接近官核并且拥有更多的新特性！内置了SukiSU+Susfs


注意：该内核的zip包不包含`dtbo.img`，并且不会刷你的dtbo分区。推荐使用原厂的`dtbo`，或者来自第三方系统包自带的dtbo（如果原作者确认那好用的话）。因为该源码build出来的`dtbo.img`有些小问题，比如在锁屏界面上尝试熄屏时，屏幕会突然闪一下到最高亮度。如果你刷过其它第三方内核，或者遇到一些奇怪的问题，建议检查一下你的`dtbo`是否被替换过。

如果你在TWRP卡刷时碰到了卡条问题，不用担心，你只需要等待20s手动重启就好啦

支持的设备:
| 设备代号  | 设备名称                           |
|-----------|----------------------------------|
| umi       | 小米10                            |
| cmi       | 小米10 Pro                        |
| cas       | 小米10 Ultra                      |
| thyme     | 小米10S                           |

该内核的其他特性/改进:
1. 支持USB串口驱动（CH340/FTDI/PL2303/OTI6858/TI/SPCP8X5/QT2/UPD78F0730/CP210X）
2. 支持EROFS
3. F2FS开启了realtime discard以更好的TRIM闪存
4. 支持 CANBus 和 USB CAN （如 CANable）适配器（一些折腾嵌入式的可能会喜欢这个）
5. zRAM 支持 LZ4、LZ4HC、ZSTD 压缩算法
