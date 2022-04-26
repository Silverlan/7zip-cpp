cmake_minimum_required(VERSION 2.8)
project(7zpp)
include(CTest)

file(GLOB 7ZPP_SOURCES  ${CMAKE_CURRENT_LIST_DIR}/7zpp/*.cpp ${CMAKE_CURRENT_LIST_DIR}/7zpp/*.h )
add_library(7zpp ${7ZPP_SOURCES})
target_include_directories(7zpp PRIVATE  ${CMAKE_CURRENT_LIST_DIR}   ${CMAKE_CURRENT_LIST_DIR}/7zpp ${CMAKE_CURRENT_LIST_DIR}/7z/C  ${CMAKE_CURRENT_LIST_DIR}/7z/CPP)

set(Boost_USE_STATIC_LIBS ON) 
set(Boost_USE_MULTITHREADED ON)  
find_package(Boost COMPONENTS filesystem ) 
# Setup testing
IF( NOT CMAKE_BUILD_TYPE )
   SET( CMAKE_BUILD_TYPE Debug)
ENDIF()
