# rename 的使用
## 去掉开头部分
```
Round570div3-A_Nearest_Interesting_Number.cpp
Round570div3-B_Equalize_Prices.cpp
Round570div3-C_Computer_Game.cpp
Round570div3-D_CandyBox_EasyVersion.cpp
Round570div3-E_Subsequences_EasyVersion.cpp
```

```
$ rename 's/Round570div3\-//' *
```
rename 有两个参数，第一个是正则表达式，第二个是要修改的文件。
