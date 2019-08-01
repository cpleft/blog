# 修改grub引导上次启动的系统
在一个机器上装了linux的多系统之后，系统的引导程序默认会变成grub。grub在引
导的时候，默认引导列表中的第一个系统。

将它配置成引导上次启动的系统

```
$ sudo vim /etc/default/grub
```

```
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT=true
```

```
$ sudo update-grub
Sourcing file `/etc/default/grub'
Generating grub configuration file ...
Found linux image: /boot/vmlinuz-4.15.0-55-generic
Found initrd image: /boot/initrd.img-4.15.0-55-generic
Found linux image: /boot/vmlinuz-4.15.0-54-generic
Found initrd image: /boot/initrd.img-4.15.0-54-generic
Found linux image: /boot/vmlinuz-4.15.0-52-generic
Found initrd image: /boot/initrd.img-4.15.0-52-generic
Found Windows Boot Manager on /dev/nvme0n1p1@/EFI/Microsoft/Boot/bootmgfw.efi
Adding boot menu entry for EFI firmware configuration
done
```
