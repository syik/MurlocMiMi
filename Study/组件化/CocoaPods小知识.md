### 出现Argument List too long的原因
由于某一个组件里面的 podspec 里面出现了如下配置：
![20180629153027944127294.png](http://p88xz0cfk.bkt.clouddn.com/20180629153027944127294.png)
因为这个是一个集合操作，会把所有组件的设置最终写入到 pods-debug.xcconfig 里面，
![20180629153027967156695.png](http://p88xz0cfk.bkt.clouddn.com/20180629153027967156695.png)
而这个配置一旦到主工程，就会产生一个递归操作，导致出现拼接 search 路径过长的问题。

