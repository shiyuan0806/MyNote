## Ubuntu apt 获取资源的时候可能导致的问题

### 执行 `sudo apt install` 时提示 `/var/lib/dpkg/lock`

分析原因:

- 另一个程序正在运行，导致资源被锁不可用
- 导致资源被锁的原因可能是上次运行安装或更新没有正常完成，解决办法就是删掉

``` shell
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock
```

### Python cv2库 import 的问题

在 import cv2 时报错

``` text
ImportError: libgthread-2.0.so.0: cannot open shared object file: No such file or directory
```

解决：

``` shell
!apt-get update
!apt-get -y upgrade
!pip install opencv-python
!apt-get install libgtk2.0-dev -y
```