cmake_minimum_required(VERSION 2.6)
project(cvplot_example)

#OPENCV
include_directories(~/local/include)
link_directories(~/local/lib)
#find_package(OpenCV REQUIRED)
#MESSAGE( STATUS "OpenCV version: " ${OpenCV_VERSION} )
#MESSAGE( STATUS "OpenCV libs: " ${OpenCV_LIBS} )

list( APPEND OpenCV_LIBS opencv_core opencv_imgcodecs opencv_highgui opencv_video opencv_videoio opencv_imgproc opencv_calib3d opencv_features2d opencv_xfeatures2d opencv_optflow opencv_cudaoptflow)

#ldof_gpu library
MESSAGE( STATUS "current folder: " ${CMAKE_CURRENT_SOURCE_DIR} )
include_directories( ~/Desktop/opencv-workspace/ldof_opencv/src )
link_directories( ~/Desktop/opencv-workspace/ldof_opencv/src )

# build as release type ==> faster
set( CMAKE_BUILD_TYPE Release )

#C++ AND linker flags
list(APPEND CMAKE_CXX_FLAGS "-std=c++11 -pipe -D __STDC_CONSTANT_MACROS -D STD=std -Wall -O3 -DNDEBUG -ggdb ${CMAKE_CXX_FLAGS}")

# create library
add_library( cvplot SHARED cvplot.cpp cvplot.h )
target_link_libraries( cvplot ${OpenCV_LIBS} )

# add the executable for myIDT
add_executable( ${PROJECT_NAME} plot_sample.cpp )
target_link_libraries( ${PROJECT_NAME} ${OpenCV_LIBS} cvplot )
