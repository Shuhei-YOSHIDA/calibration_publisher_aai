cmake_minimum_required(VERSION 2.8.3)
project(calibration_publisher_aai)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  geometry_msgs
  image_transport
  roscpp
  sensor_msgs
  std_msgs
  tf2
  tf2_geometry_msgs
  tf2_ros
)

find_package(OpenCV REQUIRED)

catkin_package()

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${OpenCV_INCLUDE_DIRS}
)

add_executable(calibration_publisher
  src/calibration_publisher.cpp
)

add_dependencies(calibration_publisher
  ${catkin_EXPORTED_TARGETS}
)

target_link_libraries(calibration_publisher
  ${catkin_LIBRARIES}
)

#install(TARGETS calibration_publisher
  #ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  #LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  #RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
#)
