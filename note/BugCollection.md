# Bug Collection
> This page is to collect bugs I encountered.

---
### for 循环中的条件结束判断
```cpp
for (int i = 0; i <= 5 && vis[i] == false; ++i)
```
这个 for 循环的本意是在循环的过程中判断 vis[i] 是否是 false，
如果是 false 才可以进入循环体，如果不是 false 就进行下一次循环(continue)。

但事与愿违，这种写法的真正执行流是在循环的执行过程中 **只要有一次遇到
vis[i] 不是 false，就会直接退出循环(break)** ，而不是像期望的那样进入
下次循环。

所以它应该这样写
```cpp
for (int i = 0; i <= 5; ++i)
    if (vis[i] == false)
```

### c++ . 操作符
在一次代码中
```cpp
    while (head < tail) {
        for (int i = 0; i < queue[head].length(); ++i) {
            string s = queue[head].erase(i);
            // ...
                if (queue[k] == s)
```
我的想法是把 `queue[head]` erase 之后赋值给 s，但是 `.erase()` 的操作
实际上作用于 `queue[head]` 本身。 这个时候 queue[k] 和 s 一定是相等的。

正确的写法应当将它们分开：
```cpp
    while (head < tail) {
        for (int i = 0; i < queue[head].length(); ++i) {
            string s = queue[head];
            s = s.erase(i);
```
