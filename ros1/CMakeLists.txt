cmake_minimum_required(VERSION 3.5)
project(rslidar_msg)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(std_msgs REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  sensor_msgs
  message_generation
  )

add_message_files(FILES
  RslidarPacket.msg
  )

generate_messages(DEPENDENCIES 
  std_msgs
  sensor_msgs
  )

catkin_package(CATKIN_DEPENDS 
  std_msgs 
  sensor_msgs
  message_runtime
  )
