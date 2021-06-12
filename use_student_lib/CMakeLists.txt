cmake_minimum_required(VERSION 3.0.0)
project(TestLibrary)

set(STUDENT_LIB_DIR "${CMAKE_CURRENT_LIST_DIR}/../studentlib_shared")

IF(CMAKE_SYSTEM_NAME STREQUAL Linux)
message(STATUS "Using libtestStudent.so")
set(PROJECT_LINK_LIBS libtestStudent.so)
ENDIF()

IF(CMAKE_SYSTEM_NAME STREQUAL Darwin)
message(STATUS "Using libtestStudent.dylib")
set(PROJECT_LINK_LIBS libtestStudent.dylib)
ENDIF()

link_directories(${STUDENT_LIB_DIR}/build)

include_directories(${STUDENT_LIB_DIR}/include)

add_executable(libtest libtest.cpp)
target_link_libraries(libtest ${PROJECT_LINK_LIBS})