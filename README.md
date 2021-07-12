# Control-widowx-arm-with-ROS-package

Author name: Amna Mazen Ali

I uploded a video about step by step tutorial on Youtube: https://www.youtube.com/watch?v=32R-RxS9qWE&t=6s

This tutorial shows how to control different joints of widowx arm using ROS package. I used this reference with some modifications: https://www.researchgate.net/publication/291789058_Turtlebot_2_with_a_WidowX_arm_first_steps


# 1- Create new package

* Go to the source folder inside "widowx" workspace 

$ cd ~/widowx/src

* use the command catkin_create_pkg <package-name> <dependencies> to create a new package
  
$ catkin_create_pkg widowx_arm_testing std_msgs roscpp arbotix_python
  
* Paste "widowx_arm_testing.cpp" into the src folder of "widowx_arm_testing package. This c++ program gives +ve, -ve and zero commands to each joint in widowx- arm 
  and then relax all the joints.
  
# 2- Modify "CMakeList.txt" 
  
add_executable(widowx_arm_testing src/widowx_arm_testing.cpp)
  
target_link_libraries(widowx_arm_testing ${catkin_LIBRARIES})
  
# 3- Compile 
  
 $ cd ~/widowx
  
 $ catkin_make
  
 $ source ./devel/setup.bash
  
# 4- Let's run the program
  
  $ rosrun widowx_arm_testing widowx_arm_testing
  
  * You should running the controller first
  
  $ roslaunch widowx_arm_controller widowx_arm_controller.launch
  
