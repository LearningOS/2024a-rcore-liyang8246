### 简答题

- 1 正确进入 U 态后，程序的特征还应有：使用 S 态特权指令，访问 S 态寄存器后会报错。 请同学们可以自行测试这些内容 (运行 三个 bad 测例 (ch2b_bad_*.rs)) 描述程序出错行为，同时注意注明你使用的 sbi 及其版本。
  
- 2
    深入理解 trap.S 中两个函数 __alltraps 和 __restore 的作用，并回答如下问题:
    - 2.1
        从 Trap 中返回,从线程切换中返回
    - 2.2
        使用了 sstatus, sepc 和 sscratch 寄存器
        sstatus 寄存器用于设置特权级状态
        sepc 寄存器用于恢复之前线程 pc
        sscratch 寄存器用于恢复之前线程的栈指针
    - 2.3
        因为 sp 就是 x2 其实已经处理过了
        x4 不知道
    - 2.4
        sp 用户栈 sscratch 内核栈
    - 2.5
        L46 `csrw sstatus, t0`
    - 2.6
        sscratch 用户栈 sp 内核栈
    - 2.7
        Tarp发生时由硬件切换至S态