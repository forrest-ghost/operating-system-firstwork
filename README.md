# operating-system
通过管道方式实现进程间通信
问题描述：
> 设有二元函数 f(x,y) = f(x) + f(y) 其中： 
> f(x) = f(x-1) * x (x >1) f(x)=1 (x=1) 
> f(y) = f(y-1) + f(y-2) (y> 2) f(y)=1 (y=1,2) 
> 请编程建立 3 个并发协作进程，它们分别完成 f(x,y)、f(x)、f(y)
## 实验目的
通过 Linux 系统中管道通信机制，加深对于进程通信概念的理解，观察和体验 并发进程间的通信和协作的效果 ，练习利用无名管道进行进程通信的编程和调试 技术。
## 代码理解
思路：父进程是函数F_xy=F_x+F_y,第一个子进程第一层fork()负责计算F_y,并与父进程F_xy通信;
 在fork>0时，即F_xy进程的内部再fork(),再创建一个子进程F_x；
F_xy将参数x和y分别传递给F_x,F_y,进程F_x,F_y计算出函数结果后将结果传递给F_xy,再输出到屏幕上。
## 程序截图
![运行截图](https://github.com/forrest-ghost/image-folder/blob/main/second_os_workonmachine.png)
