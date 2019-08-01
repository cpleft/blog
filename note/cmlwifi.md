# linux命令行连接wifi

需要的工具：
nmcli

查看机器的网络设备：
```
$ nmcli dev
```
查看附近的wifi：
```
$ nmcli dev wifi
```
第一次连接wifi：
```
$ nmcli dev wifi connect `SSID` password `password`
```
连接以往的wifi：
```
$ nmcli con up `SSID`
```
