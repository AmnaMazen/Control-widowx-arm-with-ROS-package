# Control-widowx-arm-with-ROS-package

This tutorial shows how to control different joints of widowx arm using ROS package


# 1- Create new package

* Go to the source folder inside "widowx" workspace 

$ cd ~/widowx/src

* use the command catkin_create_pkg <package-name> <dependencies> to create a new package
  
$ catkin_create_pkg widowx_arm_testing std_msgs roscpp arbotix_python
  
* Paste "widowx_arm_testing.cpp" into the src folder of "widowx_arm_testing package
  
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
  
