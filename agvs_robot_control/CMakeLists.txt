cmake_minimum_required(VERSION 2.8.3)
project(agvs_robot_control)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  geometry_msgs
  robotnik_msgs
  roscpp
  sensor_msgs
  std_srvs
  std_msgs
  tf
  ackermann_msgs
)

catkin_package(
  CATKIN_DEPENDS 
     roscpp
     robotnik_msgs 
     sensor_msgs
     std_srvs 
     std_msgs
     tf
     ackermann_msgs
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

add_executable(agvs_robot_control src/agvs_robot_control.cpp)


add_dependencies(agvs_robot_control robotnik_msgs_generate_messages_cpp)


target_link_libraries(agvs_robot_control
   ${catkin_LIBRARIES}
)
