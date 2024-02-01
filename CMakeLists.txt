cmake_minimum_required(VERSION 3.22.1)

project(LearnGStreamer C CXX)

find_package(PkgConfig REQUIRED)

pkg_check_modules(gstreamr-1.0 REQUIRED gstreamer-1.0)
include_directories(${gstreamr-1.0_INCLUDE_DIRS})
link_directories(${gstreamr-1.0_LIBRARIES_DIRS})

pkg_check_modules(gstreamr-audio-1.0 REQUIRED gstreamer-audio-1.0)
include_directories(${gstreamr-audio-1.0_INCLUDE_DIRS})
link_directories(${gstreamr-audio-1.0_LIBRARIES_DIRS})

pkg_check_modules(gstreamr-video-1.0 REQUIRED gstreamer-video-1.0)
include_directories(${gstreamr-video-1.0_INCLUDE_DIRS})
link_directories(${gstreamr-video-1.0_LIBRARIES_DIRS})

pkg_check_modules(gstreamr-pbutils-1.0 REQUIRED gstreamer-pbutils-1.0)
include_directories(${gstreamr-pbutils-1.0_INCLUDE_DIRS})
link_directories(${gstreamr-pbutils-1.0_LIBRARIES_DIRS})

pkg_check_modules(GTK3 REQUIRED gtk+-3.0)
include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})

add_executable(basic-tutorial-2-exercise basic-tutorial-2-exercise.c)
target_link_libraries(basic-tutorial-2-exercise ${gstreamr-1.0_LIBRARIES})

add_executable(basic-tutorial-3-exercise basic-tutorial-3-exercise.c)
target_link_libraries(basic-tutorial-3-exercise ${gstreamr-1.0_LIBRARIES})

add_executable(basic-tutorial-5-exercise basic-tutorial-5-exercise.cpp)
target_link_libraries(basic-tutorial-5-exercise ${gstreamr-1.0_LIBRARIES} ${GTK3_LINK_LIBRARIES})

add_executable(playback-tutorial-7-exercise playback-tutorial-7-exercise.c)
target_link_libraries(playback-tutorial-7-exercise ${gstreamr-1.0_LIBRARIES})

