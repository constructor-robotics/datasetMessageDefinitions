cmake_minimum_required(VERSION 3.3)
project(ping360_sonar_msgs)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS_RELEASE "-O3")
set(CATKIN_ENABLE_TESTING OFF)
## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
#find_package(ament_cmake_python REQUIRED)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(builtin_interfaces REQUIRED)

## Generate added messages and services with any dependencies listed here
rosidl_generate_interfaces( ping360_sonar_msgs
        "msg/SonarEcho.msg"
        DEPENDENCIES std_msgs
)



ament_export_dependencies(rosidl_default_runtime)

ament_package()

