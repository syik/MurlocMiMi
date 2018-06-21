1. Debug will create new tab.
2. 断点 状态下 执行 `expression didReach = false` 或者编辑断点，以前就有的功能。 //Practise
3. Symbolic Breakpoint  `[UILabel setText:]` 截获系统的断点，以前也有的功能。 进入汇编代码，`po $arg1` 对象 `po (SEL)$arg2` 方法`po (SEL)$arg3` 具体的参数值//Practise
4. Action Debugger Command => `breakpoint set --one-shot true --name "-[UILabel setText:]"`
5. 在不改变当前执行条件的情况下使用普通断点 `expression self.valueLabel.txt = valueText`去纠正执行过程然后查看结果。 //Practise
6. 进入到某个断点后直接在lldb命令行中输入： `expression jumpAstronaut(animated: false)` 执行
7. 通过遵循 CustomDebugStringConvertible 协议来输出debug的po 内容。
8. 增加 Watchpoints
9. expression 后面的表达式就是实际的执行代码
10. po self.view.recurisveDescription()  doesn't work ==> expression -l objc -O -- [self.view recursiveDescription] doesn't work ==> expression -l objc -O -- [self.view recursiveDescription]  ==> expression -l objc -O -- [`self.view`recursiveDescription] 
11. 命令行alias: command alias poc expression -l objc -O --
poc 0x7f3a ==> 输出对象的实际内容，po 只能输出实际地址的整型值
12. 执行 expression CATransaction.flush() 可以不停的看到动画的执行过程的改变。
13. 导入自己的lldb py脚本： ~/.lldbinit 里面增加：`command script import ~/nudge.py` `command alias poc expression -l objc -O --` `command alias ☀️ expression -l objc -O -- (void)[CATransaction flush]`
14. po 实际只是 `expression --object-description -- <expression>` 只能打印值，或者显示 debug description
15. p  ==> expression -- <expression>
16. frame ==> 
17. Mac 下在查看 View 的视图结果界面，可以使用 po ((NSLayoutConstraint *)ox100111) 的方式输出约束， 实际也是进入了一个界面断点，可以通过右侧的界面断点的代码跳转到实际设置的地方，直接改代码。
18. Window 会以单独的方式切换出来，可以更方便调试。
19. CATransaction.flush() 依然可以更新视图，当expression 某一个值后就可以执行。
20. Creat backtraces in the inspector ==》Edit scheme 里面的logging Malloc stack （All Allocation and Free history)
21. 

### Crash logs
1. logs sources
2. 