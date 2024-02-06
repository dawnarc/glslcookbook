cmake_minimum_required (VERSION 3.0)
set (CMAKE_CXX_STANDARD 11)

project (GLSLCOOKBOOK)

if(MSVC)
  add_definitions(/DNOMINMAX)
endif()

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/modules/")

find_package( glm REQUIRED )
include_directories(${GLM_INCLUDE_DIR})

find_package( glfw3 REQUIRED )
include_directories(${GLFW3_INCLUDE_DIR})

find_package( OpenGL REQUIRED )

include_directories( ingredients )

add_subdirectory( ingredients )
add_subdirectory( chapter01 )
add_subdirectory( chapter02 )
add_subdirectory( chapter03 )
add_subdirectory( chapter04 )
add_subdirectory( chapter05 )
add_subdirectory( chapter06 )
add_subdirectory( chapter07 )
add_subdirectory( chapter08 )
add_subdirectory( chapter09 )
add_subdirectory( chapter10 )

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/media DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
