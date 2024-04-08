cmake_minimum_required(VERSION 2.8.3)
project(pzn_plus_description)
add_compile_options(-std=c++14)

find_package(gazebo REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  rospy
  gazebo_ros
)

catkin_package(
CATKIN_DEPENDS rospy gazebo_ros 
)


include_directories( 
# include
  ${catkin_INCLUDE_DIRS} 
  ${GAZEBO_INCLUDE_DIRS}
) 
           