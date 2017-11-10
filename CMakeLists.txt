cmake_minimum_required(VERSION 3.8)
project(uav_target_recog)

find_package(OpenCV REQUIRED)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES main.cpp)
add_executable(uav_target_recog ${SOURCE_FILES})

if(DEFINED OpenCV_LIBRARIES)
    # This is a Windows hack - the Windows cmake file sets LIBRARIES while the *NIX one uses LIBS.
    set(OpenCV_LIBS ${OpenCV_LIBRARIES})
endif(DEFINED OpenCV_LIBRARIES)

include_directories(${OpenCV_INCLUDE_DIRS})
target_link_libraries(uav_target_recog ${OpenCV_LIBS})