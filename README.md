#**嵌入式系统实验报告**

##**实验1  姓名:洪哲铮 学号:14353085 班级:14M1**  
<br/>
##一、DOL 框架描述（Description）
####通过实验分布式操作层（DOL）是一个框架，基本上由三部分组成：
###1.应用程序编程
DOL定义了一组计算和通信程序，使对形状分布平台，并行应用程序的编程。使用这些程序，应用程序员可以编写程序，而无需了解底层架构的详细知识。事实上，这些程序都受限于硬件相关的软件（HDS）层进一步完善。
###2.仿真功能
提供程序员可能性测试其应用程序，功能仿真框架已经形成。除了应用功能验证，这个框架是用来在应用程序级获得的性能参数。
###3.映射优化
DOL映射优化的目标是计算一组应用程序的最佳映射到形状架构平台。在第一步骤中，基于XML规范格式已定义允许以描述一个抽象级别的应用程序和体系结构。尽管如此，所有必要的，以获得准确的性能估计包含信息。
<br/>
<br/>
##二、DOL安装笔记（How to Install）
1.实验环境

主机系统为window8 64位专业版 所用虚拟机软件为VMware Workstation pro


2.配置环境过程中的文件解压和下载

    sudo apt-get update

![image](https://cl.ly/0E132Q0b241a/AZ1.png)

	sudo apt-get install ant

![image](https://cl.ly/41220E47161r/AZ2.png)

    sudo apt-get install openjdk-7-jdk

![image](https://cl.ly/1v3M1U191S16/AZ3.png)

	sudo apt-get install unzip

![image](https://cl.ly/2E2Z3O023s0k/AZ4.png)

    sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz

![image](https://cl.ly/0g0K1g3W3H1O/D1.png)

    sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip

![image](https://cl.ly/0w2m2H3c2n3b/D2.png)

解压systemc：

    tar -zxvf systemc-2.3.1.tgz

![image](https://cl.ly/1U0c2h0u0C0h/JYSM.png)
3.编译systemc

进入systemc-2.3.1的目录下

    cd systemc-2.3.1

新建一个文件夹objdir

    mkdir objdir

进入文件夹objdir

    cd objdir

运行configure

    ../configure CXX=g++ --disable-async-updates

运行之后如下图

![image](https://cl.ly/3o2M281T161f/BYSM.png)

编译

    sudo make install


4.编译dol

进入dol文件夹

    cd ../dol

修改build_zip.xml文件，由于系统为64位，所以将lib-linux改成lib-linux64

编译

    ant -f build_zip.xml all

编译成功，结果如下图

![image](https://cl.ly/2v2K1E1t0C1w/BYDOL.png)

试运行第一个例子

进入build/bin/mian路径下

    cd build/bin/main
	ant -f runexample.xml -Dnumber=1

运行成功，结果如下图

![image](https://cl.ly/3P321H022N2v/1.png)
<br/>
<br/>
##三、实验心得（Experimental experience）
这次实验的目的是让我们完成dol的配置，在上学期操作系统的学习过程中，我们已经接触过了VMware Ubuntu虚拟机，对其中的一些操作还是比较熟悉的，具体的操作步骤只要按照ppt中给出的具体代码按部就班地操作就可以了，难度并不是很大。个人遇到的问题是，在成功编译dol以后，不能成功地运行第一个例子。在尝试了Q&A中所有的解决办法以后，仍然没有能够解决。只好重新回顾整个配置过程，看看自己有没有什么疏漏。后来发现是在修改build_zip.xml文件的时候，系统为64位，却没有把lib-linux改成lib-linux64，导致没有办法成功运行样例。在这种地方浪费了很多时间去debug实在是很不值，今后的实验中要更加细致地阅读ppt，不漏过任何一个细节，这样才能高效地完成实验。此外还遇到的一个问题是C compiler cannot create executables，需要在终端里面执行 sudo apt-get install build-essential来解决编译环境的问题。
执行结果如下：
![image](https://cl.ly/3o370m1e1M3R/Q.png)
