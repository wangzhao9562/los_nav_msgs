cmake_minimum_required(VERSION 2.8.3)
project(los_nav_msgs)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  actionlib_msgs
  geometry_msgs
  message_generation
  roscpp
  rospy
  std_msgs
)

add_message_files(
  DIRECTORY msg
  FILES
    Mission.msg
    CommonCircle.msg
    CommonLine.msg
)

add_action_files(
  DIRECTORY action
  FILES
    LosNav.action
)

generate_messages(
  DEPENDENCIES
    actionlib_msgs
    std_msgs
    geometry_msgs
)

catkin_package()
