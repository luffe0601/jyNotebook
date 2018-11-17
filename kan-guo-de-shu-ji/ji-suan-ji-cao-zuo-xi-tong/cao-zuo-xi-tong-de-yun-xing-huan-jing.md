### 运行机制

* 指令
  * 特权指令
    * 如:内存清零指令，不允许用户程序使用
  * 非特权指令
    * 如:普通的运算指令

```
cpu如何判断当前是否可以执行特权指令
```

* 处理器状态:用程序状态寄存器\(PSW\)中的某标志位来标识当前处理器处于什么状态，如0为用户态，1为核心态
  * 用户态\(目态\)&gt;此时cpu只能执行非特权指令
  * 核心态\(管态\)&gt;特权指令、非特权指令都可以执行
* 程序
  * 内核程序
    * 操作系统的内核程序是系统的管理者，即可以执行特权指令，也可以执行非特权指令，运行在核心态
  * 应用程序
    * 为了保证系统能安全运行，普通应用程序只能执行非特权指令，运行在用户态

![](/assets/js-14.3.3-1.png)

![](/assets/js-14.3.3-3.png)

* 内核是计算机上配置的底层软件，是操作系统最基本、最核心的部分
* 实现操作系统内核功能的那些程序就是内核程序
* 操作系统内核 - 与硬件关系较紧密的模块

  * 时钟管理
    * 实现计时功能
  * 中断处理
    * 负责实现中断机制
  * 原语
    * 是一种特殊的程序
    * 处于操作系统最底层、最接近硬件的部分
    * 这种程序的运行具有原子性 -- 其运行只能一气呵成，不可中断
    * 运行时间较短，调用频繁
  * 对系统资源进行管理的功能 -- 有的操作系统不把这部分能归为"内核功能"。也就是说，不同的操作系统，把内核公的划分可能并不一样
    * 进程管理
    * 存储器管理
    * 设备管理

* 操作系统的体系结构:大内核和微内核

  * 大内核:将操作系统的主要模块都作为系统内核，运行在核心态
    * 优点:高性能
    * 缺点:内核代码庞大，结构混乱，难以维护
  * 微内核:只把最基本的功能保留在内核
    * 优点:内核功能少，结构清晰，方便维护
    * 缺点:需要频繁地在和心态和用户态之间切换，性能低



![](/assets/js-14.3.3-4.png)
