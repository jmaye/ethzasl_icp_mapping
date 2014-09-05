cmake_minimum_required(VERSION 2.4.6)
include($ENV{ROS_ROOT}/core/rosbuild/rosbuild.cmake)

set(ROS_BUILD_TYPE Release)

rosbuild_init()

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

include($ENV{ROS_ROOT}/core/rosbuild/FindPkgConfig.cmake)

pkg_check_modules(EIGEN REQUIRED eigen3)
include_directories(${EIGEN_INCLUDE_DIRS})

rosbuild_add_library(ethzasl_gridmap_2d src/grid-map.cpp)
