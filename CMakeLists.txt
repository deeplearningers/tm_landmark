cmake_minimum_required(VERSION 3.16)
project(firstTengine)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fopenmp")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fopenmp")
set(CMAKE_CXX_STANDARD 11)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")


include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_SOURCE_DIR}/include/common)


#add_library(libtengine-lite-static STATIC IMPORTED)
#set_target_properties(libtengine-lite-static PROPERTIES IMPORTED_LOCATION ${PROJECT_SOURCE_DIR}/lib/libtengine/x86_64/tengine-lite-static.lib)

add_executable(firstTengine tm_landmark.cpp tengine_operations.c)

set(EXTRA_LIBS
        ${CMAKE_SOURCE_DIR}/lib/libtengine/x86_64/tengine-lite-static.lib)
        #${CMAKE_SOURCE_DIR}/lib/libtengine/x86_64/opencv_world347.lib)

target_link_libraries(firstTengine ${EXTRA_LIBS})
