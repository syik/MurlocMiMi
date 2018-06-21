记录日常在 Mac 系统下的一些小知识点

### 更改 Mac 文件夹的图标背景
1. 打开一张图片，Ctrl + C 圈中一段区域选择需要加入的图片。
2. 选择一个文件夹，CMD + i 查看简介，然后选中左上角的图标，使用 Ctrl + V 粘贴进去即可。

### Mac 制作启动盘的命令
`sudo / Applications / Install \ macOS \ 10.14 \ Beta.app/Contents/Resources/createinstallmedia --volume / Volumes / Untitled`

### Mac 清理磁盘空间的地方
由于 Xcode 和 AppCode 产生的中间文件很大，所以主要清理这两个文件夹的内容
`/Users/wanliming/Library/Caches`
`/Users/wanliming/Library/Developer`
`/Users/wanliming/Library/Developer/Xcode/DerivedData`
`/Users/wanliming/Library/Developer/Xcode/iOS\ DeviceSupport`里面的模拟器

