# linux 下压缩和解压文件
在 linux 系统下我们经常要解压各种压缩文件，或者压缩文件到各种不同的格式。
常见的打包或压缩文件的格式有这些：
- .tar
- .gz
- .tar.gz
- .bz
- .tar.bz
- .bz2
- .tar.bz2
- .zip
- .rar

一组文件被用 `tar` **打成包**以后生成 `.tar` 文件，它并没有被压缩，只是被
打成了一个包，或者叫 Archive。

比如将两个文件 a.txt b.txt 打到一个包 X.tar 里：
```
tar cf X.tar a.txt b.txt
```
tar 是 shell 命令，用于将文件打包，后面的 `cf` 是选项，`c` 表示打包，`f` 
指定包文件的名字。

在打包的同时进行压缩，就形成了 `.tar.gz`，`.tar.bz` 等文件，`gz` 是表示
以 `gzip` 为压缩方式，`bz` 是以 `bzip` 为压缩方式。

## 对不同压缩格式的压缩方法
### .tar
- 打包
```
tar cvf X.tar file1 file2 directory1 directory2
```
- 解包
```
tar xvf X.tar
```

### .gz
- 压缩
```
gzip file1
```
- 解压
```
gzip -d X.gz
```

### .tar.gz
- 压缩
```
tar zcvf X.tar.gz file1 file2 directory1 directory2
```
- 解压
```
tar zxvf X.tar.gz
```

### .tar.xz
- 解压
```
tar Jxvf X.tar.xz
```

### .tar.bz2
- 解压
```
tar jxvf X.tar.bz2
```

### .tar.Z
- 解压
```
tar Zxvf X.tar.Z
```

### .zip
- 压缩
```
zip X.zip file1 file2 directory1 directory2
```
- 解压
```
unzip X.zip
```

### .rar
- 压缩
```
rar a X.rar file1 file2 directory1 directory2
```
- 解压
```
rar x X.rar
```

## 遇到的一些问题
- stdin: unexpected end of file (EOF)  
通常是压缩文件不完整，需要重新下载。
