cmake_minimum_required(VERSION 3.27)

# vcpkg integration
include(FetchContent)
FetchContent_Declare(vcpkg
        GIT_REPOSITORY "https://github.com/microsoft/vcpkg/"
)
FetchContent_MakeAvailable(vcpkg)
set(CMAKE_TOOLCHAIN_FILE "${vcpkg_SOURCE_DIR}/scripts/buildsystems/vcpkg.cmake" CACHE FILEPATH "")

project(MusiCV)

set(CMAKE_CXX_STANDARD 17)

# Add executable
add_executable(MusiCV main.cpp)

#
# Add Dependencies
#

# OpenCV
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
target_link_libraries(MusiCV ${OpenCV_LIBS})