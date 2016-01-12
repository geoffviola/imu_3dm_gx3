cmake_minimum_required(VERSION 2.8.3)
project(imu_3dm_gx3)

find_package(catkin REQUIRED COMPONENTS roscpp sensor_msgs tf cmake_modules)


catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES imu_3dm_gx3
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

add_definitions("-std=c++0x -Wall -Werror")

find_package(Eigen REQUIRED)
include_directories(${catkin_INCLUDE_DIRS} ${eigen_INCLUDE_DIR})
add_executable(imu_3dm_gx3
  src/imu_3dm_gx3.cc
)
target_link_libraries(imu_3dm_gx3 ${catkin_LIBRARIES})
add_dependencies(imu_3dm_gx3 ${catkin_EXPORTED_TARGETS})
