<table>
  <tr>
    <td>Language</td>
    <td><a href="http://rpiwin10.github.io">English</a></td>
    <td><a href="http://rpiwin10.github.io/zh_CN">简体中文</a></td>
  </tr>
</table>

<table>
  <tr>
    <th>语言：</th>
    <th>32GB</th>
    <th>16GB</th>
  </tr>
  <tr>
    <td>简体中文</td>
    <td><a href="https://pan.baidu.com/s/1O2q_mIRweJAYg-bUF0diCw">0.2</a>  |  <a href="https://pan.baidu.com/s/1A-hUnv2prE8PVZMf4MGIEw">0.3</a>|<a href="https://raw.githubusercontent.com/RpiWin10/zh_CN/master/0.4.html">0.4</a> </td>
    <td><a href="https://pan.baidu.com/s/1mg3mCQY2_0O6tg1-u4btTA">0.3</a>|<a href="https://raw.githubusercontent.com/RpiWin10/zh_CN/master/0.4.html">0.4</a></td>
  </tr>
</table>



<hr>
# 与我们讨论
<hr>
Discord:[https://discord.gg/gv2xEmN](https://discord.gg/gv2xEmN)<br>
QQ 群:784419839
<hr>

## 更新驱动
<hr>

```
git clone https://github.com/RpiWin10/Drivers.git 
dism /image:[WindowsPath] /add-driver /driver:[driverPath] /forceunsigned
```
假设E: 是你的SD卡上的Windows盘符C:\Users\gloom\Downloads\rpi是你下载的驱动位置
```
dism /image:E: /add-driver /driver:C:\Users\gloom\Downloads\rpi /forceunsigned
```

<hr>
## 安装视频：

player.bilibili.com/player.html?aid=23793454&cid=39781297&page=1

这里是所需要的命令
```
dism /mount-image /imagefile:install.wim /Index:1 /MountDir:m
dism /image:m /add-driver /driver:system32 /recurse /forceunsigned
dism /unmount-wim /mountdir:m /commit
dism /apply-image /imagefile:install.wim /index:1 /applydir:F:\
bcdboot F:\Windows /s E: /f UEFI
bcdedit /store E:\EFI\Microsoft\Boot\bcd /set {default} testsigning on
bcdedit /store E:\EFI\Microsoft\Boot\bcd /set {default} nointegritychecks on
```

非常感谢:
- [USB 驱动](https://github.com/nta/dwusb)
- [iot移植版本驱动](https://github.com/ms-iot/bsp)
- UEFI 启动器: http://github.com/andreiw/RaspberryPiPkg


