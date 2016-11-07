#**DOL实例分析&编程**

##**实验2  姓名:洪哲铮 学号:14353085 班级:14M1**  
<br/>
#一、修改之后的截图

###1.Example1 输出结果

![image](https://cl.ly/410K1Q271L07/ex2.png)

###2.Example2 输出结果

![image](https://cl.ly/3C0B0D0U070K/ex1.png)

#二、具体的修改步骤

#对example1的修改：

<font size=5>步骤1.打开dol/build/bin/main/example/文件下的square.c文件；</font><br>

<font size=5>步骤2.找到其中定义平方进程的部分，把i*i修改成i*i*i从而实现三次方进程；</font><br>

<font size=5>步骤3.重新编译运行example1，对比得到的结果与之前的结果；</font><br>

#对example2的修改

<font size=5>步骤1.打开dol/examples/example2/目录下的example2.xml文件；</font><br>

<font size=5>步骤2.找到其中的iterator定义的部分；</font><br>

<font size=5>步骤3.将下列代码中的N值修改为2，让square模块由3个变成2个；</font><br>

	<variable value=“3” name = "N"/>

<font size=5>步骤4.重新编译运行example2，对比得到的结果与之前的结果；</font><br>

##三、实验感想

<font size=5>之前的实验侧重于文件的配置，对于文件内部的内容没有太多的涉及。而通过本次实验，我们对文件的内容有了一些初步的了解：
src文件夹里面包含2中类型的文件，后缀名分别是*.c和*.h，其中.h文件主要用来声明，而.c文件则是包含了功能实现的模块，
所以如果我们要对功能进行修改（譬如本次实验中的example1），我们就可以在.c文件中修改模块来实现。除了这两个文件以外，还有xml文件也是很重要的一个文件，它定义了模块与模块之间的连接关系，可以通过迭代的方法来重复调用模块的功能，（譬如
这次实验里面的example2）。通过这次实验，虽然修改的东西不是很多，但是通过这几步操作我们理解了上述文件的具体组成，和
各自的功能。对于各种文件类型也算是有了一个初步的了解，今后还要在实验的过程中更注重细节。学到更多东西。</font>


