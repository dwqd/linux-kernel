#### **ARM指令中多数据传输共有两种:**

https://www.cnblogs.com/lifexy/p/7363208.html 原帖地址



**LDM:**(load much)多数据加载,将地址上的值加载到寄存器上

**STM:**(store much)多数据存储,将寄存器的值存到地址上

主要用途：现场保护、数据复制、参数传送等，共有8种模式（前面4种用于数据块的传输，后面4种是堆栈操作）如下：

（1）**IA:**（Increase After） 每次传送后地址加4,其中的寄存器**从左到右执行**,例如:STMIA R0,{R1,LR} 先存R1,再存LR

（2）**IB:**（Increase Before）每次传送前地址加4,同上

（3）**DA:**（Decrease After）每次传送后地址减4,其中的寄存器**从右到左执行**,例如:STMDA R0,{R1,LR} 先存LR,再存R1

（4）**DB：**（Decrease Before）每次传送前地址减4,同上

（5）**FD:** 满递减堆栈 (每次传送前地址减4)

（6）**FA:** 满递增堆栈 (每次传送后地址减4)

（7）**ED:** 空递减堆栈 (每次传送前地址加4)

（8）**EA:** 空递增堆栈 (每次传送后地址加4)

注意：其中在数据块的传输中是STMMDB和LDMIA对应，STMMIA和LDMDB对应

而在堆栈操作是STMFD和LDMFD对应，STMFA和LDMFA对应

**格式:**

LDM{cond} mode Rn{!}, reglist{^}

STM{cond} mode Rn{!}, reglist{^}

**其中**

 Rn：基址寄存器，装有传送数据的起始地址，Rn不允许为R15；

 ！：表示最后的地址写回到Rn中；

 reglist：可包含多于一个寄存器范围，用“，”隔开，如{R1，R2，R6-R9}，寄存器由小到大顺序排列；

 ^：不允许在用户模式和系统模式下运行