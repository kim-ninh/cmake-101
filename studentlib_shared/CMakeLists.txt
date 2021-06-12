cmake_minimum_required(VERSION 3.0.0)
project(directory_test)
set(CMAKE_BUILD_TYPE Relase)

include_directories(include)

file(GLOB SOURCES "src/*.cpp")

add_library(testStudent SHARED ${SOURCES})
