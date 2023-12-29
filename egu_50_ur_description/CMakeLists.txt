cmake_minimum_required(VERSION 2.8.3)
project(egu_50_ur_description)


find_package(catkin REQUIRED COMPONENTS
egu_50_description


ur_description 
)

catkin_package(
) 


include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)
  