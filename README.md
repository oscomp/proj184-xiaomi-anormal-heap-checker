# proj184-xiaomi-anormal-heap-checker

## Heap 异常检测工具

### 支持单位 （可选内容）

小米移动

### 项目描述

Heap异常是指HeapBufferleak、HeapBufferOverflow、UseAfterFree、DoubleFree等内存异常问题， Asan、heapTrack、Valgrind等内存检测工具虽然很强大， 但是这些工具共同的缺陷就是占用资源太多，只有在怀疑有以上问题之后才建议使用。本项目的目的是开发一个能够检测Heap异常的轻量型工具，这个工具占用的资源很少，可以一直在开发版本甚至是release版本里使用，在出现Heap异常问题之后能够预警，尽量保存准确的异常信息如：调用栈、内存地址与大小、当前的运行的进程名称。

### 所属赛道

2022全国大学生操作系统比赛的“OS功能挑战”赛道

### 参赛要求

• 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生或研究生（2022年春季学期或之后毕业的大一~大四的本科生或研究生）

• 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖

• 请遵循“2022全国大学生操作系统比赛”的章程和技术方案要求

### 项目导师

• 杨冬东：yangdongdong@xiaomi.com

• 赵小冰：zhaoxiaobing@xiaomi.com

### 难度

中等

### 特征

1. 建议使用c/c++/rust语言,运行环境可选择任一linux发行版

2. 低性能开销、低内存消耗，稳定性高

3. 可运行在arm/arm64/x86架构上

4. 可准确记录调用栈、内存大小、内存地址、当前的进程名称

### 文档

1. 参考linux kfence : https://docs.kernel.org/dev-tools/kfence.html

2. linux kernel:https://kernel.org/

### License

• GPLv2 (https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)

### 预期目标

注：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标

#### 第一题

实现UseAfterFree、HeapBufferOverflow、DoubleFree的捕获，可参考linux 内核里kfence的实现，捕获到异常信息尽量准确， 消耗较少的资源，能够在开发或是release版本里一直使用。异常信息包含的内容参考特征4.

#### 第二题

实现在适当的时机触发对HeapBufferleak检测，查阅相关资料，尽量准确的总结内存泄露特征，对每种特征加权，权值大于某个阈值意味着该内存泄露的概率较高，对泄露概率较高的内存输出预警信息，预警信息包含的内容参考特征4。特征及其权值最好能够简单的配置，可由应用场景来进行不同的组合。

#### 第三题

输出设计文档与参考code
