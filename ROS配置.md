#**配置ROC**

##**实验2  姓名:洪哲铮 学号:14353085 班级:14M1**  

#ROS具体的配置步骤


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

#cartographer具体的配置步骤（依次执行给出的语句）


<font size=5>步骤1.安装所有依赖项</font><br>

	sudo apt-get install -y google-mock libboost-all-dev  libeigen3-dev libgflags-dev libgoogle-glog-dev liblua5.2-dev libprotobuf-dev  libsuitesparse-dev libwebp-dev ninja-build protobuf-compiler python-sphinx  ros-indigo-tf2-eigen libatlas-base-dev libsuitesparse-dev liblapack-dev

<font size=5>步骤2.安装ceres solver</font><br>

	git clone https://github.com/hitcm/ceres-solver-1.11.0.git

	cd ceres-solver-1.11.0/build

	cmake ..

	make 

	sudo make install

<font size=5>步骤3.安装 cartographer</font><br>

	git clone https://github.com/hitcm/cartographer.git
	
	cd cartographer/build

	cmake .. -G Ninja

	ninja

	ninja test

	sudo ninja install

<font size=5>步骤4.安装cartographer_ros</font><br>

	mkdir catkin_ws

	cd catkin_ws

	mkdir src

	cd src

	sudo git clone https://github.com/hitcm/cartographer_ros.git

	catkin_make

<font size=5>步骤5.数据下载测试</font><br>

	roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag

<font size=5>步骤1.建立sources.list</font><br>

##配置过程截图（仅截取部分）：

![image](https://cl.ly/180B110V1Q0i/ROS.png)

##cartographer数据下载测试结果

![image](https://cl.ly/1q2Z3R183H34/cartographer.png)

##过程中遇到的问题：

在执行测试样例的时候，出现了博客上给出的问题：“[demo_backpack_2d.launch] is neither a launch file in package [cartographer_ros] nor is [cartographer_ros] a launch file name 
The traceback for the exception was written to the log file”

解决方法：执行以下语句

	source ~/catkin_ws/devel/setup.bash

	rospack profile