# 性能优化
``` ###
至于哪些方面需要优化，一方面是算法的效率还要就是现象，例如CPU特别高那么看看goruntine的调度，哪个函数占用比高，是不是存在死循环；  
内存大，看看是不是有大的内存分配没有及时回收，或者是不是有频繁的内存分配，是不是有内存泄露？
响应慢是卡在哪里，是执行效率还是和组件通信等等。
```

{雨痕10篇性能优化文章}[https://segmentfault.com/blog/qyuhen]

- 小对象合并成结构体一次分配，减少内存分配次数
```
var a int 
var b string

type param struct{
   a int
   b string
}
```
-  缓存区内容一次分配足够大小空间，并适当复用
```

```

## 个人总结

- map，array 预分配内存（防止申请堆内存分配，直接从栈内的申请）
- string 字符串使用 （bytes.buffer  预分配足够大内存）
- defer 读取文件或者数据库，关闭连接
- pprof 观察cpu使用率，trace 内存使用情况（优化工具）
- chan leak 协程阻塞，内存泄漏
