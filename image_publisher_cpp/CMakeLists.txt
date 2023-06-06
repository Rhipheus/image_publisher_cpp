cmake_minimum_required(VERSION 3.5)
project(image_publisher_cpp)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(cv_bridge REQUIRED)
find_package(OpenCV REQUIRED)

add_executable(image_publisher src/image_publisher_script.cpp)
ament_target_dependencies(image_publisher rclcpp std_msgs sensor_msgs cv_bridge OpenCV)

ament_package()

install(TARGETS
  image_publisher
   DESTINATION lib/${PROJECT_NAME}
 )