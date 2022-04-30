##                    使用EFISTUB替代initrd linux kernel

   对gnu/linux 而言，initranfs（initrd）确实是提供了可定制性，可编辑kernel_cmdline ，但对于geek而言，加载initramfs相比直接通过bootloader引导内核相对花费较多的时间，对于laptop 等便携式设备，极客更愿意构建一个适合本机硬件，减少启动时间，加快系统响应，个性化定制的一个内核。

  使用efistub意味着与内核配置取消对initrd的支持，built-in 内核命令行，build-in本机基础驱动，即静态编译基本驱动，如memory ，nvme 或sata ，acpi等驱动。

   pciutils可以获取当前电脑的硬件设备使用的内核模块与内联内核驱动!

```bash
lspci -nnk|more
```

  gnu/linux启动默认打印启动调试信息，这也为我们获取本机的firmware信息提供了便利!

```bash
sudo dmesg  |grep -i "firmware"|more
```



