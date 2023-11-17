cmake_minimum_required(VERSION 3.27)
project(MusiCV)

set(CMAKE_CXX_STANDARD 17)

# Add executable
add_executable(MusiCV main.cpp)

# Add dependencies
include(cmake/CPM.cmake)
