cmake_minimum_required(VERSION 3.3)
project(micron_driver_ros)
#set(CMAKE_CXX_FLAGS "-std=c++0x ${CMAKE_CXX_FLAGS}")
#set(CMAKE_CXX_STANDARD 20)
#set(CMAKE_CXX_STANDARD_REQUIRED ON)
#set(CMAKE_CXX_FLAGS_RELEASE "-O3")
#set(CATKIN_ENABLE_TESTING OFF)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(ament_cmake REQUIRED)
#find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

#find_package(OpenCV REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
#find_package(cv_bridge REQUIRED)
## System dependencies are found with CMake's conventions
#find_package(Boost REQUIRED COMPONENTS thread)



rosidl_generate_interfaces( ${PROJECT_NAME}
        "msg/IntensityBin.msg"
        "msg/ScanLine.msg"
        DEPENDENCIES builtin_interfaces
        DEPENDENCIES std_msgs
        DEPENDENCIES geometry_msgs
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()



