# linux格式化U盘

首先确保U盘没有挂载，如果挂载了，就卸载它：

查看磁盘分区：

```bash
# fdisk -l
```

卸载U盘：

```bash
# umount /dev/sda
```

格式化成 fat 格式：

```
# mkfs.vfat -F 32 /dev/sda
```

如果有一个磁盘有多个分区，就一一格式化，最后对总体再格式化。
