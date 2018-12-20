##  :8ball:MVC 发布时注意的事项 ##

### :closed_umbrella: roslyn处理  ###
当前版本的Mono 的编译器还是Mono的mcs编译器，并没有完成到roslyn 这个编译器的升级工作，这个工作正在进行过程中，在不远的将来就可以统一使用roslyn。解决这个问题的方法就是用Mono的mcs编译器，项目上右键管理NuGet程序包，打开管理器，按顺序卸载以下两个组件：

* Microsoft.CodeDom.Providers.DotNetCompilerPlatform

* Microsoft.Net.Compilers

图示如下

* 右击击项目找到管理NuGet程序包
![](https://github.com/Lumnca/Jexus/blob/master/Imgs/a1.png)

* 删除已安装的上面两个包

![](https://github.com/Lumnca/Jexus/blob/master/Imgs/a2.png)

### :closed_umbrella: 发布为文件系统 ###
