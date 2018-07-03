
### big map
![20180703153062163738947.png](http://p88xz0cfk.bkt.clouddn.com/20180703153062163738947.png)

### New debug in Xcode10 => Debug can create new tab.
![20180703153060194263071.png](http://p88xz0cfk.bkt.clouddn.com/20180703153060194263071.png)

### express
* 可以在断点后： expression testLLDB = true
* 编辑断点
![20180703153060359959059.png](http://p88xz0cfk.bkt.clouddn.com/20180703153060359959059.png)
* 打印具体的地址内容
`command alias poc expression -l objc -O --`
expression -l objc -O -- [`self.view` recursiveDescription]  #可以在 Swift 中打印当前 View 的层级
expression -l objc -O -- 0x7fbdcc511950 #可以打印对象的内容，而po只能打
* 断点过程中去调试动画，使用先更改某个值，然后再 expression CATransaction.flush() 会很有用。

### Symbolic Breakpoint
![20180703153060403089329.png](http://p88xz0cfk.bkt.clouddn.com/20180703153060403089329.png)
断点到系统的方法断点，汇编代码，但是可以通过 `po $arg1` 对象 `po (SEL)$arg2` 方法`po $arg3` 具体的参数值 
在LLDB的过程中，可以手动通过 `breakpoint set --one-shot true --name "-[UILabel setText:]"` 来增加一个断点
thread jump –by 1 可以跳过一行

### Enter breakpoint in lldb
breakpoint set --one-shot true --name "-[UILabel setText:]"

### po & p
po ==> `expression --object-description -- <expression>` <--O> 是等价于 Debug description 描述的，也就是遵循 CustomDebugStringConvertible 后输出的内容
p  ==> expression -- <expression>  <-->

### Debug view inspector
![20180703153061050785330.png](http://p88xz0cfk.bkt.clouddn.com/20180703153061050785330.png)
![20180703153061052245885.png](http://p88xz0cfk.bkt.clouddn.com/20180703153061052245885.png)


## Write the full crashlog into file
bugreport unwind --outfile /Users/wanliming/Desktop/buglog.txt
bugreport unwind --append-outfile /Users/wanliming/Desktop/buglog.txt

### 需要写入到系统配置表里面的内容
### TODO: nudge 的使用， 内容加入到全局自动控制配置表里面
~/.lldbinit 里面增加：`command script import ~/nudge.py` `command alias poc expression -l objc -O --` `command alias ☀️ expression -l objc -O -- (void)[CATransaction flush]`


### Crash logs
1. logs sources
2. 视频结合了几个实际中的例子来重现问题以及解决问题。