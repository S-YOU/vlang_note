## 编译器

V的新版本把整个编译器的大部分代码从main模块移到vlib/compiler下

这样的目的在于其他模块就可以方便地引用compiler模块,来解析V源代码,重用编译器的功能,可以更快地开发各种开发工具,比如语法解析,IDE等

比如:

```
module main

import compiler

fn main() {
    args:=compiler.env_vflags_and_os_args() //调用compiler函数获取环境变量VFLAG和args
    println(args)
}
```



