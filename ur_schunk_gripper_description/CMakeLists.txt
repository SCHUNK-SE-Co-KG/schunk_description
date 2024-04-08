cmake_minimum_required(VERSION 2.8.3)
project(ur_schunk_gripper_description)


find_package(catkin REQUIRED COMPONENTS
  egu_description
  pzv_64_description
  pzn_plus_description
  egp_description
  ur_description 
)

catkin_package(
) 


include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)
  