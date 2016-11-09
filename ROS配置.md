#**配置ROC**

##**实验2  姓名:洪哲铮 学号:14353085 班级:14M1**  

#具体的配置步骤


<font size=5>步骤1.建立sources.list</font><br>
	
	sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

<font size=5>步骤2.建立keys</font><br>
	
	sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116

<font size=5>步骤3.更新Debian包索引</font><br>

	sudo apt-get update

<font size=5>步骤4.安装所有的ROS包</font><br>

	sudo apt-get install ros-jade-desktop-full

<font size=5>步骤5.初始化rosdep并更新</font><br>

	sudo rosdep init
    rosdep update

<font size=5>步骤6.配置环境</font><br>

	echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
    source ~/.bashrc

<font size=5>步骤7.安装rosinstall</font><br>

	sudo apt-get install python-rosinstall

##配置过程截图（仅截取部分）：

![image](https://cl.ly/180B110V1Q0i/ROS.png)

