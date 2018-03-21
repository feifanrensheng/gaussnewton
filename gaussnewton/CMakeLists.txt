cmake_minimum_required(VERSION 2.8)

project(gaussnewton)

set( CMAKE_BUILD_TYPE "Debug" )

set( CMAKE_CXX_FLAGS "-std=c++11 -O3" ) 
set(CMAKE_MODULE_PATH /home/zn/opencv-3.1.0/release)

# 寻找OpenCV库
find_package( Opencv REQUIRED )
if(Opencv_FOUND)
    message(STATUS "The OpenCV lib is found!")
endif()

# 添加头文件
include_directories( "/usr/include/eigen3" )

add_executable(gaussnewton gaussnewton.cpp)
target_link_libraries(gaussnewton ${OpenCV_LIBS})
