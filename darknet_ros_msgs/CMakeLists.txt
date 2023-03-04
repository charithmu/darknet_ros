cmake_minimum_required(VERSION 3.5.1)

project(darknet_ros_msgs)

# Set c++11 cmake flags
set(CMAKE_CXX_STANDARD 11)

find_package(catkin REQUIRED
  COMPONENTS
    actionlib_msgs
    geometry_msgs
    sensor_msgs
    std_msgs
    message_generation
)

add_message_files(
  FILES
    BoundingBox.msg
    BoundingBoxes.msg
    ObjectCount.msg
)

add_action_files(
  FILES
    CheckForObjects.action
)

generate_messages(
  DEPENDENCIES
    actionlib_msgs
    geometry_msgs
    sensor_msgs
    std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    actionlib_msgs
    geometry_msgs
    sensor_msgs
    message_runtime
    std_msgs
)
